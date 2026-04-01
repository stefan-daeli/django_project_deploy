### Check Server
```
lsb_release -a
```
**```Linux Standard Base release``` | displaying Linux distribution information*
```
ll
```
**```long listing``` | display a list of files in detailed view*
```
sudo apt update && sudo apt upgrade -y
```
**Update package list*
### Install Python
```
apt install python3.xx-venv
```
**example : ```python3.12```, ```python3.13```*
```
python3 --version
```
**python version checker*
### Install & Configure Git
```
sudo apt install git -y
```
**git install*
```
git config --global user.name "<git_username>"
```
**Set a global Git username*
```
git config --global user.email "<git@email.com>"
```
**Set a global Git email*
```
ssh-keygen -t ed25519 -C "<git@email.com>"
```
**Generate an SSH key using the ```ed25519 algorithm```. This is used for secure authentication to a Git server (without a password).*
```
git config --list
```
**Display all active Git configurations (global and local).*
```
eval "$(ssh-agent -s)"
```
**Run the SSH agent in the background. The agent stores SSH keys so repeated authentication is not required.*
```
ssh-add ~/.ssh/id_ed25519
```
**Adds the SSH private key ```id_ed25519``` to the SSH agent.*
```
cat ~/.ssh/id_ed25519.pub
```
**Displays the SSH public key. This key will be copied to the GitHub account.*
```
ssh -T git@github.com
```
**Test the SSH connection to GitHub*
### install Nginx
```
sudo apt install nginx -y
```
```
nginx -v
```
### Install MySQL Server
```
sudo apt install mysql-server -y
```
```
sudo systemctl status mysql
```
**If inactive*
```
sudo systemctl start mysql
```
```
sudo systemctl enable mysql
```
```
sudo mysql
```

