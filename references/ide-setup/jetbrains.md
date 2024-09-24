---
title: JetBrains
---
This doc contains information about connecting to DevZero workspaces using any of the following JetBrains IDEs:

- CLion
- GoLand
- IntelliJ
- PhpStorm
- PyCharm
- Rider
- RubyMine
- RustRover
- WebStorm

## Connect to a workspace

{% tabs %}
{% tab title="Using JetBrains Gateway" %}

- Сlick **New Connection** under the **SSH** connection provider.

![Connect using SSH](./../../.gitbook/assets/jetbrains-gateway-connect.png)

- Create a new connection using username "devzero" and the workspace you want to connect to in host. Then click on **Check Connection and Continue**.

![Configure SSH connection to your workspace](./../../.gitbook/assets/jetbrains-gateway-host-configuration.png)

- Select the IDE of your preference and the path of your codebase. Then click on **Download IDE and Connect**.

![Select your IDE](./../../.gitbook/assets/jetbrains-gateway-ide-selection.png)

{% hint style="info" %}
The default path for your cloned code is `/home/devzero`
{% endhint %}

- Under **Connections > SSH**, you should see your workspace listed.

![Your workspaces](./../../.gitbook/assets/jetbrains-gateway-workspaces.png)
{% endtab %}

{% tab title="Using any JetBrains IDE" %}

- Create a new project under **Remote Development > SSH**.

![Connect using SSH](./../../.gitbook/assets/jetbrains-remote-project.png)

- Create a new connection using username "devzero" and the workspace you want to connect to in host. Then click on **Check Connection and Continue**.

![Configure SSH connection to your workspace](./../../.gitbook/assets/jetbrains-gateway-host-configuration.png)

- Select the IDE of your preference and the path of your codebase. Then click on **Download IDE and Connect**.

![Select your IDE](./../../.gitbook/assets/jetbrains-gateway-ide-selection.png)

{% hint style="info" %}
The default path for your cloned code is `/home/devzero`
{% endhint %}

- Under **Remote Development > SSH**, you should see your workspace listed.

![Your workspaces](./../../.gitbook/assets/jetbrains-workspaces.png)
{% endtab %}
{% endtabs %}
