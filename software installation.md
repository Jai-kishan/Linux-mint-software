#Software install via terminal

## google chrome
```
echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/chrome.list
```
```
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -
```
```
apt-get update
```
```
apt-get install google-chrome-stable
```

## sublime 3 Text Editor Install 

```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```
```
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```
```
sudo apt-get update
```
```
sudo apt-get install sublime-text
```

### uninstall sublime 3
```
sudo apt-get remove sublime-text && sudo apt-get autoremove
```

## NodeJs
```
sudo apt install nodejs
```
