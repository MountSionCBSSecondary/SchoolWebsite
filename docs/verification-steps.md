## How to verify someone's work done on the website via http-server
Just in case you don't know what I mean by this, when you are pinged to review somebody's work on the website, we would like to have a real environment where we can test the website as if it was live on the website itself. To do this, we make a server using the program http-server. Let's go through how to do this.

#Ensure that npm is installed
http-server runs on the backend of npm, so we have to make sure it's installed. To do this:
- Open Terminal and type npm --version
- If it comes up stating the version of the program, congrats! It's installed and you don't have to do anything else on this step. You can move onto 'How to install http-server'.
- However if you are greeted with an install prompt, decline it. Instead we will utilise a different method of installing npm.

#How to install npm in Terminal:
In Fedora 29, the current version as of 17/1/19, in order to install programs from the terminal, we utilize the 'yum' command. Since npm is included in Fedora's list of applications, we can just install it easily using the following steps:
- In Terminal, type 'yum install npm' and when prompted, accept all questions and allow it to install itself
- You are now ready to move onto the next step.

#How to install http-server:
Now you are ready to make your server, how do we do this? Via the program http-server! To do this:
- Navigate to the branch you are testing
- Type 'npm i -g http-server' and press Enter and allow it to install, if you get any errors, ignore. They are mild and won't affect the usage of the program in our case.
- Type 'http-server -c-1'
- Congratulations! You are now set up to start testing the work on the website and to verify everything works! Just copy one of the IP addresses it gives you into your browser of choice and navigate the website. To close the program in Terminal, just hold down CTRL and tap C.