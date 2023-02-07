### Deploy lyfe bot on the aws for 2 rupees
<p align="center">
<img src="https://i.imgur.com/EjCAmkU.jpeg" alt="animated" width="400" height="280" />
</p>
// ###### Create a AWS account for 2 rupees(indian) 

// https://aws.amazon.com/resources/create-account/

   #### Install with script
```
      wget -N "https://gist.githubusercontent.com/lyfe00011/0208883ee3a3f602d0f7c7ff138c05ea/raw/install.sh" && chmod +x install.sh 
```
```
bash install.sh
```
\* #### Install without script
 
 ###### 1. Install git ffmpeg curl
   
```
    sudo apt -y update &&  sudo apt -y upgrade
```
      
```
     sudo apt -y install git ffmpeg curl
```
*********
###### 2. Install nodejs
```
      sudo apt -y remove nodejs
```
      
```
       curl -fsSl https://deb.nodesource.com/setup_lts.x | sudo bash - && sudo apt -y install nodejs
```
###### 3. Install yarn
```
         curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
```
         
```  
         echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```
     
```  
        sudo apt -y update && sudo apt -y install yarn
```
###### 4. Install pm2
       
```
         sudo yarn global add pm2
```

###### 5. Clone Repo and install packages

```
  git clone https://github.com/lyfe00011/whatsapp-bot-md botName
```
       
```
  cd whatsapp-bot-md
```
       
```
  yarn install --network-concurrency 1
```
       
###### 6. Enter Environment Variables

###### copy paste lines below (paste it after adding the SESSION ID only)

```
         echo "SESSION_ID = Session_Id_you_Got_After_Scan_Dont_Add_This_Line_If_You_Can_Scan_From_Terminal_Itself

         PREFIX = .

         STICKER_PACKNAME = LyFE

         ALWAYS_ONLINE = false

         RMBG_KEY = null

         LANGUAG = en

         WARN_LIMIT = 3

         FORCE_LOGOUT = false

         BRAINSHOP = 159501,6pq8dPiYt7PdqHz3

         MAX_UPLOAD = 200

         REJECT_CALL = false

         SUDO = 989876543210

         TZ = Asia/Kolkata

         VPS = true

         AUTO_STATUS_VIEW = true

         SEND_READ = false" > config.env
```
###### [Read More](https://github.com/lyfe00011/whatsapp-bot-md/wiki/Environment_Variables)

###### nano config.env, if you want edit. TO Save ctrl + o press enter then ctrl + x

*\
###### 7. start and stop bot

         To start bot `pm2 start . --name botName --attach`

         To stop bot `pm2 stop botName`
