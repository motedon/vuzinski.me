---
title: Updates
draft: false
tags: []
---
Personal or technical updates worth pointing out.
## Technical Updates:
##### **21.09.2024 04:01**
The "Recently edited" and "Recent new files" Tables now work. Clicking each link won't show 404 page.
Thanks to ChatGPT... I didn't manage to figure out how to find the files and how to modify or change something in them using the Templater or Dataview pluggins in Obsidian, mind you, I have no experience with JavaScript despite it being used in the Templater script...
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
##### **19.09.2024 01:18**
Hopefully writings should start pouring like an alcoholic pouring a drink.

**01:20**
I'm starting to see blue fog/smoke while looking at a light source, going blind?

## Technical details:
The priority is this to be mobile-reading friendly.
Desktop version has few useless features.
Date format is DD.MM.YYYY time format is HH:MM (24-Hour)