---
title: User-scoped
---
## Saving an user-scoped environment variable

Visit the Environment Variables section at [https://www.devzero.io/dashboard/environment-variables/user](https://www.devzero.io/dashboard/environment-variables/user) to add, remove, or update your user-scoped environment variables and secrets. User-scoped environment variables can only be seen, managed, and used by you.

{% hint style="info" %}
User-scoped environment variables are automatically made available on each of your running workspaces by default.
{% endhint %}

![Adding personal environment variables](../.gitbook/assets/Personal%20variables.gif)

## Using an environment variable

![Personal Environment Variables](../.gitbook/assets/Update%20environment%20variables%20(1).png)

Using an environment variable within your workspace is how you would normally use any environment variable (eg: `echo $NOT_SO_SECRET_KEY`).

{% hint style="info" %}
Note: User secrets are not available during build time, they are only available during launch and runtime steps. However, all user secrets are automatically available as environment variables within each user's workspace.
{% endhint %}

To use it in a recipe, you can reference it the same way. If your environment variable is called `MY_KEY`:

![Environment Variables during build-stage](../.gitbook/assets/env-var-in-build.png)

Need to store a secret environment variable? Check out the [secrets.md](secrets.md "mention") page.
