
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

The first part at the start contains the admin server configurations, We have the admin server listen URL “127.0.0.1:333” and the SSL certificates and key. When running gophish on a VPS and want admin server to be accessible via the internet, this should be changed to “0.0.0.0:3333”.


