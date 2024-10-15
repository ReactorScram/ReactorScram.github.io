<html>
<head>
  <link rel="stylesheet" href="../style.css">
  <title>Dev VM Checklist</title>
</head>
<body>

[Index](../index.html)

Created 2024 Oct 10, updated Oct 15

**Dev VM Checklist**

For cleaning up a typical Ubuntu 20.04 / 22.04 install.

1. Tell Ubuntu to ignore system errors and updates. (There is always at 
least one)
2. ```bash
sudo apt-get remove \
    bluez bluez-cups bluez-obexd \
    cups cups-common docker.io \
    libreoffice-base-core libreoffice-common \
    openvpn python3-update-manager \
    thunderbird ubuntu-release-upgrader-core vim-common
```
3. `sudo apt-get autoremove`
4. `sudo apt-get update && sudo apt-get upgrade`
5. `sudo apt-get install curl git kate konsole pkg-config`
6. `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
7. `ssh-keygen -t ed25519`
8. Set up `~/.gitconfig`
```ini
[gpg]
    format = ssh
[pull]
    rebase = false
[advice]
    diverging = false
[gpg "ssh"]
    allowedSignersFile = /home/user/.config/git/allowed_ssh_signers
```
9. Set up `~/.config/git/allowed_ssh_signers` = 
`/home/user/.ssh/id_ed25519.pub`
10. In repos that need signed commits, run ```bash
git config commit.gpgsign true
git config user.signingkey /home/user/.ssh/id_ed25519.pub
git config user.email ReactorScram@users.noreply.github.com
git config user.name "Not Applicable"
```
11. `mkdir -p ~/projects/2024`
12. [Tauri v2 pre-requisites](https://v2.tauri.app/start/prerequisites/)
13. [Install PNPM](https://pnpm.io/installation)
14. `sudo usermod -aG docker $USER`
15. In Kate, set "Show whitespace indicators" to "Always", under 
"Scrollbars", set "Show marks", in "Text Navigation", set "Allow scrolling past the end of the document"

</body>
</html>
