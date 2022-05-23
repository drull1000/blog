+++
title = "Full OSINT Guide"
date = "2022-05-23T10:13:24-03:00"
author = "Drull"
authorTwitter = "drull1000"
cover = "./assets/osintCover.jpg"
tags = ["OSINT", "Cybersecurity", "Hacking"]
keywords =["OSINT", "Cybersecurity", "Hacking"]
description = "A collection of everything I have learned about OSINT from various resources."
showFullContent = false
readingTime = true
hideComments = true 
+++

# How to do OSINT - A brief introduction.

This is a collection of everything I have learned about OSINT from various resources over the internet. Be aware that some of the tools presented here may change or stop working with time, which is normal. The most important thing you should get out of this is **to learn the methods used and be able to replicate them.**

The goal of this guide is to show the path one should follow when doing research on a target. The guide is divided in different sections covering a wide range of topics. Each one of them has their own tools that I recommend and use.

This page will be updated with time as I find new resources and new tools. Happy hacking.

## What is OSINT?

Open-source intelligence is the collection and analysis of data gathered from open sources (overt and publicly available sources) to produce actionable intelligence. OSINT is primarily used in national security, law enforcement, and business intelligence functions and is of value to analysts who use non-sensitive intelligence in answering classified unclassified, or proprietary intelligence requirements across the previous intelligence disciplines. [Read more.](https://en.wikipedia.org/wiki/Open-source_intelligence)

**OSINT is the first phase of hacking.**

## Keeping your data safe

Before starting, it is important to make sure that your data is secure and that you won't reveal your true identity. Ideally, we are not going to interact directly with our target, but it is always essential to stay secure.

### Password managers

You want to keep the information you are collecting **as private as possible.** In order to do that, it is essential to use a password manager like [Bitwarden.](https://bitwarden.com)

Other tips:

- Generate a strong password and use it for only one account.
- Enable 2FA.
- Don't save passwords in browsers.
- Never answer online security questions truthfully, since those are vulnerable to social engineering.
- Avoid using SMS for 2FA.
- Consider unique usernames.

### ️Secure email

Another significant step is to use a secure email provider that offers encryption, such as [Protonmail.](https://protonmail.com)

Other tips:

- Keep your email address private
- Disable automatic loading of remote content
- Don't share sensitive data via email. You can use [onionshare](https://onionshare.org) to share sensitive files.
- Use aliasing/anonymous forwarding (ex: [SimpleLogin](https://simplelogin.io/?slref=bridsqrgvrnavso))

### Encryption

Before backing up your data in the cloud, it is encouraged to encrypt it. For that, you can use [Cryptomator.](https://cryptomator.org)

### Sock Puppets

A sock puppet is a fake identity you assume on the internet so that you don't give out your real data. **This should never link back to your true identity.** Sock puppets should look real and be active online to look more legitimate.

**You must generate a fake profile and add fake data to it.** This data should be the same across all the sock puppets' accounts. Remember: women are better at social engineering. Don't use other people's photos, because that could be easily reverse searched. You can use something like [this person does not exist](https://thispersondoesnotexist.com).

- If it is affordable to you, you should use burner phones and computers to manage the accounts.
- Use a VPN instead of your real IP address.

## Searches

Now it's time to talk about search engines and how to better utilize them. When we are searching for something on Google, for example, it is very common to find a bunch of irrelevant and messy results. When we are doing an OSINT investigation, it is important to filter the good results from the bad ones. That's why we use something called search operators.

### Search operators

There are a number of commands you can use to refine your search results.

- Results about cats or dogs

  `cats dogs`

- Results for exact term "cats and dogs". If no results are found, related results will be shown.

  `"cats and dogs"`

- Fewer dogs in results

  `cats -dogs`

- Find subdomains of dogs.com

  `site:dogs.com -www`

- More dogs in results

  `cats +dogs`

- PDFs about cats. Supported file types: pdf, doc(x), xls(x), ppt(x), html

  `cats filetype:pdf`

- Pages about dogs from example.com

  `dogs site:example.com`

- Pages about cats, excluding example.com

  `cats -site:example.com`

- Page title includes the word "dogs"

  `intitle:dogs`

- Page text includes the word "dogs"

  `intext:dogs`

- Page url includes the word "cats"

  `inurl:cats`

- Pages that include the cached pages for dogs.com

  `cache: dogs.com`

- Pages include the word "cats" and "dogs"

  `cats AND dogs`

- Pages include the word "cats" OR "dogs"

  `cats OR dogs`

- Pages that include the phrase "cats [something] dogs"

  `cats * dogs`
  
Bonus:  
[Google alerts](https://google.com/alerts) can alert you of new search results for what you are looking for.

### For people

If you are looking for a specific person, a good way to start is to look for the person's name on a search engine. If you want something more specific, you can go over to [whitepages](https://whitepages.com) or [truepeoplesearch](https://truepeoplesearch.com), although these websites are more focused on the USA.

- If you want to pull out voting records of people, you can use something like [Voterrecords](https://voterrecords.com)

Other options:

- [fastpeoplesearch](https://fastpeopesearch.com)
- [fastbackgroundcheck](https://fastbackgroundcheck.com)
- [webmii](https://webmii.com)
- [thatsthem](https://thatsthem.com)
- [xlek](https://xlek.com) aka cubib
- [backmetodos](https://t.me/Blackmetodos)

### For businesses

If you are doing OSINT on a business, the first place to look at is their website and social media, specially LinkedIn.

- Check for company directory in the URL, news, forums, phone numbers, employees, and their positions, photos and what is contained in them

- If you look for photos you might be able to get some data from your target, such as sticky notes, operating systems and metadata.

- Look for the company name in a government website that can give you some legal data, such as directors, CEOs and other names.

- Look for complaints and reviews.

- [OpenCorporates](https://opencorporates.com) has information on companies and officers.

- [indeed](https://indeed.com) is useful to see what skills employees need to work in a specific company.

### For websites

Some data you can extract from websites are: technologies used, IP addresses, who is hosting it, subdomains, etc…

- [CentralOps](https://centralops.net/co/) can be used to find **a lot of information** about the host. It is possible to find sensitive information on who is hosting the website.

- [dnslytics](https://dnslytics.com/reverse-ip) Reverse IP search. If someone hosts their own server, you can use it to find other registered websites.

- If you want to check for website changes, you can use [changetower](https://changetower.com)

- [ahrefs](https://ahrefs.com/backlink-checker) is a website that allows you to look for backlinks

- Shodan can also be used to look for vulnerabilities, if you have an IP address.

- Some websites might have some subdomains online that shouldn't be available to the public. You can use search operators to look for some subdomains like “dev”, “forums”, “admin”, "adm", "VPN" by subtracting www and adding inurl: URL. You can use sublist3r, OWASP Amass and [crt.sh](https://crt.sh) to list subdomains of a website

- [Wayback](https://web.archive.org) machine can show you old versions of the website.

- On Google, you can open the cached website by clicking on the arrow next to the link.

- [BuiltWith](https://builtwith.com/) to find the technologies used.

Other options:

- [domaintools](https://whois.domaintools.com)
- [viewdns.info](https://viewdns.info/) a lot of useful tools to analyze websites
- subfinder, assetfinder for finding subdomains. CLI.
- Gowitness: CLI tool for taking screenshots of domains

### For phone numbers

For searching phone numbers, you can first look for them on Google and see what comes out. If you don't get interesting results, try searching with hifens, area codes or even spell the numbers. Play with the syntax. Even a phone emoji 📱 can be useful.

- If google or any other search engine does not work, the websites used for searching people can also be used for phone numbers.

- If you have the person's email, you can test if they have a phone number associated with the account by going to reset password.

Other options:

- [Truecaller](https://truecaller.com)
- Phoneinfoga

### For birthdates

If you want to look for someone's birthday, try looking for that on Google and use search operators. Twitter is a great place to look at.

### For resumes

Google and other search engines can easily help you find resumes. Try looking for images and PDFs. You can also look for the person's name on LinkedIn.

- You can combine search operators to look for them in places like google, Dropbox, scribd.

Other options:

- [indeed](https://indeed.com)
- [search resumes free](https://jobvertise.com)

### For IoT and connected devices

You can find vulnerable IoT devices on [shodan.io](https://shodan.io) and find IP addresses, location, open vulnerable ports (such as 3389) and more.

- [wigle.net](https://wigle.net) is a map of wireless networks.

### For aircraft

Most aircraft can be tracked down due to the unencrypted data transmitted. Every aircraft has a unique serial number and there are websites capable of tracking them, such as [radarbox](https://radarbox.com)

- You can copy the plane number and look for more info about it on [aviationdb](https://aviationdb.net)

- You can also listen to the conversation between the pilots and the control tower on [liveatc.net](https://liveatc.net)

Other options:

- [flightradar](https://flightradar24.com)

## Social media

Social media can be a goldmine for OSINT researchers. It is incredible the amount of data someone can get from a specific person just by looking at their profile. When analyzing someone's profile, try to look for everything you can. Photos, relatives, workplace, check-ins, friends, interests, etc…

### Twitter

Tweets from a person can be very revealing, and usually people put everything about their lives online.

For Twitter OSINT, there are tools that can help you with your investigation, but you should start playing with the search bar. Twitter has search operators that can be used to narrow down the results.

Besides the standard search operators, Twitter has some specific ones, such as:

- Sent from the NASA account

`from:nasa`

- Replying to NASA

`to:nasa`

- Mentioning NASA

`@nasa`

You can even look for geocodes with a km range. All you need is the latitude and longitude.

A full list can be found [here](https://developer.twitter.com/en/docs/twitter-api/v1/rules-and-filtering/search-operators)

Other options:

- [socialbearing](https://socialbearing.com)
- [twitonomy](https://twitonomy.com)
- [tweetbeaver](https://tweetbeaver.com)
- [spoonbill](https://spoonbill.io)
- [tinfoleak](https://tinfoleak.com)
- Twint CLI tool

### Facebook

On Facebook, you can use the search bar and narrow down some results.

Some search operators are:

- Show photos of lizards

`photos of Mark Zuckerberg`

- You can find an account's ID by looking at the source code of it.

Other options:

- [intelx.io](https://intelx.io/tools?tab=facebook)

### Instagram

Most of the Instagram OSINT is covered in the photos section, but there are some tools that can be used.

- Look at whom the person follows in their account

Other options:

- [codeofaninja intagram id](https://tools.codeofaninja.com/find-instagram-user-id)

### Snapchat

Snapchat has a [map](https://map.snapchat.com). You can look for snaps in a certain area.

### LinkedIn

LinkedIn is an awesome place to look for connections and work information of someone.

## Images

If everything you have from your target is a picture, **extract everything you can from it.** Is it a car picture? Does it have a plate? What's the side of the steering wheel? What are the surroundings?

### Reverse image search

You can look for the image source by using a search engine that has a reverse image search feature, such as [Google image search](https://images.google.com) and [Yandex](https://Yandex.com).

- Yandex has the ability to search for similar pictures.

- You can combine it with search operators.

Other options:

- [TinEye](https://tineye.com)

### EXIF data

EXIF data is metadata that can be viewed from an image. It can reveal location, device used to take the picture, time and more.

You can use tools such as [metagoofil](https://github.com/laramies/metagoofil) to harvest data from different files.

### Satellite images

If you want to do some physical location OSINT, you should check satellite photos of the location and absorb all you can about the place. Entrances, parking lots, employees and their dress code, badge readers, security, cameras… everything is important.

## Credentials discovery

### Usernames

[whatsmyname](https://whatsmyname.app/) and [Namechk](https://namechk.com) are good tools to see where a username is being used, and its accounts tied to it.

- It is an awesome way to find old accounts that may contain critical information.

- Sherlock is a python CLI tool that looks for usernames.

### Emails

[Have I been pwned](https://haveibeenpwned.com) is a good place to look for emails that have been found in data breaches.

- A good technique is to simply go to the Gmail login and see if the email exists. You can even click on “I forgot my password” and see if there are other emails linked to that account.

- If you want to search for emails related to companies and its employees, you can check its name on [hunter.io](https://hunter.io). This website can give you emails and show you their domain patterns.

- In order to verify if the emails are valid, you can use [email-checker](https://email-checker.net/validate).

Other options:

- [Scylla](https://scylla.so)
- [phonebook.cz](https://phonebook.cz)

### Passwords

When we are talking about passwords in OSINT, we are talking about finding breached credentials.

- By finding email and passwords, we can analyze them and look for a potential pattern that might come out.

- You can use [dehashed.com](https://dehashed.com) to see if a login has been breached.

- If you are dealing with a hashed password, a good thing to do is to try dehashing it on [hashes.com](https://hashes.com)

## Frameworks

OSINT frameworks are basically a collection of tools in one place. Some of them are:

- [OSINT framework](https://osintframework.com)
- Recon-ng
- Maltego
- Hunchly
