## Setup Jenkins



```
brew install jenkins-lts
```
When this command fails it will ask to install Java. At this particular time the version below was recommended.
```
brew cask install homebrew/cask-versions/adoptopenjdk8
```

Try the first command again.

Open:
```
sudo nano /usr/local/opt/jenkins-lts/homebrew.mxcl.jenkins-lts.plist

Change
```
<string>--httpListenAddress=127.0.0.1</string>
to
```
<string>--httpListenAddress=0.0.0.0</string>

Run 
```
brew services start jenkins-lts
```
=> 👍 



References:
https://www.jenkins.io/download/lts/macos/
https://www.macminivault.com/installing-jenkins-on-macos/
