# Tutorial to log into a course-specific account on ieng6

## Installing VSCode
* The first step is to download Visual Studio Code. 
* When VSCode is first opened, it should look like the image below.

![Screenshot](https://user-images.githubusercontent.com/114367462/193203794-2ab46a33-d12b-4e34-9cfe-aa65315559ef.png)

## Remotely Connecting
* The next step is to install OpenSSH which is only a step necessary for Windows users. (Open SSH is already on Mac)
* Next, type the command ssh cs15lfa22fx@ieng6.ucsd.edu with the 'fx' replaced. Type yes when prompted and enter your password.

![Screenshot](https://user-images.githubusercontent.com/114367462/193339658-55361de6-42c5-42bc-b219-d278e2bd5d05.png)

## Trying some commands
* After logging into the secure shell, you can try running commands such as cd, mkdir, ls, etc
* Below is the result of running the command ls -a which results in all of the files being shown.

![Screenshot](https://user-images.githubusercontent.com/114367462/193339681-ab801f01-08de-4406-b421-8aba412db95e.png)

## Moving files with scp
* Create a file called WhereAmI.java and save it to your computer
* As of right now, if you run ls inside the secure shell you will not see this new file. To copy it from your client to the shell, use the command scp WhereAmI.java cs15lfa22fx@ieng6.ucsd.edu:~/ with the "fx" replaced. 
* Now running ls, you will see the WhereAmI.java file in the shell and can run it.

![Screenshot](https://user-images.githubusercontent.com/114367462/193338679-8c795278-4e69-4b70-ba71-48cb476fb7c2.png)

## Setting an SSH key
* Type the command ssh-keygen and return multiple times in order to take the default path.
* In order to complete the process, type the following commands: ssh cs15lfa22fx@ieng6.ucsd.edu, mkdir .ssh, scp /Users/dhruv/.ssh/id_rsa.pub cs15lfa22@ieng6.ucsd.edu:~/.ssh/authorized_keys and replace your username
* Now you will no longer have to type your password repeatedly while using the ssh and scp commands 

![Screenshot](https://user-images.githubusercontent.com/114367462/193339159-ceb82491-5a75-45a9-8d7c-10d6647de357.png)
![Screenshot](https://user-images.githubusercontent.com/114367462/194993843-357c9792-f5a8-4bff-91cf-b9cae1234337.png)


## Optimizing Remote Running
* Finally, you can optimizing remote running further by typing a command along with the ssh command. 
* An example of the ssh command with the ls command is shown below. When the secure shell opens, results of the ls command will automatically generate. 

![Screenshot](https://user-images.githubusercontent.com/114367462/193338970-2b5b337f-2d28-4c51-b097-8ceec04fbcef.png)

