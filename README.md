# AVD L3LS Lab

## Getting Started

This is a simple example used to demonstrate AVD getting started videos. Here is how to get started using MacOS or Linux.

> See the Windows section to explore options here.

This repository will use the UV python project and package manager, you can [install UV here](https://docs.astral.sh/uv/getting-started/installation/)

1. Clone the repository

2. The following will install all python and ansible requirements

    ```bash
    uv sync
    ansible-galaxy collection install -r collections/requirements.yml
    ```

3. Now you can test running your first AVD build using `uv run`.

    ```bash 
    uv run make build-site-1 build-site-2
    ```

4. 
5. From here you can follow any of the AVD instructional videos

## Windwos Users

## MacOS Users

If you are a MAC user, you will most likely need to address this [known issue](https://avd.arista.com/5.5/ansible_collections/arista/avd/roles/eos_validate_state/index.html?h=fork%28%29#known-issues)

Run the following in your current session to resolve the issue. Add to your `.bash_profile` for persistence across terminals.

```bash
export OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES
```