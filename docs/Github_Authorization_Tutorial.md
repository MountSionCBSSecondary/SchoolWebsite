# How to authorise Fedora for work on GitHub

## 1) Generate RSA files

- In Fedora, go to Applications → Utilities → Terminal

- Type "ssh-keygen -t rsa -b 4096 -C <your_email@example.com>" and press Enter twice

- Press Enter twice again

## 2) Add your SSH key to the SSH Agent

- In Terminal, type "eval $(ssh-agent -s)" and press Enter

- Then, type ssh-add ~/.ssh/id_rsa and press Enter

## 3) Adding SSH file to GitHub

- In the Terminal, type "cd ~/.ssh" and press Enter

- Then type "vi id_rsa.pub" and press Enter

- Copy all of the file's contents

- Then hold down the SHIFT key and tap the colon key, release SHIFT key and type "wq" and press Enter

- Go to GitHub.com and login

## 4) Adding SSH to GitHub

- After login click on your profile picture and Settings

- Navigate to SSH Keys Settings

- Add a New SSH Key

- Choose your own title and paste the copied contents of id_rsa.pub into the Key section and save

## 5) Initialize Authorization

- Create a repo/fork

- Click on Clone/Download

- Clone as SSH

- Use the copy button to the side of the Text

- In Terminal, type git clone and copy in copied text

- If prompted, type yes to everything

- Congratulations, you have successfully authorised your computer for GitHub!
