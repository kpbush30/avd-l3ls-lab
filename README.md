# AVD L3LS Lab

## Getting Started

This is a simple example used to demonstrate AVD getting started videos. Here is how to get started using MacOS or Linux.

This repository will use the UV python project and package manager, you can [install UV here](https://docs.astral.sh/uv/getting-started/installation/)

### Native Envrionment

If you are running MacOS or a distribution of Linux, you can follow the directions below to run AVD natively as part of a virtual envrionment.

1. Clone the repository

    ```bash
    git clone https://github.com/kpbush30/avd-l3ls-lab
    ``` 

2. The following will install all python and ansible requirements

    ```bash
    uv sync
    ansible-galaxy collection install -r requirements.yml
    ```

3. Now you can test running your first AVD build using `uv run`.

    ```bash 
    uv run make build-site-1 build-site-2
    ```
    
    You can also activate the python virtual envrionment and run without UV

    ```bash
    source .venv/bin/activate
    make build-site-1 build-site-2
    ```

4. From here you can follow any of the AVD instructional videos

If you are a MAC user, you will most likely need to address this [known issue](https://avd.arista.com/5.5/ansible_collections/arista/avd/roles/eos_validate_state/index.html?h=fork%28%29#known-issues) Run the following in your current session to resolve the issue. Add to your `.bash_profile` for persistence across terminals.

```bash
export OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES
```

## Container Options

You can run the AVD dev container using a variety of container management tools, depending on what you have available to you or simply personal preference.

### Podman

A very popular option that is owned and actively maintained by Red Hat. Here's how to get started:

1. [Install podman](https://podman.io/docs/installation) to your desktop
2. Deploy and run the AVD container using podman

    ```bash
    podman run -it ghcr.io/aristanetworks/avd/universal:python3.11-avd-v5.5.1
    ```

3. This should launch a shell that will give you an Ansible capable envrionment with AVD preinstalled

    ```bash
    avd ➜ / $ ansible --version
    ansible [core 2.18.6]
    config file = None
    configured module search path = ['/home/avd/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
    ansible python module location = /home/avd/.local/lib/python3.11/site-packages/ansible
    ansible collection location = /home/avd/.ansible/collections:/usr/share/ansible/collections
    executable location = /home/avd/.local/bin/ansible
    python version = 3.11.12 (main, Apr  9 2025, 22:06:32) [GCC 10.2.1 20210110] (/usr/local/bin/python3.11)
    jinja version = 3.1.6
    libyaml = True
    
    avd ➜ / $ ansible-galaxy collection list | grep arista
    arista.avd        5.5.1
    arista.cvp        3.12.0
    arista.eos        11.0.1

    avd ➜ / $ pip list | grep avd
    pyavd                     5.5.1
    ```

### Docker Desktop 

1. [Install Docker](https://docs.docker.com/desktop/) to your desktop
2. Deploy and run the AVD container using podman

    ```bash
    docker run -it -w /avd ghcr.io/aristanetworks/avd/universal:python3.11-avd-v5.5.1
    ```

3. This should launch a shell that will give you an Ansible capable envrionment with AVD preinstalled

    ```bash
    avd ➜ / $ ansible-galaxy collection list | grep arista
    arista.avd        5.5.1
    arista.cvp        3.12.0
    arista.eos        11.0.1

    avd ➜ / $ pip list | grep avd
    pyavd                     5.5.1
    ```

### Lima VM

Yet another very lighweight option that is very easy to use on MacOS. You can [install Lima](https://lima-vm.io/docs/installation/) to your desktop and watch a great intro to using [AVD with Lima](https://youtu.be/Th2dx2FKtPc?feature=shared).

## VSCode Dev Containers

The respository is equiped with the dev container to run natively within vscode. This option works for Windows, MacOS, or Linux, leveraging containers to run AVD to generate your configurations.

This will require installing the following:

1. Install [VSCode](https://code.visualstudio.com/download) and the [VSCode Dev Containers Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
2. Install [Docker Desktop](https://docs.docker.com/get-started/introduction/get-docker-desktop/)

Once installed, you can follow the 

1. Open VSCode and click the `><` icon a the bottom left
2. Select `Reopen in Container`
3. Now you can test running your first AVD build
4. If you would like to update the AVD container, modify the `.devcontainer/devcontainer.json` file with the new image

    > You can find AVD dev container images [published here](https://github.com/aristanetworks/avd/pkgs/container/avd%2Funiversal/versions?filters%5Bversion_type%5D=tagged)

    ```json
    {
        "name": "AVD Universal",
        "image": "ghcr.io/aristanetworks/avd/universal:python3.12-avd-v5.5.1" << Update Image Version
    }
    ```

5. From here you can follow any of the AVD instructional videos

## AVD Examples

While this repository contains a specific AVD example, there are additional examples within the AVD Ansible collection. If you followed the steps above, you can find the additional examples under the `collections/` folder. Specifically the `collections/ansible_collections/arista/avd/examples/`