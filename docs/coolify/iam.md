---
head:
  - - meta
    - name: description
      content: Coolify - Users
  - - meta
    - name: keywords
      content: users coollabs coolify 
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

# Identity & Access Management (IAM)


## Users
After you successfully installed Coolify, you can start configuring it via the provided UI.

### Registration

The first registered user will be the `root/admin` user (with id 0) of your Coolify instance. This user will see and change all resources deployed, access system-wide configurations, initiate the one-click update process, etc.

:::tip 
After the first user is registered successfully, `registration is disabled` to prevent unwanted registrations. 

You can enable registration in the `Settings` menu. 
:::

Every other user won't access system-wide configurations and only see their own team's resources.

### Authentication Methods
`Email/password` registration is supported.

### Reset Password

Admins can reset the passwords of team members in the `Settings` menu. If a password reset is requested, the user has 10 minutes to do it. 

Password reset is done through the login process. The user's new password will be the one used on the login form. 

After 10 minutes, the old password can be used to log in, and the password reset process is stopped. 


## Teams
Each registered user has its own team automatically. Each team only has access to its own resources. 

You can register any number of teams and invite any number of users to it.

You can only access other team's resources if someone with an `admin` privilege invites you to that team.

### Privileges
Team members could have two kinds of privileges:

- `admin` has the same privileges as the `owner` of the team.

Admin can check, modify, delete any resources that are owned by the team.

- `read` can only read things.

### Root Team
With the first user, a `root team` is also created with id `0`. 

Users in this team have the same privileges as the first user so that they see and change all resources deployed, access system-wide configurations, initiate one-click update process, etc.
