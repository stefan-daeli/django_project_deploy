### Check Server
```
lsb_release -a
```
**desc*
```
ll
```
**desc*
```
sudo apt update && sudo apt upgrade -y
```
**desc*
### Install Python
```
apt install python3.xx-venv
```
**example : ```python3.12```, ```python3.13```*
```
python3 --version
```
**desc*
### Install & Configure Git
```
sudo apt install git -y
```
**desc*
```
git config --global user.name "<git_username>"
```
**desc*
```
git config --global user.email "<git@mail.com>"
```
**desc*
```
ssh-keygen -t ed25519 -C "<git@mail.com>"
```
**desc*
```
git config --list
```
**desc*
```
eval "$(ssh-agent -s)"
```
**desc*
```
ssh-add ~/.ssh/id_ed25519
```
**desc*
```
cat ~/.ssh/id_ed25519.pub
```
**desc*
```
ssh -T git@github.com
```
**desc*
### install Nginx
```
sudo apt install nginx -y
```
```
nginx -v
```

