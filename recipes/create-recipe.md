---
title: Creating a Recipe
---
{% embed url="https://devzero.b-cdn.net/create-first-recipe.mp4" %}
Create your first DevZero Recipe!
{% endembed %}

## 1. Create New Recipe

From your [DevZero Console](https://devzero.io/dashboard), select `Create New` >> `Create new recipe`. This will take you to the [new repo](https://www.devzero.io/dashboard/recipes/new) page.

![Click 'Create new recipe'](https://devzero.b-cdn.net/click-create.gif)

## 2. Name Your Recipe

Provide a name for your new Recipe.

![Name your Recipe](https://devzero.b-cdn.net/name%20recipe.gif)

## 3. Select Repository

From here, you can choose to use a public Github repository by providing a URL or you can authenticate to our Github App to select a private repository.

Alternatively, you can launch a blank Recipe by clicking "Create a recipe" without providing a code repo.

![Add code to your Recipe.](https://devzero.b-cdn.net/add-repo-to-recipe.gif)

{% hint style="info" %}
If you're not using GitHub or prefer a different authentication method, check out this section on [cloning source code](cloning-source-code.md).
{% endhint %}

## 4. Make Recipe Changes

Make desired changes to your Recipe, select 'Save and Build' to initiate a build process, verifying successful Recipe compilation. To streamline Recipe creation, we offer suggested steps based on an analysis of your code.

After you've successfully built your Recipe and are done iterating, you're ready to Publish the Recipe to your Recipe Library.

![Make Recipe changes.](https://devzero.b-cdn.net/recipe-edit.gif)

{% hint style="info" %}
 We provide detailed build logs to help you identify any errors in your build and make iterating on Recipes easy.
{% endhint %}

## 5. Launch A Workspace from New Recipe and Connect

Click 'Launch' to create a new Workspace from your Recipe. To connect to your Workspace, you'll need to [install the DevZero CLI](../references/cli-man-page/install-the-cli.md). From there you can connect with VSCode or a directly with a terminal.

![Launch and connect to a Workspace.](https://devzero.b-cdn.net/connect-to-workspace.gif)
