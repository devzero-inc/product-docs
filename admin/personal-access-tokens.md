---
title: Personal Access Tokens
---
## Managing Personal Access Tokens

To manage Personal access tokens, nagivate to [User Settings](https://www.devzero.io/dashboard/settings/user-settings) and find the "Personal Access Tokens" section

To create a token, click on "Create new token". Once the token is created, be sure to copy and save the token contents somewhere secure, it will not be shown again.
![Creating a devzero personal access token](../.gitbook/assets/pat-dialog.png)

Deleting a token is performed in the same section.

![Deleting a devzero personal access token](../.gitbook/assets/pat-delete.png)

## Using a personal access token

A personal access token can be used to authenticate the `dz` cli. Simply log in by passing the token contents via the `--token` flag. Upon token expiry, the cli will prompt to re-authenticate.

```
dz auth login --token <token contents>
```
