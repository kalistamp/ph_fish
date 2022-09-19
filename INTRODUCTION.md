
### Phishing Basics:

The basic idea behind phishing is to create a copy of a login page (Scam Page) or whole website and allow user to login so that you can obtain the account credentials. 


[ex.] an attacker creates a copy of gmail page, which exactly looks similar to the original, but coded in a way that it will store credentials whenever someone tries to login through that page. Now the attacker will share the link of his phising page somehow (through mails, messages, web links, etc.) and attacker has all the credentials of all the users who tried to login through phishing page.

* * *

### Types of Phishing:

* Spear Phishing - 

Spear-phishing, as with throwing a physical spear; you’d have a target to aim at, the same can be said with spear-phishing in that you’re targeting an individual, business or organisation rather than just anybody as mass. This is an effective form of phishing for a red team engagement as they are bespoke to the target it makes them hard to detect by technology such as spam filters, antivirus and firewalls.

* Whale Phishing
* Smishing (SMS)

* * *

### Set-Up:

Three  things to work with regarding phishing emails - ```Sender’s email address``` | ```the subject``` | and ```the content```

How email travels from the sender to the recipient ---> [Reference Image ](https://assets.tryhackme.com/additional/phishing1/email-network-flow-4.png)

* ```The Senders Address:```

(  Run your email through a spam filter first, It is very easy to detect phishing or spamming context, Big mail providers like gmail often have pretty good filters, target companies - Use good SMTP ) ``` SMTP Port 465 ``` | ``` IMAP Port 993 ``` | ``` Pop3 Port 995 ```

Sending a Trusted source that the victim will feel comfortable clicking on is important,
Ideally, the sender’s address would be from a domain name that spoofs a significant brand, a known contact, or a coworker.

To find what brands or people a victim interacts with, you can employ OSINT (Open Source Intelligence) tactics. For example:

Observe their social media account for any brands or friends they talk to. Searching Google for the victim’s name and rough location for any reviews the victim may have left about local businesses or brands. Looking at the victim’s business website to find suppliers. Looking at LinkedIn to find coworkers of the victim.

* ```The Subject:```

You should set the subject to something quite urgent, worrying, or piques the victim’s curiosity, so they do not ignore it and act on it quickly.

[ex.] Your account has been compromised.
Your package has been dispatched/shipped.
Staff payroll information (do not forward!)
Your photos have been published.

* ```The Content:```

If impersonating a brand or supplier, it would be pertinent to research their standard email templates and branding (style, logo’s images, signoffs etc.) and make your content look the same as theirs, so the victim doesn’t expect anything. If impersonating a contact or coworker, it could be beneficial to contact them; first, they may have some branding in their template, have a particular email signature or even something small such as how they refer to themselves, for example, someone might have the name Dorothy and their email is [email protected]. Still, in their signature, it might say “Best Regards, Dot”. Learning these somewhat small things can sometimes have quite dramatic psychological effects on the victim and convince them more to open and act on the email.

If you’ve set up a spoof website to harvest data or distribute malware, the links to this should be disguised using the anchor text and changing it either to some text which says “Click Here” or changing it to a correct looking link that reflects the business you are spoofing, for example:


* * *

### Infrastructure:

A certain amount of infrastructure will need to be put in place to launch a successful phishing campaign.

* Domain Name:

You’ll need to register either an authentic-looking domain name or one that mimics the identity of another domain. Look into tools such as [go_phish](https://github.com/gophish/gophish) on how to create a domain name.

* SSL/TLS Certificates:

Creating SSL/TLS certificates for your chosen domain name will add an extra layer of authenticity to the attack.

* Email Server/Account:

You’ll need to either set up an email server or register with an SMTP email provider.

* DNS Records:

Setting up DNS Records such as SPF, DKIM, DMARC will improve the deliverability of your emails and make sure they’re getting into the inbox rather than the spam folder.

``` [NOTE] ``` Web Server - You’ll need to set up webservers or purchase web hosting from a company to host your phishing websites. Adding SSL/TLS to the websites will give them an extra layer of authenticity.

Summary: DNS has TXT records that can improve email deliverability ...

* ``` EXTRA ``` Analytics:

When a phishing campaign is part of a red team engagement, keeping analytics information is more important. You’ll need something to keep track of the emails that have been sent, opened or clicked. You’ll also need to combine it with information from your phishing websites for which users have supplied personal information or downloaded software.

* * *

### Automation Tools:

Some of the above infrastructures (DOMAIN | SSL | SMTP | DNS RECORDS) can be quickly automated by using the below tools.

* GoPhish
* SET (Social Engineering Toolkit)
* [King-phisher](https://github.com/rsmusllp/king-phisher)
* Evilginx
* Modlishka

* * *
Once the Above Infrastructure is set up you will need to have your ```Landing Page``` Source code ready for whatever site you plan on mimicking- (This is the website that the Phishing email is going to direct the victim to; this page is usually a spoof of a website the victim is familiar with.)

* * *

### Droppers:

Droppers are software that phishing victims tend to be tricked into downloading and running on their system. The dropper may advertise itself as something useful or legitimate such as a codec to view a certain video or software to open a specific file.

The droppers are not usually malicious themselves, so they tend to pass antivirus checks. Once installed, the intended malware is either unpacked or downloaded from a server and installed onto the victim’s computer. The malicious software usually connects back to the attacker’s infrastructure. The attacker can take control of the victim’s computer, which can further explore and exploit the local network.



***

* [SOURCE](https://classroom.anir0y.in/post/tryhackme-phishingyl/#task-03-writing-convincing-phishing-emails)
* [hOMEPAGE](https://classroom.anir0y.in/categories/tryhackme/)
