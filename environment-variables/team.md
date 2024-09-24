---
title: Team-scoped
---
## Saving a team-scoped environment variable

Visit the Environment Variables section at [https://www.devzero.io/dashboard/environment-variables/team](https://www.devzero.io/dashboard/environment-variables/team) to add, remove or update your  team-scoped environment variables. Team-scoped environment variables can be referenced and used by anyone within your DevZero team.

![Team environment variables](../.gitbook/assets/Update%20environment%20variables%20(1).png)

{% hint style="info" %}
Team-scoped environment variables and secrets must be directly referenced in your recipe template steps. Unlike user-scoped environment variables, they are **not** automatically added to every workspace.
{% endhint %}

![Team Environment Variables](../.gitbook/assets/Update%20environment%20variables.png)

## Using a team-scoped environment variable

Using an environment variable within your workspace is how you would normally use any environment variable (eg: `echo $NOT_SO_SECRET_KEY`).

To use it in a build, you can reference it the same way. If your environment variable is called `MY_KEY`:

![Environment Variables during build-stage](../.gitbook/assets/env-var-in-build.png)

Need to store a secret environment variable? Check out the [secrets.md](secrets.md "mention") page.
