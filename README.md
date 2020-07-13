# Linux-Zsh-GNU-Ubuntu-config-development 
  - (GNU=Ubuntu config)(Linux=[terminal,zsh]) - RUFUS

1. mount pendrive boot with gpt
   * obs: due to the new 9th generation processors and processes, we must use the following pen drive boot configurations using the rufus, important
   
<hr/>
2. Install zsh
   - Update the packages
      - ```sudo apt update```
   - Install zsh
      - ```sudo apt install zsh```
   - Install curl 
     - ```sudo apt install curl```
   - Install git
     - ```sudo apt install git-all```
   - Zsh default terminal
     - ```chsh -s $(which zsh)```
   - Install Firacode font
     - download in repository
       - ```https://github.com/tonsky/FiraCode```   
   - Install Oh my zsh
     - ```sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"```
   - Install SpaceshipTheme
     - clone reposiory in ~
       - ```git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"```
     - linking repository
       - ```ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"```
    - Instal visual code
      - download visual studio code
        - ```https://code.visualstudio.com/download```
      - open folder download archive
      - run command
        - ```sudo dpkg -i code...```
    - Configure theme zsh
      - in folder ~ with terminal
        - ```code ./.zshrc```
      - in file replace `ZSH_THEME="robbyrussell"`
        - ```ZSH_THEME="spaceship"```
    - Install plugins zsh
      - run comand
        - ```sh -c "$(curl -fsSL https://raw.githubusercontent.com/zdharma/zinit/master/doc/install.sh)"```
      - restart terminal
      - open .zshrc, and add file
        - ```zinit light zdharma/fast-syntax-highlighting
             zinit light zsh-users/zsh-autosuggestions
             zinit light zsh-users/zsh-completions
          ```
      - restart terminal
    - Install nvm
      - run command
        - ```curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash```
      - add file profile enviroment variable nvm past in .zshrc or .bashrc
        - ```export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
             [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
          ```
      - install node 
        - ```nvm install --lts```
      - use node
        - ```nvm use --lts```
    - Install Yarn
      - run comand to add package repository
        - ```curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -```
      - write file
        - ```echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list```
      - install yarn
        - ```sudo apt update && sudo apt install --no-install-recommends yarn```
    - Install jdk8
      - add package
        - ```sudo add-apt-repository ppa:openjdk-r/ppa```
      - update packages
        - ```sudo apt-get update```
      - install package
        - ```sudo apt-get install openjdk-8-jdk```
      - install drives x86
        - ```sudo apt-get install gcc-multilib lib32z1 lib32stdc++6```
    - Install Android Stuio
      - download Android Studio.tar.gz
      - extract file in directori `~` where home/user
      - create a file in `~/Android/Sdk`
      - add profile file `.zshrc`
      - add ```export PATH=$PATH:~/android-studio/bin```
      - add in before alias coment ```alias sudo='sudo env PATH=$PATH $@'```
      - run terminal ```studio.sh```
      - not import config
      - send realtory
      - (welcome) next
      - (install type) custom
      - select JAVA_HOME
      - using visual code for open files ```sudo code . --user-data-dir='.'```
      - add variables envoriment in bash/.bashrc file
    - Configure visual code
      - `shift` + `ctrl` + `p` find JSON preferenes
      -      ```json
      {
        //Defini o tema e icones
        "workbench.colorTheme": "Dracula",
        "workbench.iconTheme": "material-icon-theme",
        //Aumenta font terminal
        "terminal.integrated.fontSize":14,

        //Configura tamanho e familia da fonte
        "editor.tabSize":2,
        "editor.fontSize": 14,
        "editor.lineHeight": 24,
        "editor.fontFamily": "Fira Code",
        "editor.fontLigatures":true,

        "explorer.compactFolders": false,
        "editor.renderLineHighlight":"gutter",
        "workbench.editor.labelFormat":"short",

        "javascript.updateImportsOnFileMove.enabled":"never",

        "breadcrumbs.enabled":true,
        "editor.parameterHints.enabled":false,
        "typescript.updateImportsOnFileMove.enabled":"never",
        "explorer.confirmDragAndDrop":false,
        "explorer.confirmDelete":false,
        "editor.rulers":[80,120],
        "terminal.integrated.shell.linux": "/bin/zsh",
        "editor.codeActionsOnSave": {
          "source.fixAll.eslint": true
        },
        "emmet.syntaxProfiles": { "javascript": "jsx" },
        "emmet.includeLanguages": { "javascript": "javascriptreact" },
        "files.associations": {
          ".sequelizerc": "javascript",
          ".stylelintrc": "json",
          ".prettierrc": "json"
        },
        "material-icon-theme.folders.associations": {
          "infra": "app",
          "entities": "class",
          "schemas": "class",
          "typeorm": "database",
          "repositories": "mappings",
          "http": "container",
          "migrations": "tools",
          "modules": "components",
          "implementations": "core",
          "dtos": "typescript",
          "fakes": "mock",
          "websockets": "pipe",
          "protos": "pipe",
          "grpc": "pipe"
        },

        "material-icon-theme.files.associations": {
          "ormconfig.json": "database",
          "tsconfig.json": "tune",
          "*.proto": "3d"
        },
      }
      ```
     - install extensions live shared
       - ```wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs```
     
