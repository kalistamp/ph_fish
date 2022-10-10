
### Options for getting a Domain:

* [Freenom](https://www.freenom.com/en/index.html?lang=en)
* AWS Route 53
* https://www.domnest.com/tld/sh
* https://tld-list.com/
* Search Expired Domains for a now available, high reputation domain. ExpireDomains is in essence a garbage bin that shows you how much value a discarded domain has... a wonderful resource to the adversaries: 
https://www.expireddomains.net/
* [catphish](https://github.com/ring0lab/catphish)
* [urlcrazy](https://github.com/urbanadventurer/urlcrazy)

URLCRAZY Setup:

``` 
git clone https://github.com/urbanadventurer/urlcrazy.git
cd urlcrazy
sudo -s
gem install bundler
bundle install
urlcrazy therecap.org
```
* After running URLCRAZY you will see a Full list of all Typo Domains that were discovered. The domains with the question-mark are ones we can choose from... The rest are in use and not available. 

***

### Choosing A Phishing Domain:

[ Expired/OLD Domains are better than new ones to avoid spam folder ] 

Choosing the right Phishing domain to launch your attack from is essential to ensure you have the psychological edge over your target. A red team engagement can use some of the below methods for choosing the perfect domain name.

Expired Domains:

Although not essential, buying a domain name with some history may lead to better scoring of your domain when it comes to spam filters. Spam filters have a tendency to not trust brand new domain names compared to ones with some history

Typosquatting:

Typosquatting is when a registered domain looks very similar to the target domain you’re trying to impersonate. Here are some of the common methods:

Misspelling: goggle.com Vs google.com
Additional Period: go.ogle.com Vs google.com
Switching numbers for letters: g00gle.com Vs google.com
Phrasing: googles.com Vs google.com
Additional Word: googleresults.com Vs google.com
These changes might look unrealistic, but at a glance, the human brain tends to fill in the blanks and see what it wants to see, i.e. the correct domain name.

TLD Alternatives:

A TLD (Top Level Domain) is the .com .net .co.uk .org .gov e.t.c part of a domain name, there are 100’s of variants of TLD’s now. A common trick for choosing a domain would be to use the same name but with a different TLD. For example, register reddit.co.uk to impersonate reddit.com

* IDN Homograph Attack/Script Spoofing:

Originally domain names were made up of Latin characters a-z and 0-9, but in 1998, IDN (internationalized domain name) was implemented to support language-specific script or alphabet from other languages such as Arabic, Chinese, Cyrillic, Hebrew and more. An issue that arises from the IDN implementation is that different letters from different languages can actually appear identical. For example, Unicode character U+0430 (Cyrillic small letter a) looks identical to Unicode character U+0061 (Latin small letter a) used in English, enabling attackers to register a domain name that looks almost identical to another.

(Read on IDN Attacks) - https://dobby1kenobi.medium.com/lost-in-translation-222bbf00f2c

https://altcodeunicode.com/

***

### Checking Domain Categorization: 

Website categorization, refers to the process of classifying websites based on their content and places what is a countless number of websites into a distributed number of categories under different umbrellas for marketing, cybersecurity, and brand protection purposes, in order to prevent insider threat risks.

Well-known categorization sites are listed below:

https://www.fortiguard.com/iprep
https://sitereview.bluecoat.com/#/
https://talosintelligence.com/
https://urlcat.checkpoint.com/urlcat/main.htm
https://urlfiltering.paloaltonetworks.com/
https://global.sitesafety.trendmicro.com/
https://www.brightcloud.com/tools/url-ip-lookup.php
https://archive.lightspeedsystems.com/
https://multirbl.valli.org/
https://mxtoolbox.com/blacklists.aspx

***

### Authenticate your Domain:

What is Domain Authentication ?

Domain authentication, formerly known as domain whitelabel, shows email providers that SMTP providers (such as SendGrid in this example) has your permission to send emails on your behalf. To give SendGrid permission, we need to point DNS entries from your DNS provider (like GoDaddy, Cloudflare, etc) to SendGrid. By doing that our recipients will no longer see the "via sendgrid.net" message on our phished emails.

Email service providers do not trust messages that have not set up domain authentication because they cannot be sure of the legitimacy of the message. Explicitly stating that it comes from our registered domain increases the reputation with email service providers which makes it much less likely that they will filter the mail and not allow it get to the recipient's inbox, which increases the deliverability.

Login to your SendGrid account and navigate at Sender Authentication under Settings:
1. Click on the "Authenticate Your Domain" under Domain Authentication section.
2. Select your Domain provided under DNS host option and specify Yes under the question "Would you also like to brand the links for this domain?"
3. Enter your domain and expand the Advanced Settings option. From the Advanced Settings checkbox and apply the following values accordingly:

- Use custom link subdomain
- Use a common DKIM selector 



