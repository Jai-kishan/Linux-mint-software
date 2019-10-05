# Linux-mint-software
how to install Linux mint basic software using termianl

# sublime
* Open a terminal and use the command below to install the GPG key.
```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add - 
```

### After that, create add the repository in your sources.list.
```
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```

### Now refresh the package list and install Sublime Text.
```
sudo apt update && sudo apt install sublime-text
```

# Ipython
```
sudo apt install ipython
```


# Ipython3
```
sudo apt install ipython3
```


#++++++++++++++++++++++++++++++++++++#
# Virtual Enviourment Install
#++++++++++++++++++++++++++++++++++++#
```
sudo apt install virtualenv
```

#++++++++++++++++++++++++++++++++++++#
# Virtual ENviourment Create
#++++++++++++++++++++++++++++++++++++#
###python-2
```
virtualenv enviourment_name -p python
```

### python-3
```
virtualenv enviourment_name -p python3
```

#++++++++++++++++++++++++++++++++++++#
# GIT
#++++++++++++++++++++++++++++++++++++#
```
sudo apt install git
```