<hr/> 

3. install docker,docker-compose, docker-machine
   * update packages linux
     - ```sudo apt-get update```
   * **(opcional) case remove oldest versions** 
     - ```sudo apt-get remove docker docker-engine docker.io```
   * install docker package
     - ```sudo apt install docker.io```
   * Start and Automate Docker, the Docker service needs to be setup to run at startup. To do so, type in each command followed by enter
     - ```sudo systemctl start docker```
     - ```sudo systemctl enable docker```
   * Testing success
     - ```docker --version```
   * Referencies
     - ```https://www.digitalocean.com/community/questions/how-to-fix-docker-got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket```

   * **Optional**
   * Install docker-compose 
     - ```sudo apt install docker-compose```
   * Install docker-machine
     - ```
          base=https://github.com/docker/machine/releases/download/v0.16.0 &&         
          curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&
          sudo mv /tmp/docker-machine /usr/local/bin/docker-machine &&
          chmod +x /usr/local/bin/docker-machine
       ```
   * testing 
     - ```docker-machine version```
   * create machine default
     - install virtual-box
       - ```sudo apt-get install virtualbox```
     - isntall machine default -d second plan, 
       - ```docker-machine create -d virtualbox temp.sysadmin.local```
       - path
         - ```eval $(docker-machine env temp.sysadmin.local)```
         - ```docker-machine env temp.sysadmin.local ```
     - initial machine default
       - ```docker-machine start default```
   * Back Docker-LocalMachine return enviroment variable
     - este comando troca para o docker local
     - ```eval "$(docker-machine env -u)"```
<hr/>
   
8. install Android Studio and configure enviroment
   - Install java JDK
     - ```sudo apt install openjdk-8-jdk```
     - test instalation
       - ```java --version```
   - Download Android studio
     - ```wget https://dl.google.com/dl/android/studio/ide-zips/3.4.0.18/android-studio-ide-183.5452501-linux.tar.gz```
   - Install package
     - ```sudo tar -xvzf android-studio-ide-183.5452501-linux.tar.gz```
   - Execute comands
     - ```cd android-studio```
     - ```cd bin```
     - ```./studio.sh```
     - choice options e go to config adb/sdk_options/Licensys agree licenses
     - execute ```code .bashrc``` or ```code .zshrc``` past in last lines
       - ```
          export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64

          export ANDROID_HOME=$HOME/Android/Sdk

          export PATH=$PATH:$ANDROID_HOME/emulator

          export PATH=$PATH:$ANDROID_HOME/tools

          export PATH=$PATH:$ANDROID_HOME/tools/bin

          export PATH=$PATH:$ANDROID_HOME/platform-tools
         ```
     - in /home with terminal execute comand in bash 
       - ```source .bashrc```
     
     - or zsh  
       - ```source .zshrc```
         - case problem use
           - ```sudo code . ~/.zshrc --user-data-dir='.'```
   - Install dependencies
     - ```sudo apt install android-tools-adb android-tools-fastboot```
   
   - Open Android Studio, install emulator and initialized
     - ```cd android-studio;cd bin;./studio.sh```
     - in config/sdk_manager/Android_SDK/SDK_tools
       - ```select Google play licenses sdk tools```
       - ```acept terms```
     - in config/abd_manager/initialized one emulator
   - Common Problemns
     - Unable to load script from assets 'index.android.bundle'. Make sure...
       * Esse erro geralmente acontece porque o sistema não conseguiu criar o bundle inicial que contém todo o código Javascript da aplicação. Para resolver comece criando uma pasta ```assets``` dentro da pasta ```android/app/src/main```.
       * Logo após, execute o comando:
         - ```npx react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res/```
        * Agora, feche as abas do terminal e execute novamente o comando:
          - ```npx react-native run-android``` **or** ```yarn run react-native run-android``` **or** ```yarn android```
   - **Comands commons que salvam xD** 
   - git
     - access develop
       - ```git checkout branch_name```
     - run 
       - ```git pull```
     
     - back to branch
       - ```git checkout branch_name```
     - run git merge develop
       - ```git merge branch_name```
   - Node
     - kill process nodeJs
       * case netstat command not found
         - ``sudo apt-get install net-tools```
       - see a process in port
         * ```sudo netstat -lpn |grep :'3000'```
       - kill the id process without aspas
         * ```kill -9 id_process```
   
   - Problems with emulator in projects react-native, when install dependencia, or bundle not start
      - Register bundle
        - ```npx react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res/```
      - reset cache
        - ```cd android;./gradlew clean;cd ..;npx react-native run-android;npx react-native start --reset-cache;```
      - link assets
        - ```npx react-native link```
   - Force kill process
     - alt + f2
     - click in program 
