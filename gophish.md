

### Installation on Host:

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

## Installation on Cloud:

* SSH into the EC2 instance that you have created...
* To make sure all of our programs run correctly we are going to update all the packages on our instance:
```sudo apt-get update``` | ```sudo apt-get upgrade```

* Install golang:
```sudo apt-get install golang```

NOTE: I recieved the error: go: go.mod file not found in current directory or any parent directory

Solution: go env -w GO111MODULE=auto (source: https://stackoverflow.com/questions/67929883/go-error-go-go-mod-file-not-found-in-current-directory-or-any-parent-director)
            
* Install gophish:
```go get github.com/gophish/gophish```

```cd go | cd src | cd github.com | cd gophish --> [ /home/ubuntu/go/src/github.com/gophish/gophish ]```

* Next we are going to build gophish program using go: ( run ls to make sure the gophish.go file is present in the directory )
```go build``` ( Once gophish is done build you can type ls again to confirm the new gophish file is created and present )

* Next we are going to edit the config.json file, you can use nano or vim to do this:

``nano``` into the config.json file 
We are going ot change the "listen_url" from 127 to ```0.0.0.0:3333``` so that gophish admin panel can be accessed from any ip (Note that the port being used is still 3333)

Save and exit nano

* Now that gophish is fully installed and configed it is time to run the program inside opf our EC2 instance:

```sudo ./gophish```
admin
password
            
Error: ```" bind: address already in use "```

Solution: ```sudo fuser -k 80/tcp``` [Source](https://github.com/gophish/gophish/issues/709)


***

### Modification setup

In the file config.go there is a Server variable set to “gophish” out of the box. So what is the best way to change this? We don’t want to spoof any mail client or server because it might tip our hand (Trust me on this!). So instead, let’s opt to set the value to IGNORE.

[From] ```const ServerName = "gophish"```

[To] ```const ServerName = "IGNORE"```

There are numerous blogs and articles on how to setup and configure Gophish and the assets. In the following steps we will summarize some of these activities that will help us to launch our phishing campaign properly (i.e. not falling flat on your face and getting caught by spamfilters of internet proxies).

***

## Setup:

* Campaign:

Here on this Tab you will be able to see all the statistics from your phishing campaign such as who clicked your email, who submitted credentials, and more things like that ... You can not start a Campaign untill all Tabs Below are completed 

***

* User & Groups:

This is were you will input who you plan on sending your emails out too. You can manually enter the victims name and email address or you can go ahead and just import a CSV file List that you can aquired 


***

* Email Template:

This is where you will enter the HTML code which will determine how your email will be displayed ( See reference below ) 

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

* Landing page:

The landing page is what you want users to “land” on once they click on the link in the email. 

Instead of working with Gophish for this part of the campaign we are going to instead use another tool ```evilginx2``` to create our own custom landing page.

NOTE: If you would like to test a simpilar phish and do not want to set up evilginx2, you can come here in this tab on Gophish and Capture Passwords 



***

* Sending Profile:

This is referring to who the email is going to be coming from, This could be something like ``I.T. Administrator```, or `company support```, or anyone who you choose to impersonate.

Whatever you choose, this identity is being spoofed by whatever domain we just obtained earlier
