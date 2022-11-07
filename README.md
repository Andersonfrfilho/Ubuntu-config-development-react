# Linux-Zsh-GNU-Ubuntu-config-development 
  - (GNU=Ubuntu config)(Linux=[terminal,zsh]) - RUFUS

  <p align="center">
    <a href="#">
      <img src="./images/logo.png" alt="logo" style="height: 250px;width:750px; margin-right: 10px;">
    </a>
    <h3 align="center">Configuration development - NodeJs | ReactJs | React-Native </h3>
  </p>

1. mount pendrive boot with gpt
   * obs: due to the new 9th generation processors and processes, we must use the following pen drive boot configurations using the rufus, important
   - select **(GPT) partition scheme

    <p align="center">
      <img src="./images/pen-drive-boot.png" alt="Markdown Monster icon" style="height: 550px;width:450px; margin-right: 10px;">
    </p>
    <br/>
   - select **(GPT) partition scheme

    <p align="center">
      <img src="./images/part-1.png" alt="Markdown Monster icon" style="height: 450px;width:550px; margin-right: 10px;">
    </p>
    <br/>
   - in partition manager select steps select type instalation size(32mb~=550mb)type-partition(primary)Use as EFI()
    <p align="center">
      <img src="./images/part-2.png" alt="Markdown Monster icon" style="height: 450px;width:550px; margin-right: 10px;">
    </p>
    <br/>
   - create second partition swap this partition manager bootloader in your system Use as(swap), type(Primary) size:double memory ram
    <p align="center">
      <img src="./images/part-3.png" alt="Markdown Monster icon" style="height: 450px;width:550px; margin-right: 10px;">
    </p>
    <br/>
   - create root partition / <- root partition memory total
    <p align="center">
      <img src="./images/part-4.png" alt="Markdown Monster icon" style="height: 450px;width:550px; margin-right: 10px;">
    </p>
    <br/>
<hr/>

