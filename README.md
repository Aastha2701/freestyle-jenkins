# freestyle-jenkins


#### STEP-1 :- Create an Ubuntu-22 instance and Connect it

#### STEP-2 :-  Install java

- sudo apt update

- sudo apt install openjdk-11-jre -y

- java -version

#### STEP-3 :-  Set-up Jenkins binary and key files

#### STEP-4 :-  Install jenkins and Login it

#### STEP-5 :-  Generate password and mention your password

#### STEP-6 :-  Install suggested plug-ins

#### STEP-7 :-  Define jenkins username and password

#### STEP-8 :-  Go to jenkins dashboard and create project ( Container only )

  - Click on New Item
    
  - Enter an item name = my-own-project-freestyle

  - Select Freestyle project and  Click ok

  - GitHub project = Github-repo url

  - Source Code Management = Github-repo url

  - Credentials  =  Add --->  generate it

  - Save

  - Now Install Docker & allow permission ( Go to your terminal )
    
      - sudo apt-get install docker.io -y
   
      - sudo usermod -aG docker $USER
   
      - sudo usermod -aG docker jenkins
   
      - sudo systemctl restart docker
   
      - sudo systemctl restart jenkins
