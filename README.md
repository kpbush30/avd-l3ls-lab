# AVD L3LS Lab



## MACOS Users

If you are a MAC user, you will most likely need to address this known issue

https://avd.arista.com/5.5/ansible_collections/arista/avd/roles/eos_validate_state/index.html?h=fork%28%29#known-issues

Run the following in your current session to resolve the issue. Add to your `.bash_profile` for persistence across terminals.

```bash
export OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES
```