2. Configure your system

   - Update the packages
      - ```sudo apt update```
   - Install komo
      - ```https://github.com/cheesecakeufo/komorebi```
      - sudo dpkg -i package
      - download video
      - https://mylivewallpapers.com/movies/the-matrix-animated-wallpaper/
      - create wallpaper with wallpaper creator
      - sudo mv home/name_wallpaper /System/Resources/Komorebi
      - change file .komorebi
      - change name wallpaper
      
      <hr/>
       
   - Install [Zsh](https://www.zsh.org/)
      - ```sudo apt install zsh```

      <hr/>
       
   - Install [curl](https://curl.haxx.se/) 
     - ```sudo apt install curl```
   - Install [git](https://git-scm.com/)
     - ```sudo apt install git-all```

      <hr/>
       
   - [Zsh](https://www.zsh.org/) default terminal
     - ```chsh -s $(which zsh)```
     - reload system
     - option 2 

      <hr/>
       
   - Install [Firacode](https://github.com/tonsky/FiraCode) font
     - download in repository
       - ```https://github.com/tonsky/FiraCode```

      <hr/>
       
   - Install [Oh my zsh](https://ohmyz.sh/)
     - ```sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"```

      <hr/>
       
   - Install [SpaceshipTheme](https://github.com/denysdovhan/spaceship-prompt)
     - clone reposiory in ~
       - ```git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"```
     - linking repository
       - ```ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"```

      <hr/>
       
   - [Theme Gnome Terminal Dracula](https://draculatheme.com/gnome-terminal/)
     - You'll need the `dconf` command (if you run a recent Gnome version). In Ubuntu,this can be installed by running:
       - ```sudo apt-get install dconf-cli```
     - In other distros you'll need to dig around to find it, search your repositories for dconf related packages.
     - After installing dconf, you can clone this repository to your machine.
       - ```git clone https://github.com/dracula/gnome-terminal```
       - ```cd gnome-terminal```
     - Then you can run the installation script:
       - ```./install.sh```
     - Open terminal gnome-terminal
     - setting
     - preference custom fonts

      <hr/>
         
   - Instal [Visual Studio Code](https://code.visualstudio.com/download)
     - download visual studio code
       - ```https://code.visualstudio.com/download```
     - open folder download archive
     - run command
       - ```sudo dpkg -i code...```

      <hr/>
       
   - Using [Spaceship](https://github.com/denysdovhan/spaceship-prompt)
     - run command in directory `~` <- this directory /home/your_user
       - ```code .zshrc```
     - Set ZSH_THEME="spaceship" in your .zshrc.
        - ```ZSH_THEME="spaceship"```

      <hr/>
       
   - Install [plugins Zsh](https://zdharma.org/zinit/wiki/INTRODUCTION/)
     - run comand
       - ```sh -c "$(curl -fsSL https://raw.githubusercontent.com/zdharma/zinit/master/doc/install.sh)"```
       - restart terminal
       - open zshrc add in file
     - open `.zshrc`, and add file run command
       - ```code .zshrc```
       - ```
          ### End of Zinit's installer chunk
          zinit light zdharma/fast-syntax-highlighting
          zinit light zsh-users/zsh-autosuggestions
          zinit light zsh-users/zsh-history-substring-search
          zinit light zsh-users/zsh-completions
          zinit light buonomo/yarn-completion

          pasteinit() {
            OLD_SELF_INSERT=${${(s.:.)widgets[self-insert]}[2,3]}
            zle -N self-insert url-quote-magic # I wonder if you'd need `.url-quote-magic`?
          }

          pastefinish() {
            zle -N self-insert $OLD_SELF_INSERT
          }
          zstyle :bracketed-paste-magic paste-init pasteinit
          zstyle :bracketed-paste-magic paste-finish pastefinish

          SPACESHIP_PROMPT_ORDER=(
          user          # Username section
          dir           # Current directory section
          host          # Hostname section
          git           # Git section (git_branch + git_status)
          hg            # Mercurial section (hg_branch  + hg_status)
          exec_time     # Execution time
          line_sep      # Line break
          vi_mode       # Vi-mode indicator
          jobs          # Background jobs indicator
          exit_code     # Exit code section
          char          # Prompt character
          )
          SPACESHIP_USER_SHOW=always
          SPACESHIP_PROMPT_ADD_NEWLINE=false
          SPACESHIP_CHAR_SYMBOL="❯"
          SPACESHIP_CHAR_SUFFIX=" "
          ```
      - restart terminal

   <hr/>

   - Install [Nvm](https://github.com/nvm-sh/nvm)
     - run command
       - ```curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash```
     - Add file profile enviroment variable nvm past in `.zshrc` or `.bashrc`
       - ```
            export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
            [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
         ```
     - Install node 
       - ```nvm install --lts```
     - use node
       - ```nvm use --lts```

   <hr/>

   - Install [Yarn](https://classic.yarnpkg.com/pt-BR/docs/install)
     - run comand to add package repository
       - ```curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -```
     - write file
       - ```echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list```
     - install yarn
       - ```sudo apt update && sudo apt install --no-install-recommends yarn```

   <hr/>

   - Install JDK8 -> java development kit
     - add package
       - ```sudo add-apt-repository ppa:openjdk-r/ppa```
     - update packages
       - ```sudo apt-get update```
     - install package
       - ```sudo apt-get install openjdk-8-jdk```
     - install drives x86
       - ```sudo apt-get install gcc-multilib lib32z1 lib32stdc++6```

   <hr/>

   - Install [Android Stuio](https://developer.android.com/studio)
     - download Android Studio.tar.gz
     - extract file in directori `~` where home/user
     - create a file in `~/Android/Sdk`
     - add profile file `.zshrc`
     - java default `/usr/lib/jvm/java-8-openjdk-amd64`

     - ```
        export JAVA_HOME=CAMINHO_ANOTADO_COM_SUA_VERSÃO
        export ANDROID_HOME=~/Android/Sdk
        export PATH=$PATH:$ANDROID_HOME/emulator
        export PATH=$PATH:$ANDROID_HOME/tools
        export PATH=$PATH:$ANDROID_HOME/tools/bin
        export PATH=$PATH:$ANDROID_HOME/platform-tools
        # emiter shorcut Android studio
        export PATH=$PATH:~/android-studio/bin
        ```
     - run terminal `studio.sh`
     - add proxy
     - automatic proxy
     - not import config
     - send realtory
     - (welcome) next
     - (install type) custom
     - select JAVA_HOME
     - using visual code for open files `sudo code . --user-data-dir='.'`
     - add variables envoriment in bash/.bashrc file
  
  <hr/>

   - Configure visual code

     - `shift` + `ctrl` + `p` find JSON preferenes

     - ```json
          {
            //Defini o tema e icones
            "workbench.colorTheme": "Omni",
            "workbench.iconTheme": "material-icon-theme",
            //Aumenta font terminal
            "terminal.integrated.fontSize":14,
            "workbench.editor.enablePreview": false,
            //Configura tamanho e familia da fonte
            "editor.tabSize":2,
            "editor.fontSize": 14,
            "editor.lineHeight": 24,
            "editor.fontFamily": "Fira Code",
            "editor.fontLigatures":true,
            "cSpell.language": "en,pt,pt_BR",

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

     - Extensions
       
       * [carbon-now-sh](https://marketplace.visualstudio.com/items?itemName=ericadamski.carbon-now-sh)
       
       * [Code autocomplete](https://marketplace.visualstudio.com/items?itemName=svipas.code-autocomplete)
      
       * [Color Highlighting](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)
       
       * [Color picker](https://marketplace.visualstudio.com/items?itemName=anseki.vscode-color)

       * [Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)

       * [Code spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)
         
         * [Brazilian Portuguese - Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker-portuguese-brazilian)
         
         * [Fullstack - Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=rbalet.code-spell-checker-fullstack)

       * [DotEnv](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv)
      
       * [EditorConfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)

       * [Eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
      
       * [Git history](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)
       
       * [Git Lens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
       
       * [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost)
       
       * [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)
    
          - install extensions live shared

            - ```wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs```

       * [MarkDown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)
       
       * [Material Icon theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)

       * [Omni Theme](https://marketplace.visualstudio.com/items?itemName=rocketseat.theme-omni)
       
       * [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
       
       * [Preview](https://marketplace.visualstudio.com/items?itemName=searKing.preview-vscode)
       
       * [vscode-styled-components](https://marketplace.visualstudio.com/items?itemName=jpoissonnier.vscode-styled-components)
       
       * [docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
       
       * [handlebars](https://marketplace.visualstudio.com/items?itemName=andrejunges.Handlebars)
         * [install](ext install andrejunges.Handlebars)
       
       * [handlebars - preview](https://marketplace.visualstudio.com/items?itemName=greenbyte.handlebars-preview)
         * [install](ext install andrejunges.Handlebars)

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
     - Create the docker group if it does not exist
     - ```sudo groupadd docker```
     - Add your user to the docker group.
     - ```sudo usermod -aG docker $USER```
     - Run the following command or Logout and login again and run (that doesn't work you may need to reboot your machine first)
     - ```newgrp docker```
     - Check if docker can be run without root
     - ```docker run hello-world```
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

  - Install insomnia

  <hr/>

  - install spotify
  - Flat Remix
  <hr/>
  
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
         - ```sudo apt-get install net-tools```
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
     
   - Electron
     * possiveis erros
     * 17502:0812/101639.918679:FATAL:setuid_sandbox_host.cc(158)] The SUID sandbox helper binary was found, but is not configured correctly. Rather than run without sandboxing I'm aborting now. You need to make sure that /home/miyazaki/Documents/gluco/glucogear-device-upload/node_modules/electron/dist/chrome-sandbox is owned by root and has mode 4755.
       * ```CONFIG_USER_NS=y enables the user namespaces feature, but they're still restricted to privileged users by default. This suggests sysctl kernel.unprivileged_userns_clone=1```
# The art of debugging issues
  - Check what the error is
  - Check your code against mine
  - Open Google and search for the error
  - Report it in course's forums
# Include as much details as you can
  - Errors the bug produced
  - The file(s) with the issue
  - The time in the lecture where the error occurs
# left show apllication tolbar
  - gsettings set org.gnome.shell.extensions.dash-to-dock show-apps-at-top true
# emulator or views emulators
* https://github.com/Genymobile/scrcpy

git config

- config editor:
  - `git config --global --global core.editor code`
  - `git config --global --edit`

```gitconfig
[alias]
	s = !git status -s
	c = !git add --all && git commit -m 
	l = !git log --pretty=format:'%C(blue)%h%C(red)%d %C(white)%s - %C(cyan)%cn, %C(green)%cr'
[core]
	editor = \"C:\\Users\\ander\\AppData\\Local\\Programs\\Microsoft VS Code\\bin\\code\" --wait
[safe]
	directory = D:/project/cherry-go-backend
[core]
	editor = code --wait
```

```sh
emulator -no-snapshot -avd pixel-6-pro
```

