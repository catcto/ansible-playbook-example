# ansible-playbook-example

Use Ansible to manage servers, including server initialization, software installation, environment configuration, and more.

## Installation

### Server

1. Initialize `Ubuntu 22.04`. Refer to the [Ubuntu 22.04 Initialization](https://notes.xiaowu.ai/%E5%BC%80%E5%8F%91%E7%AC%94%E8%AE%B0/%E6%9C%8D%E5%8A%A1%E5%99%A8%E8%BF%90%E7%BB%B4/Ubuntu).
2. Install `Docker`. Refer to the [Docker Installation](https://notes.xiaowu.ai/%E5%BC%80%E5%8F%91%E7%AC%94%E8%AE%B0/%E6%9C%8D%E5%8A%A1%E5%99%A8%E8%BF%90%E7%BB%B4/Docker).
3. Install `Ansible`. Refer to the [Ansible Installation](https://notes.xiaowu.ai/%E5%BC%80%E5%8F%91%E7%AC%94%E8%AE%B0/%E6%9C%8D%E5%8A%A1%E5%99%A8%E8%BF%90%E7%BB%B4/Ansible).
4. Install `Zsh` and `Oh My Zsh`. Refer to the [Zsh Installation](https://notes.xiaowu.ai/%E5%BC%80%E5%8F%91%E7%AC%94%E8%AE%B0/%E6%9C%8D%E5%8A%A1%E5%99%A8%E8%BF%90%E7%BB%B4/Shell#Zsh).
5. Create directories for applications, data, and temporary files:
   ```shell
   $ mkdir ~/apps ~/data ~/temp
   ```

### Local

For MacOS, use `brew install ansible` for installation. Alternatively, you can use the ansible-devops image. Refer to the [detailed steps](https://github.com/catcto/ansible-devops).

## Usage

### Run Docker Compose

```shell
ansible-playbook -i inventory.ini playbook/docker.yml -e "docker_compose=test" -l "my-server-1,my-server-2"
ansible-playbook -i inventory.ini playbook/docker.yml -e "docker_compose=test docker_service=redis" -l "my-server-1"
ansible-playbook -i inventory.ini playbook/docker.yml -e "docker_compose=test docker_command='--file docker-compose.dev.yaml'" -l "my-server-2"
```