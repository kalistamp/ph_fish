
### Getting a Domain:

A domain name needs to be convincing and similar enough to the domain of the legitimate website. One can use [urlcrazy](https://github.com/urbanadventurer/urlcrazy) or [catphish](https://github.com/ring0lab/catphish) to generate a list of typo domains.

After running URLCRAZY you will see a Full list of all Typo Domains that were discovered. The domains with the question-mark are ones we can choose from... The rest are in use and not available. 

URLCRAZY Setup:

``` 
git clone https://github.com/urbanadventurer/urlcrazy.git
cd urlcrazy
sudo -s
gem install bundler
bundle install
urlcrazy therecap.org
```

***

Another option is to obtain a free domain from [Freenom](https://www.freenom.com/en/index.html?lang=en) which offers free Top Level Domains (TLD) that are available ...


***

Search Expired Domains for a now available, high reputation domain. ExpireDomains is in essence a garbage bin that shows you how much value a discarded domain has... a wonderful resource to the adversaries: 
https://www.expireddomains.net/

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




