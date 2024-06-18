# Docker and Docker Compose

{% code overflow="wrap" lineNumbers="true" %}
```yaml
version: "3"
build:
  steps:
    - type: apt-get
      packages: ["curl", "apt-transport-https", "ca-certificates"]
    - type: apt-get
      packages: ["docker-ce", "docker-ce-cli", "containerd.io"]
      extra_repositories:
      - key_url: https://download.docker.com/linux/ubuntu/gpg
        repository: https://download.docker.com/linux/ubuntu
    - type: command
      command: |
        curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
        chmod +x /usr/local/bin/docker-compose

        groupadd docker || true
        usermod -aG docker devzero
        mkdir -p /home/devzero/.docker
        newgrp docker
        chown devzero:devzero /home/devzero/.docker -R
        chmod g+rwx /home/devzero/.docker -R
        systemctl enable docker.service
        systemctl enable containerd.service
      directory: /home/devzero
      user: root
launch:
  steps:
    - type: command
      command: |
        systemctl start docker
      directory: /home/devzero
      user: root
```
{% endcode %}
