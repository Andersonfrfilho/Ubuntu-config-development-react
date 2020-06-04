# Ubuntu-config-development

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

          "editor.rulers":[80,120]
        }
      ```
8. install zsh
   * Instalar oh-my-zsh
     - ```sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"```
   * Install spaceship
     - ```git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"```
   * symlink
     - ```ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"```
   * use comand
     - ```sudo apt-get install zsh
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
   
