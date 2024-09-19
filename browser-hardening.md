## Browser Hardening

***Most important caveat in tech hardening:*** Customizing any of the performance-related `config` settings of your browser, might not provide the desired result across websites, and may eventually become an obsolete or an unnecessary change, once the default settings of your browser become improved along with its updated versions. You can backup the `prefs.js` file of your profile before trying these types of experiments. 

The `user.js` file available in the following repository was created for being utilized with a [Firefox Nightly](www.mozilla.org/en-US/firefox/nightly/notes/) browser. Its settings were decided upon, using research gathered from the given links in the references section.

>Download the user.js file from this repo - https://github.com/psyedout/firefox-user-prefs/ 

<br>

---

### Introduction 

The entire internet is a giant file-system, so to speak. Browsing files within the searchable world-wide-web of the internet, by accessing websites using a [web browser app](https://en.wikipedia.org/wiki/Comparison_of_web_browsers), is similar to walking around in a large public library and viewing the available books or magazines, while advertising and intelligence agencies constantly follow you around, looking over your shoulder, to figure out what you are viewing. Once they have a stereotyped idea about your online behavior and browsing preferences, they can suggest to you, a range of 'suitable' things that you may find attractive, so as to steer you towards those things via advertisements. 

How did those agencies ever determine what's best for you, and for your current or future needs? Answers to such ordinary questions that impact the lives of the public at large, are kept private and secret by those agencies, from the public, and especially from self-actualized people, for "business or national security reasons", and also, "for *your* own 'good.'" As such, your privacy and confidentiality is none of your concern as a matter of personal right, preference, or of your private and personal interests. 

>For all manner of intents and purposes, if one has to invest their personal attention towards something, then that something naturally becomes a matter of personal interest and business. Plus, there is no business that is worth attending to, and investing any attention towards, unless that something is somehow, personally relevant or intriguing. Wouldn't you agree? 

As such, why would you, ever bother to attend to something or someone, if that item, event, or person, had absolutely nothing to do with you and with your existence in this universe? 

So, in this article, I'm going to go over some of my thoughts and musings, on how to harden a browser, specifically a Mozilla one, for... you know, privacy purposes. This is because, whether you as an individual, do or don't care about your privacy, or about any of the things that might be worthwhile in aiding your progress, on your unique path in life, you might as well start meditating deeply about the worthiness of your attention and lifespan, at least now that you have somehow ventured into reading this article. In doing so, you might be surprised to learn that your own views about yourself, might be different, compared to the views held by arbitrary advertising companies and their workers regarding who you are, and what you ought to be.

---

### A note about latest browsers

A Firefox Nightly build often has various "bleeding-edge quirks", which can be problematic for regular browsing experience, as they can break a web-designer's intended display of a website's content. However, the main purpose of using the given `user.js` profile is to browse plain-text websites, with a level of anonymity that can be safe and secure for the end-user, with an emphasis on prioritizing the needs of the end-user, over that of the website designer's artistic endeavors. 

The priority of end-user accessibility needs, anonymity, secrecy, privacy, security, and confidentiality are also to be maintained above the needs of the types of marketers and advertisers, who tend to conduct phishing and watering-hole attacks to parasitically extract "business intelligence" from all online devices and web-users. 

To get started: 

1. You can view the current settings of your Mozilla browser, and the subsequent changes you may have adopted, through the `about:support` page, which can be accessed via the URLbar of your Firefox browser. 

1. To utilize a `user.js` file for a Mozilla browser, copy and paste it into the required "AppData" folder, which is better explained in the guide, videos from TechLore, or in the Arkenfox wiki provided in the references section. 

After blocking fingerprinting methods related to local storage, canvas, WebGL, WebRTC, screen resolution, audio context, clipboard, PDF-js, and other components like camera, graphics card, memory chips, battery pack, network adapters, BlueTooth module, and gyroscopes, that are unique to your hardware device; the eventual objective is to <ins>not</ins> have a drastically different looking combination of: 

- internet service provider, browser, default language, timezone, fonts list, browser plugins, and operating system being used by you for your online activities, compared to other online entities. 
 
What the current settings of your browser's UserAgent can reveal to common websites, can be tested using these examples - 

1. https://www.deviceinfo.me/

1. https://amiunique.org/ 

1. https://browseraudit.com/

<br>

---

### References:

1. https://www.eff.org/pages/surveillance-self-defense

1. https://github.com/techlore

1. https://arkenfox.github.io/gui/

1. https://wiki.mozilla.org/Privacy/Privacy_Task_Force/firefox_about_config_privacy_tweeks

1. https://wiki.mozilla.org/Security/Referrer

1. https://gist.github.com/0XDE57/fbd302cef7693e62c769

1. https://brainfucksec.github.io/firefox-hardening-guide

1. https://firefox-source-docs.mozilla.org/index.html

1. https://restoreprivacy.com/firefox-privacy/

1. https://w3c.github.io/geolocation-api/#privacy 

    1. `media.navigator.enabled = false` prevents audio, video, and geolocation access, and queries, from websites.

---

<details><summary><h3>Few other thoughts and opinions on individual privacy</h3></summary>

The above method may be helpful and useful, in avoiding advertisements that can clutter your browsing experience, although the very same method might make you more conspicuous to public security and policing agencies, that happen to continuously monitor all incoming and outgoing online traffic, in your geolocation's region. 

As an analogy, imagine people walking in a public town-square, mask-less people, who are dressed in ordinary attire for doing their shopping at eateries and clothing stores. And then, imagine yourself, walking around in public, among those town's folk, wearing full-body, medieval armor. Wouldn't you suddenly stand out and be rather conspicuous, compared to the rest of the crowd? Well, the local night-watch or Gendarmerie (police and armed forces), might be interested to know why a person dressed in armor avoids all banking, shopping, and other outlets, only to go to the library to read some "tech magazines." They might also be intrigued by how the person in armor, suddenly appears and then disappears, and seems to have no discernible identity, but can somehow, pass by check-posts, like a ghost. 

>Of course, after a few months and years, it may become entirely ordinary, and not seem too atypical or arbitrary, to any onlookers and overseers, if even one out every ten persons within the hypothetical towns-square, happen to look identical, while wearing the same silly-looking armor. 

The hypothetical town-square, is the world-wide-web, which has a daily crowd of hundreds of millions of human users, and billions of bots. Recording what each entity is, where it is from, what it is doing, how it is doing the things it appears to be doing, what its unique characteristics are, what it's presumable intentions might be, and what it might intend to do next, is the basic bread-and-butter of companies like Google, Microsoft, Apple, Baidu, Visa, Master Card, etc. 

So you see, once a browser app is hardened, and makes it less easy for state-sponsored and corporate entities to violate individuals' privacy, the harmful and hurtful entities among them, might simply attack the nearest of your kith and kin, and compromise your home's and workplaces' routers, to install malware into the devices used by your contacts and relationships, in order to vector an attack at you. 

So what will you need to do next? You will need to harden those routers and the operating systems, of all your devices, in order to protect the people you care about to the best extent possible, while adopting strategies and techniques for those attack vectors to be redirected at cybernetic "honey-pots." All of that seems like a massive chore, because it is. 

Preventing and admonishing, threat-actors and wrongdoers, was supposed to be an important job to be handled by public security administrators, and the judiciary, of each country. But, there are limitations to how well a judiciary along with its appendages can perform its duties, especially when the rest of the world moves at a pace that is a whole lot faster, than a local judiciary's archaic knowledge and procedures concerning cybernetic-systems. 

Who will protect the financiers, court officials, public service officers, and military personnel of your country from the insidious attacks orchestrated by supremacists? Well, weren't those police and military personnel of your country, the more qualified ones, who were supposed to be "the protectors", to protect you and themselves from all manner of human made tragedies and attacks?

Ah yes, they are as financially poor as you have been; and they also have been suffering the consequences of inequity, as you have been, if not more. Correct, *The Fifth-Estate* cannot help you nor itself, if numerous financiers, legislators, public service officers, and military personnel, of every other country, also get sucked into the greed of predatory and parasitic capitalism. 

There are other versions of social capitalism and symbiotic, or cooperative forms of existence, but for supremacists, the ultimate form of 'universal truth, reality, and wisdom', has to do with the maxim of, "eat-or-be-eaten." They do not seem to realize that only biological viruses and bacteria live by that bestial maxim, and that evolved species need not be destructive while working towards a daily-goal of equitable living, and sustainability. 

Therefore, you may be able to understand and agree that: as the thieves, usurpers, rapists, and murderers of this world continue to get richer and cleverer, and increase their usage of advanced technologies towards destruction of humanity, (which they acquire and distribute via multi-national and shell corporations, particularly to violate and abuse the sanctity of hundreds of millions of innocent people throughout the world, and to rob or steal equities from targeted communities), there remains no policing agency or legislative authority, to prevent or halt, the murderous activities of wrongdoers, and to arrest those willful violators; especially when influential members of in-charge public service agencies of numerous countries, happen to be colluding with the thieves and marauding bandits of this world. 

>Of course, there is some hope that within those very same conglomerates and agencies, there other conscientious people who can mend and repair the errors of their 'friends and colleagues'. 

Now, would the pillagers and marauders increase the range of their threats, violations, and subversive actions directed at you, if you were to harden your online and on-ground defenses to become more resilient? If you attempt to prevent molesters from groping you and your data, would they become more heavy-handed in wanting to violate you, with much more forceful and mechanistic zeal? They would, as they always have, not only because they can, but because they simply cannot tolerate the idea that there can exist such beings in this universe, who will not allow themselves to be subdued or preyed upon, by parasitic and predatory capitalists. The only thing that those fiends know to do, because of their age-old colonial habits, is to evade detection while sapping and violating every other person's privacy, in order to steal valuable personal, private, and confidential information of targeted individuals and groups; all the while, maintaining their own anonymity and secrecy. They know all too well that, **"information is power"**, and they intend to have supreme power over all individuals and peoples, throughout all possible realms. 

So, after you have come to realize that those rotten fiends will never stop, under any circumstances, only to hurt and destroy every relationship you've ever cared for, because they already have, and that those conniving and beguiling cheats will continue to usurp power, to make your life increasingly difficult, and that they will continue to use their insidious ways to injure each and every person you can ever love or care about, you will figure out a new approach to life, by either choosing to submit to them, or by choosing to be free. 

</details>