# windows-node-version-manager

Recently, I faced a situation where I needed to adjust the Node version on my machine. While the process of upgrading or downgrading Node is straightforward, it can become inconvenient when frequent adjustments are necessary.

What if there was a solution that allowed you to have multiple Node versions on your PC, eliminating the need for constant switches? This article provides guidance on installing and seamlessly switching between various Node.js versions on a Windows-based computer

## Step 1: Uninstall Node.js.

If you already have a particular Node version installed, go to your PC’s cPanel to uninstall it.

Here is how:
- Click the start button, and search for “Control Panel.”
- Under Program, click “Uninstall program.”
- A new page with all your installed programs will appear, find Nodejs and uninstall it.

You may need to restart your system to complete the process.

## Step 2: Installing NVM - Node Version Manager

NVM (Node Version Manager) proves to be an invaluable tool for simplifying the installation and management of multiple Node.js versions on your computer. This tool offers a convenient solution for switching between different Node.js versions through user-friendly commands, providing enhanced flexibility for code testing or utilizing distinct versions for various projects.

To install NVM, you can visit the GitHub download page [here](https://github.com/coreybutler/nvm-windows/releases) and follow the installation guide.

Alternatively, to streamline the process, you can use a bash command. Begin by downloading a bash terminal such as Git Bash, available [here](https://gitforwindows.org/), and installing it.

Once you've opened your Git Bash terminal, enter the following code:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install | bash
```

This command initiates the installation process for NVM on your machine.

### Version Configuration

NVM provides the flexibility to choose your preferred version. For example, you can use `v1.11` instead of `v0.39.0`. The specified version may vary, and using the latest version is recommended.

After completing the installation, close the bash terminal and reopen it.

To confirm a successful installation, run the command `nvm` to display the list of available NVM commands. If the list is visible, you can proceed to the next step. However, if you encounter an error like:

```bash
bash: nvm: command not found
```

Please follow the next step to resolve this issue.

## Step 3 Terminal Configuration for NVM

To ensure NVM is successfully installed, run the following command:

```bash
cat ~/.bashrc
```

If you see an output similar to the following:

```bash
$ cat ~/.bashrc
cat: /c/Users/your_username/.bashrc: No such file or directory
```

This indicates that there's no existing bash configuration. To resolve this, follow the steps below:

1. Create a `.bashrc` file by running the command:

```bash
touch .bashrc
```

This command creates a file with the `.bashrc` extension (though it may not be visible).

2. Open the `.bashrc` file for editing using the command:

```bash
nano .bashrc
```

3. Add the following configuration to the file:

```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

4. Press `Ctrl + X` to save the file.

5. Press `Ctrl + Z` to close the file.

With these configurations, your bash is now set up to use NVM. Run the command `nvm` again, and you should now see the list of NVM commands.

## Node Version Management with NVM

### Step 4: Installing Different Node Versions

To install a specific Node version, use the following command:

```bash
nvm install <version>
```

For example:

```bash
nvm install 12.4.0
```

This installs Node.js version 12.4.0. You can install additional versions using the same syntax.

### Step 5: Switching and Using a Node Version

To switch to and use a specific Node version, employ the command:

```bash
nvm use <version>
```

For instance:

```bash
nvm use 12.5.8
```

Ensure that you have installed the desired Node version using NVM. To view the list of installed Node.js versions, execute:

```bash
nvm ls
```

If you need to switch to a different Node.js version, you can easily do so.

**Note**: If you use Yarn to manage Node packages, you need to reinstall it for each Node version. However, if you use npm, there is no need to worry.

To install Yarn, run:

```bash
npm i -g yarn
```

This globally installs Yarn on your system.

And that's it! With NVM, managing and switching between different Node.js versions becomes a seamless process, enhancing your development workflow.
