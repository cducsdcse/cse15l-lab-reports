# Charlotte Dong Lab Report2 (Week1)  
  
**Step 1 Installing VSCode**  
Download Visual Studio Code from the [official website](https://code.visualstudio.com/download). Open it, you should see a window like the screenshot below.  
  
![Image](lab1-screenshots/lab1-openvscode.png)  
  
    
**Step 2 Remotely Connecting**  
Ssh into your course-specific account using command: *$ ssh cs15lfa22ji@ieng.ucsd.edu*. If you see the successful login message as below, your computer (client) is connected to the server in the CSE basement.  
  
![Image](lab1-screenshots/lab1-step2.png)  
  

    
**Step 3 Trying Commands**  
Try running some commands on the server and on your personal computer. As it is shown below, the terminal on the left should be similar to the command tryout using the server; the terminal on the right should be similar to the tryout using your personal computer. All commands were ran successfully using the server; while the one using my computer received “no such file or directory” for *ls /home/linux/ieng6/cs15lfa22/cs15lfa22ji*, *cp /home/linux/ieng6/cs15lfa22/public/hello.txt ~/* , *cat /home/linux/ieng6/cs15lfa22/public/hello.txt*. This is because the directory or file is remote and is not on my personal computer.  
   
![Image](lab1-screenshots/lab1-step3.png)  
  


**Step 4 Moving Files with scp**  
The code should work the same both local and remote, but the printed out results are different. When I run this on the client, my local system name, username and directory gets print out; but when I run this on the server, the remote system name, username and directory gets print out.  
  
![Image](lab1-screenshots/lab1-step4.png) 
  


**Step 5 Setting an SSH Key**
The first screenshot below is the setup process for an ssh key. Once its setup, you should be able to log in without password.  
  
![Image](lab1-screenshots/lab1-step5-1.png)  
  
After completing the above steps, you could login to your account without password, and the process should be similar to mine in the screenshot below.  
  
![Image](lab1-screenshots/lab1-step5-2.png)
  


**Step 6 Optimizing Remote Running**  
Below are two efficient commands. A third efficient command is to use the up-arrow to pull up the last command that was run.  
  
![Image](lab1-screenshots/lab1-step6.png)  
