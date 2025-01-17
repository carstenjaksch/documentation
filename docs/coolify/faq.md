---
head:
  - - meta
    - name: description
      content: Coolify - Teams
  - - meta
    - name: keywords
      content: teams coollabs coolify 
  - - meta
    - name: twitter:card
      content: summary_large_image
  - - meta
    - name: twitter:site
      content: '@andrasbacsai'
  - - meta
    - name: twitter:title
      content: Coolify
  - - meta
    - name: twitter:description
      content: An open-source & self-hostable Heroku / Netlify alternative.
  - - meta
    - name: twitter:image
      content: https://cdn.coollabs.io/assets/coollabs/og-image-documentation.png
  - - meta
    - property: og:type
      content: website
  - - meta
    - property: og:url
      content: https://coolify.io
  - - meta
    - property: og:title
      content: Coolify
  - - meta
    - property: og:description
      content: An open-source & self-hostable Heroku / Netlify alternative.
  - - meta
    - property: og:site_name
      content: Coolify
  - - meta
    - property: og:image
      content: https://cdn.coollabs.io/assets/coollabs/og-image-documentation.png
---
# FAQ

## Run Coolify with existing Traefik instance

Here is a [detailed blog](https://beaussan.io/blog/coolify-into-existing-traefik) post from [Nicolas Beaussart](https://twitter.com/beaussan) on how to use Coolify with your existing Traefik instance!


## Rollback to a specific version
You can always roll back to a specific Coolify version (for example 3.11.1) with the following command:

```bash
wget -q https://get.coollabs.io/coolify/install.sh \
-O install.sh; sudo bash ./install.sh -fx 3.11.1 
```

:::warning
As database schema changes sometimes, there could be a potential problem where the UI/API is looking for old schema that does not exists anymore and throws an error. Then you should revert the rollback.
:::

## Reset Root password
This will tag the root user with a password reset flag. Then if you login in the
next 10 minutes, your password will be changed to the password you are using to
login.

> If expires, just execute this script again.

```bash
docker exec coolify bash -c \ 
"sqlite3 /app/db/prod.db 'update User set password=\"RESETME\", updatedAt=`date +%s%N|cut -b1-13` where id=0'"
```

