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
        

  - Go to Jenkins dashboard  --->  Select your project  ---->  Configure  --->  Add a build step -----> Execute shell

      - docker build . -t myimg:latest
   
      - docker run -itd -p 8000:8000 myimg:latest
        

  - Click on Build now

  - Copy your instance id and paste it along with :8000

#### ( Successfully your application is running inside container )

( If you want to start this project automation wise , first kill(M)  your existing container for same port number allocation )

 
- Now Install Docker Compose ( Go to your terminal )

   ( Help of Docker-compose , No need to kill your container mannually )
  
  - sudo apt-get install docker-compose -y
 
  - docker-compose --version

- Go to Jenkins dashboard  --->  Select your project  ---->  Configure  --->  Add a build step -----> Execute shell

  ( Delete previous code and add below code )

    - docker-compose down
 
    - docker-compose up -d --force-recreate --no-deps --build web
 
- Go to your Github and chnage your code anything for test

- Click on Build now

- Copy your instance id and paste it along with :8000

#### ( Successfully your application is running inside container with same port number )


#### STEP-9 :-  For Automatic build process


- Go to Jenkins dashboard  --->  Select your project  ---->  Configure
  
- Build Triggers   ----->  Enable : GitHub hook trigger for GITScm polling   ---> save

- Click on Jenkins dashboard   ---->  Manage Jenkins  --->  Plugins

- Click on Available plug-ins  --->  Install GitHub Integration plug-in ( Restart it )
