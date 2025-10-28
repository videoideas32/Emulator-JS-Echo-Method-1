<img width="148" height="148" alt="image" src="https://github.com/user-attachments/assets/0296594e-cdc9-4c48-93bc-47d8e87e0590" />


...................................................................................................................................................................................................................


THIS PROJECT IS NOT ASSOCIATED WITH EMULATOR JS AND CONTAINS ONLY THE USAGE OF METHODS FOUND ONLINE

This project is simply a version of EmulatorJS that is able to be ran in a codespace


INSTRUCTIONS BELOW


1. Go to the github codespaces home page after creating/logging in to your github account
   
2. Create a codespace with a blank template and open it

3. Type or paste this command into the terminal, run the command and wait for it to finish

   git clone https://github.com/linuxserver/docker-emulatorjs.git
cd docker-emulatorjs
docker build \
  --no-cache \
  --pull \
  -t lscr.io/linuxserver/emulatorjs:latest .

5. Create a file titled docker-compose.yml in the root of the codespace with the following contents

   ---
version: "2.1"
services:
  emulatorjs:
    image: lscr.io/linuxserver/emulatorjs:latest
    container_name: emulatorjs
    environment:
      # PUID/PGID can be ignored in Codespaces as file permissions are handled differently
      - TZ=Etc/UTC # Set your timezone
    volumes:
      # Using relative paths here will create folders inside your cloned repository
      - ./config:/config
      - ./data:/data
    ports:
      - 80:80
      - 3000:3000
    restart: unless-stopped

    

6. Run the command: docker-compose up -d in the terminal and let it run



   CONGRATS

   You have officially installed everything you need to start
⠀
   Click on the ports tab and open port 3000 in the browser by clicking the globe icon

   Follow the instructions on screen to download the default fileset

   After completed add game roms to the roms folder on codespaces (located under the retro system name underneath of the data folder)

   After adding them go back to port 3000 and click to scan the retro system you have added roms to

   After scan is complete click on the game systems on the left side and click add all to config

   After adding all games: open port 80 by clicking the globe icon and your emulator should be working


  CONGRATS YOU NOW HAVE YOUR OWN EMULATOR INSTALLED





   COMMANDS FOR TROUBLESHOOTING

   docker-compose restart
   docker-compose start
   docker-compose stop

MAY NEED TO CHECK THE ACTUAL README FILE FOR CORRECT FORMAT FOR CODE AND/OR .yml FILE CONTENTS
