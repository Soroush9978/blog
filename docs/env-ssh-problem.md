
# SSH Config Issue and Resolution

## Problem
While trying to connect to a remote server using an SSH config file, the user encountered the following error:

```
ssh: Could not resolve hostname hetz-vm: Name or service not known
```

The user was able to connect directly using the command:

```
ssh -p 2929 root@116.202.25.235
```

## Configuration
The SSH config file (`~/.ssh/config`) was as follows:

```ssh
Host hetz-vm
    HostName 116.202.25.235
    Port 2929
    User root
```

## Troubleshooting Steps
1. **Check Configuration File Location:** Ensured the config file is at `~/.ssh/config`.
2. **File Permissions:** Verified the file had correct permissions using:
   ```bash
   chmod 600 ~/.ssh/config
   ```
3. **Direct SSH Command:** Confirmed that the direct SSH command worked.
4. **Verbose Output:** Used the verbose mode with:
   ```bash
   ssh -vvv hetz-vm
   ```

## Resolution
The issue was identified as using `sudo` before the `ssh` command. This caused the SSH client to look for the config file in the root user's home directory instead of the regular user's home directory.

### Recommended Solutions
- **Direct User Specification:** Use:
   ```bash
   sudo ssh -p 2929 root@116.202.25.235
   ```
- **Preserve Environment:** Use the `-E` option with `sudo`:
   ```bash
   sudo -E ssh hetz-vm
   ```
- **Edit Root's SSH Config:** If frequent root access is needed, consider adding the configuration to `/root/.ssh/config`.

## Conclusion
Understanding the context in which commands are run is crucial for troubleshooting issues related to SSH configuration.
