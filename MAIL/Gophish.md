
### GOPHISH Infrasctrucure Tool:

WATCH OVER MY STREAM AND DOCUMENT HOW TO CORRECTLY INSTALL GOPHISH INTO KALI LINUX:

***

THIS IS MY OWN ATTEMPT OT DOWNLOAD GOPHISH ON KALI RIGHT NOW _ _ 

* Install gophish by downloading the binary for your system from the most current release available: [RELEASE](https://github.com/gophish/gophish/releases/)

```
unzip  gophish-v0.11.0.zip 
cd into path to your destination folder
chmod +x gophish
```
* Configure the ```config.json``` file

Reviewing the json file:

The first part at the start contains the admin server configurations, We have the admin server listen URL ```127.0.0.1:333``` and the SSL certificates and key. When running gophish on a VPS and want admin server to be accessible via the internet, this should be changed to ```0.0.0.0:3333```

After the Config.json file is configured correctly you can now run the binary:

```sudo ./gophish```

[ You should run gophish in the same tmux session as evilginx2 ]

Your temporary credentials for the GoPhish Admin Panel will be printed in the logs from the running gophish binary.

***

### Setting up an email Template in GoPhish:

We set up and configure the email which shall be received by the victim here. To make a convincing email template, go through your own inbox and try to find an existing email from the website you’re trying to spoof. 

As an example, you can use a Password-Reset Confirmation Email which was received from LinkedIn.

* Click on the three-dot options button and Download the Email you want to use as a template.
* Open the file and copy its contents.
* Now navigate to Email Templates tab and create a new template. 
* Click on Import Email and paste the copied contents.
* (CHECK THIS TO BETTER UNDERSTAND) - Optionally, check the Change Links to Point to Landing Page checkbox. This will change all the links in the mail to point to the spoofed landing page.

Now, in the HTML tab, modify the contents to your own liking - (Crafting a convincing email is very important, so if you’re doing this for an assessment, take your time to craft a phishing email.)

(READ THIS SECTION OVER AGAIN FROM SOURCE)

*** 

### Setting up the Landing Page in GoPhish:

The landing page is what you want users to “land” on once they click on the link in the email. Once in the GoPhish admin panel, navigate to Landing Pages and create a new page. Give it a page name and for the page content, add the following.

( CHECK OVER THIS WHOLE FILE BRIEFLY AND FIGURE IT OUT - - -)
