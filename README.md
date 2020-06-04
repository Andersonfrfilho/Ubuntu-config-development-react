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
