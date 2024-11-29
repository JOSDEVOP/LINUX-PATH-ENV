
# Linux PATH Environment Variable Cheat Sheet

## Understanding the PATH Environment Variable
- **Definition:** The `PATH` variable is a list of directories the system searches for executables when you type a command.
- **Usage in DevOps:** To configure tools like Terraform, Ansible, Jenkins, or SDKs.

---

## Temporary vs. Permanent Path Updates
- **Temporary:** Lasts until the terminal session ends.
- **Permanent:** Applies every time you log in.

---

## Temporary Path Update
1. Open a terminal.
2. Add the directory to your `PATH` using `export`:
   ```bash
   export PATH=$PATH:/path/to/your/directory
   ```
3. Verify the change:
   ```bash
   echo $PATH
   ```

### Example
Add `/usr/local/terraform`:
```bash
export PATH=$PATH:/usr/local/terraform
```

---

## Permanent Path Update
### Steps
1. Identify your shell:
   ```bash
   echo $SHELL
   ```
   - Common shells:
     - Bash: `~/.bashrc` or `~/.bash_profile`
     - Zsh: `~/.zshrc`

2. Edit the configuration file:
   ```bash
   nano ~/.bashrc
   ```

3. Add the new PATH:
   ```bash
   export PATH=$PATH:/path/to/your/directory
   ```

4. Apply the changes:
   ```bash
   source ~/.bashrc
   ```

5. Verify:
   ```bash
   echo $PATH
   ```

---

## Example for DevOps Tools
### Adding Terraform
1. Open `~/.bashrc`:
   ```bash
   nano ~/.bashrc
   ```
2. Add the line:
   ```bash
   export PATH=$PATH:/usr/local/terraform
   ```
3. Save and apply:
   ```bash
   source ~/.bashrc
   ```
4. Verify:
   ```bash
   terraform --version
   ```

---

## Best Practices
1. **Keep Paths Organized:** Use directories like `/usr/local/bin` or `~/bin` for custom tools.
2. **Avoid Duplicates:** Check existing paths in `PATH`.
3. **Verify Executables:** Use `which` to ensure the correct tool is used:
   ```bash
   which terraform
   ```
4. **Test Changes:** Confirm the behavior of tools after adding paths.

---

## Common Commands
| Command                      | Description                                      |
|------------------------------|--------------------------------------------------|
| `export PATH=$PATH:/path`    | Temporarily add a directory to the PATH variable |
| `echo $PATH`                 | Display the current PATH                        |
| `nano ~/.bashrc`             | Edit the shell configuration file               |
| `source ~/.bashrc`           | Apply changes without restarting the terminal   |
| `which <command>`            | Locate the executable used for a command        |
