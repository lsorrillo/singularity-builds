# singularity-builds
This repo will be used in conjunction with singularity-Hub to
create Singularity containers.

The general workflow is to create a branch into which we install 
a subdirectory of the same name. The signularity definition file 
for a prospective container is placed in this directory and a link
created at the base of the repo. For example,



1. Clone the Git repo.

 git clone https://github.com/lsorrillo/singularity-builds

2. Make sure your repo is up-to-date.

 git pull

3. Start your project.

 Scenario 1:  Create a HelloWorld container
  * git checkout -b HelloWorld
  * mkdir HelloWorld
  * cd HelloWorld
  * create Singularity definition file. The contents might look like below:

 ````
  BootStrap:docker
  From:centos:latest
  %runscript
  echo 'This gets run when you run the image!" cd /code exec echo 'Hello' "$@"
 
  %post
     echo 'Hello from inside the container'
     mkdir -p /code
  echo 'End of the post'

 ````

4. Every Singularity definition file should be at the base of directory tree in each branch.

  * ln -s Singularity ../

5. Push your changes to commence image creation on singularity Hub.

  * git commit -m "Make appropriate comment here"
  * git push origin HelloWorld:HelloWorld
