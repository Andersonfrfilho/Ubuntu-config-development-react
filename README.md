# Ubuntu-config-development (GNU=Ubuntu config)(Linux=[terminal,zsh])

1. mount pendrive boot with gpt
   * obs: due to the new 9th generation processors and processes, we must use the following pen drive boot configurations using the rufus, important
   
<hr/>

2. install curl
   * update packages linux and system
     - ```sudo apt update```
     - ```sudo apt upgrade```
   * install curl 
     - ```sudo apt install curl```
   * testing success
     - ```curl --version```
     
<hr/> 

3. install docker
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
<hr/>

4. install Node (NVM)
   * install with curl 
     - ```curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash```
   * instance envoriment variable
     - ```export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm```
   * install version image do node
     - ```nvm install --lts```
   * use version image
     - ```nvm use --lts```
     
<hr/>

5. install Yarn/NPM
   * install npm
     - ```sudo apt install npm```
   * testing success
     - ```npm ––version```
   * install yarn 
     - ```sudo npm install yarn –g```
   * testing success
     - ```yarn --version```
     
<hr/>

6. install Git
   * update packages linux
      - ```sudo apt-get update```
   * install package git-core
     - ```sudo apt-get install git-core```
   * testing success
     - ``git --version```
   * config enviroment global git 
     - ```git config --global user.name "testuser" without aspas```
     - ```git config --global user.email "testuser@example.com" without aspas```
   * referencia <https://www.liquidweb.com/kb/install-git-ubuntu-16-04-lts/>
   
<hr/>

7. install font fira-code
   * https://github.com/tonsky/FiraCode
   
7. install visual code
   * download do visual studio code 
     - ```https://code.visualstudio.com/Download```
   * in file on download dpkg using comand
     - ```sudo dpkg -i code_1.26.0-1534177765_amd64.deb```
   
   * configure isntall extension
     - Material Icon
     - Dracula theme
   * configure JSON preferences shift + ctrl + p = JSON.preference
     - paste json config
     ```json
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
8. install zsh
   * use comand
     - ```sudo apt-get install zsh
   * define temrinal default
      - ```bash -c zsh```
   * Instalar oh-my-zsh
     - ```sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"```
   * Install spaceship
     - ```git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"```
   * symlink
     - ```ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"```

     - case problem use
       - ```sudo code . ~/.zshrc --user-data-dir='.'```
   * config file
     - define theme
       - ```ZSH_THEME="spaceship"```
     - ```json
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
     - add in files
       - ```json
       zinit light zdharma/fast-syntax-highlighting
       zinit light zsh-users/zsh-autosuggestions
       zinit light zsh-users/zsh-completions
       ```
   - add temrinal visual code preference
     
     - ```"terminal.integrated.shell.osx": "/bin/zsh"```
     
   - transform default terminal zsh in terminal
   
     - ```sudo usermod -s /usr/bin/zsh $(whoami)```
   
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
     - execute code .bashrc past in last lines
       - ```
          export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64

          export ANDROID_HOME=$HOME/Android/Sdk

          export PATH=$PATH:$ANDROID_HOME/emulator

          export PATH=$PATH:$ANDROID_HOME/tools

          export PATH=$PATH:$ANDROID_HOME/tools/bin

          export PATH=$PATH:$ANDROID_HOME/platform-tools
         ```
     - in /home with terminal execute comand
       - ```source .bashrc```
   - Install dependencies
     - ```sudo apt install android-tools-adb android-tools-fastboot```
   
   - Comands git
     - access develop
     - run git pull
     - back to branch
     - run git merge develop
   
