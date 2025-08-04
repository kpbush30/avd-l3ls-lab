# AVD L3LS Lab

## Getting Started

This is a simple example used to demonstrate AVD getting started videos. Here is how to get started using MacOS or Linux.

This repository will use the UV python project and package manager, you can [install UV here](https://docs.astral.sh/uv/getting-started/installation/)

### Native Envrionment

If you are running MacOS or a distribution of Linux, you can follow the directions below to run AVD natively.

1. Clone the repository

    ```bash
    git clone 
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

### VSCode Dev Containers

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