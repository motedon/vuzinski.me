---
title: Updates
draft: false
tags: []
---
Personal or technical updates worth pointing out.
## Technical Updates:

##### 10.10.2024 19:42
Icon, images testing - works.
##### 03.10.2024 00:07
Locales on linux and how Obsidian or where the fuck does it get its locales is absolute bullshit. I can't fucking change the date property on the frontmatter from the default garbage mm-dd-yyyy to a fucking normal, logical format, aka dd-mm-yyyy.
Seems like it's Obsidian on linux thing, my setup already has all the needed locales set up and everything seems to be working, but obsidian doesn't. There is a workaround which will be implemented since I have no fucking choice. I won't be getting the fancy date picker, but I will from now on create notes with automatic current date on the property section.

00:12
It's so fucking sad that my notes don't have the exact date of creation. Details matter to me and it sucks how things can be sometimes.
It's my fault for not closing obsidian when doing a sync so it's me who will deal with the consequences, blabla whatever fml.

##### 02.10.2024 19:24
God fucking damn it, before syncing the vault I should fucking close obsidian so that my notes don't get a new date of creation, goddamn it, time stamps matter.
I should fix it with fucking templater, bullshit behavior and now I can't find where to add the old dates in? so in one day I have vomited 20 notes, yeah right. CLOSE OBSIDIAN BEFORE EACH COMMIT YOU MONKEY.
fix with templater, fix with templater, fix with templater
##### **26.09.2024 21:10**
This page now has a domain name, vuzinksi.me, very fucking cool if you ask me.
Also soon testing for images will be done, so that more expression is allowed AKA MEMES.
200k một domain, haha ngon. tính 1 bát phở là 35k thì tầm 5 bát phở đc có blog cá nhân. Hoặc nếu tính bằng giá xăng thì nó sẽ hơi đắt, 20k/lít thì 10 lít xăng đc blog cá nhân, đẩy bình cho 5 xe wave.
##### **21.09.2024 04:01**
The "Recently edited" and "Recent new files" Tables now work. Clicking each link won't show 404 page.
Thanks to ChatGPT... I did manage to figure out how to find the files and how to modify or change something in them using the Templater or Dataview pluggins in Obsidian, mind you, I have no experience with JavaScript despite it being used in the Templater script...
An one liner that fixed it all...
```
queryOutput.value = queryOutput.value.replaceAll("content/", "");
```
And now the date is the right format in one of the tables.

##### **19.09.2024 01:12**
The "digital garden" has a shortened home page
Changed the tags so it's compact and easy
Clicking the links and tags now work. No more 404's

01:23
The tables that shows the recent stuff on the index page: 
The links don't work, what the fuck, 
## Personal Updates:
##### 10.10.2024 19:42
Doubting whether or not writing/creating this page is worth it. I barely write. I do have thoughts but I just vomit it out there, It's nothing that I feel is significant, product like, worthwhile. will see... *might delete later* 
##### **19.09.2024 01:18**
Hopefully writings should start pouring like an alcoholic pouring a drink.

**01:20**
I'm starting to see blue fog/smoke while looking at a light source, going blind?

## Technical details:
The priority is this to be mobile-reading friendly.
Desktop version has few useless features.
Date format is DD.MM.YYYY time format is HH:MM (24-Hour)