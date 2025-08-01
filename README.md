# AVD L3LS Lab

## Getting Started

This is a simple example used to demonstrate AVD getting started videos. Here is how to get started with:

1. Clone the repository

2. The following will install all requirements and drop you into your python 

    ```bash
    # Create python virtual envrionment and install all requirements
    uv sync

    # Activate new python virtual environment
    source .venv/bin/activate
    
    # Install ADV Ansible Collection reuqirements 
    ansible-galaxy collection install -r collections/requirements.yml
    ```

3. Now you can test running your first AVD build. If you are on windows, there will be a section on running AVD

    ```bash 
    make build-site-1 build-site-2
    ```

4. From here you can follow any videos on how to 


## MACOS Users

If you are a MAC user, you will most likely need to address this known issue

https://avd.arista.com/5.5/ansible_collections/arista/avd/roles/eos_validate_state/index.html?h=fork%28%29#known-issues

Run the following in your current session to resolve the issue. Add to your `.bash_profile` for persistence across terminals.

```bash
export OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES
```