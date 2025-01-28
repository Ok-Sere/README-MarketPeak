# MarketPeak E-commerce Website
>The aim of this project is to develop an e-commerce website for an online marketplace. The platform will feature product listings, a shopping cart, and user authentiction. 

>Git will be utilized for version control, the platform will be developed in a linux environment, and deployed on an AWS EC2 instance.

## Step 1.1

We began by creating a project directory names *MarketPeak_Ecommerce*. Inside the directory a git repository was initialized using command `git init`, this took me to the *master* branch of my repository.

![step 1](./img/1.%20git%20init.png)

## Step 1.2
A pre-exisiting website template was obtained for this project, this approach allows us to focus on the deployment and operational aspects, rather than webb development.

## Step 1.3

The downloaded website files were added to the git repository using command `git add .` and the changes were commited using command `git commit -m "message"`.

![step 1.3](./img/3.%20stage%20and%20commit.png)

## Step 1.4

After initializing the it repository and adding the e-commerce website template, the code was pushed to a remote repository on GitHub named **MarketPeak_Ecommerce**. The remote repository URL was added to the local repository configuration and the pushed to Github.

![step 1.4](./img/4.%20push%20code%20to%20github.png)

>Error : When pushing the code to github, as error was made. `git push -u origin main` was used. thi resukted to an error. 

>Correction: To correct this main was chnaged to master in the command, that is : `git push -u origin master`.

## Step 2.1
In the second stage of this project, an AWS EC2 Instance was launched using an Amazon Linux AMI.
The EC2 instance was connected to the terminal using SSH.

To achieve this, firstly the key.pem was downloaded and executed in the download directory.

![step 2](./img/5.%20downloaded%20pem%20key.png)

After which command `chmod 400 "MarketPeak_key.pem"` was used to set file permission before connecting with ssh.

![step 1](./img/7.1.%20connected%20ec2%20to%20terminal%20successfully.PNG)


## Step 2.2
Before deploying the e-commerce platform, we need to clone the GitHub repository to the AWS EC2 instance. SSH key pair was generated using `ssh-keygen`. 

![step 1](./img/8.%20generate%20ssh%20keypair%20using%20keygen.png)

A public key was generated, copied and added to the GitHub account.

![step 1](./img/9.%20display%20and%20copy%20puplic%20key.png)

![step 1](./img/10.%20Add%20ssh%20public%20key%20to%20your%20github.png)

The SSH clone URL was used to cone the repository.

![step 1](./img/11.%20git%20clone%20error%20and%20correction.png)

>Error: the `git clone` command did not work, this was because the git command has not been installed on the virtual computer (EC2).

>Correction: `sudo yum update -y` was used to update all the installed packages on the system to their latest versions without asking for confirmation. `sudo yum install git -y` was used to install Git on systems.

Then the SSH clone URL was used to clone the repository.

![step 1](./img/12.%20git%20cloned.png)


## Step 2.3
To be able to host the *MarketPeak E-commerce* site, we need to install **Apache HTTP Server** on Linux EC2, start and enable.

![step 1](./img//13.%20sudo%20yum%20update%20and%20install.png)

![step 1](./img/14.%20sudeo%20systemctl%20start%20&%20enable.png)


## Step 2.4
To be able to serve the website from EC2 instance, we will need to configure **httpd** to point to the directory on the linux server where the website code filrs are stored.

We begin by clearing the default httpd web directory and Marketpeak Ecommerce webite file to it. Then reload.

![step 1](./img/15.%20configure%20httpd%20for%20website.png)

## Step 2.5
To be able to open *MarketPeak Ecommerce* platform online, we will need to add a HTTP port 80 on our EC2 security group. After which we can open a web brower and access the public IP of the EC2 instance to view the deployed website.

![step 1](./img/16.%20access%20website%20from%20browser.png)