
https://github.com/gophish/gophish/issues/2590

https://www.slideshare.net/ijtsrd/comparative-analysis-of-phishing-tools

U admin panel .. how do i get it ??

https://fr3d.hk/blog/u-admin-show-tell

read this over for phishing site analysis

https://blog.group-ib.com/0ktapus
* * * 

What or where is the best way to anon obtain a cheap domain to set up phish campaign ?

Bro I never paid for domains for phishing, When I use phishing attack i use my host and generated link in ngrok then I just masked with PhishMask tool and sending emails.

https://tld-list.com/ - porkbun domain 

namecheap accepts btc


*  freenom has an API For companies that will automatically disable any free domains at a single API request made by them -- 

Another reply :

you don't need a domain to do phishing i have a site that can help you,

>>>  here the link : https://nomorz.com/index.php? 

https://www.facebook.com/people/Anomor-website/100084228355578/

***

Threat actors are getting better at slipping phishing attacks through the weak spots in platform email defenses, using a variety of techniques, such as zero-point font obfuscation, hiding behind cloud-messaging services, and delaying payload activation, for instance. They're also doing more targeting and research on victims.

The actors investigate their victims using open source intelligence to obtain lots of information about their victim [and] craft very realistic phishing emails to get them to click a URL, open an attachment, or simply do what the email tells them to do, like in the case of business e-mail compromise (BEC) attacks," he says.

The data suggests that attackers are also getting better at analyzing defensive technologies and determining their limitations. To get around systems that detect malicious URLs, for example, cybercriminals are increasingly using dynamic websites that may appear legitimate when an email is sent at 2 a.m., for example, but will present a different site at 8 a.m., when the worker opens the message.

OneDrive, Google Drive, Teams, Share Point, Slack, Box,

Instead of scanning every url that is received, security companies are using “time of click analysis” because only 1% of malicious urls are actually clicked 


***

### NOTES:

* How i ssh into my aws server (instance ?) with the downloaded pem key :

```  ssh -i /home/kali/Desktop/gophish.pem ubuntu@44.201.169.181 ```

* Fix Error !!! ---> 

time="2022-09-27T04:31:18Z" level=warning msg="No contact address has been configured."
time="2022-09-27T04:31:18Z" level=warning msg="Please consider adding a contact_address entry in your config.json"
goose: no migrations to run. current version: 20220321133237
time="2022-09-27T04:31:18Z" level=info msg="Starting admin server at https://0.0.0.0:3333"
time="2022-09-27T04:31:18Z" level=fatal msg="listen tcp 0.0.0.0:3333: 

bind: address already in use"

SOLUTION: 

The 'already in use' error means that another process is already listening on port 3333. You might have another instance of gophish running. You can run this command to see what's on that port:

``` sudo netstat -ltnp | grep -w ':3333' ```

Source: https://github.com/gophish/gophish/issues/2234


***


### Copy & Pastes :

Forum replys on phishing -

phishing with reverse proxies is alright | modlishka / evilnginx 


QUESTIONS :


Q:

I've been phishing for quite some time now and have nearly 100k emails either scraped or taken from fresh databases as well as multiple realistic website clones. Everything has been smooth-sailing until like a week ago when despite me sending the email to 5k people, i got like 2 results. this was when i found out that every single one of my emails are going to the recipients spam. I've made multiple different emails, used  a vpn, proxies, virtual machines and different mail providers but despite all that every single email that has more than 30 recipients is going to spam.. whats the issue??

A:

* one advice : target new areas/countries, less targeted.

* I recommend that you only target a specific country on each email and add a few seconds delay for each delivery. Don't send too many emails should be limited but i think you need many SMTP for send it LoL

* Run your email through a spam filter first, It is very easy to detect phishing or spamming context.

you will need to change the content.

* Big mail providers like gmail often have pretty good filters, target companies

* filter by domain (gmail,yahoo,hotmail) and then filter by country. use good smtp



* * * 

### Turn any page into a phishing page(Advance)

This just simply explains how to turn(clone) any page and make it look exactly the same and injecting a malicious code not the full phishing guide you expect. Not for beginners but still useful.

Requirements:
CSS & JS Programming

Steps:

1. Install this browser extension. https://chrome.google.com/webstore/detail/save-page-we/dhhpefjklgkmgeafimnjhojgjamoafof

2. Clone the target page using the extension.

3. Make a JS file with a function called "login" in the html directory then require it in the index html file.

4. Get all the inputs selector in the html and in the button add the property onlick with the login function.

3. Inject malicious code to the login(Send to webhook & etc using fetch API) function then host the files in Repl in an account with gibberish name also make the project title gibberish, buy a domain then apply the domain in the REPL project.





Lastly I recommend you to obfuscate the js file using obfuscator.io


* * *

* When u have generated link, just mask URL (example Phishmask tool) and send

https://nomorz.com/

* * *

### Hosting:

This is a Free hosting list to help you Host a static site
it can be used to Host a simple site or just for developing your script

- https://www.infinityfree.net/ (my favorite)
- https://www.wix.com/ (good for your small business)
- https://000webhost.com/ (good one for developing a static site)
- https://cloud.google.com/solutions/web-hosting (can use trial, but need payment card)
- https://www.awardspace.com/ (very good for students to learn about web dev)
- https://www.freehostia.com/ (limited fiture)
- https://www.freehosting.com/ (i never try this before)
- https://byet.host/ (slow server at some country)


