---
title: About the Gothic MDK
---

<style>

.article h1, .article h2, .article h3, .article h4, .article h5 {
  font-size: inherit;
}

.article h1 {
  color: #9a5050; /* red colour for the main heading */
  background-color: #262422; /* header bg colour */
  text-align: center;
  border-bottom: 1px solid #808080;
  padding: 5px;
  margin: -7px -7px; /* needed to overcome the article padding */
}

.article h2 {
}

/* Author + Date/Version Section */

.doc-info {
  background-color: #262422; /* header bg colour */
  font-weight: bold;
  display: flex;
  justify-content: space-between;
  padding: 0;
  margin: 7px -7px 0;
  border-bottom: 1px solid #808080;
}
.doc-info li {
  padding: 3px 7px;
  display: flex;
  flex-wrap: wrap; /* necessary for very narrow screens */
}
/* needed for the seperating border */
.doc-info li:nth-child(1) {
  width: 50%;
  border-right: 1px solid;
}
/* first child */
.doc-info li:nth-child(1)::before {
  content: "Author:";
  padding-right: 3px;
}
/* second child */
.doc-info li:nth-child(2)::before {
  content: "Version:";
  padding-right: 3px;
}


/* ARTICLE SECTION */
	
.article {
  background-color: #0f0f0f;
  padding: 7px;
  border: 1px solid #808080;
  margin-top: 20px;
}

/* Needed for markdown styling in order to have seperate boxes divided into h2 sections */
.article h2::before {
  display: block;
  height: 20px;
  width: calc(100% + 16px);
  background-color: black;
  content: '';
  position: relative;
  left: -8px;
  border: 1px solid #808080;
  border-left: black;
  border-right: black;
  margin-bottom: 10px;
}
</style>


# About the Gothic MDK

* Flosha
* 21.10.2024
{: .doc-info }


## Why this website in this form?

Several approaches have been made in the past to create an online Gothic modding documentation. 

One of them is the [Gothic Editing Wiki](https://wiki.worldofgothic.de/doku.php) at World of Gothic. It is very old, but it lacks various areas of modding, that it doesn't address and doesn't offer tutorials about. It is written in German, thereby making it hard to follow for the international modding community. It also contains very outdated information and, as it seems, is not updated anymore. 

A newer approach is the [Gothic Modding Community website](https://gothic-modding-community.github.io/gmc/) (short GMC). It aims to address some areas, like modeling and animation, that other resources do not inform about. It is written in English, which makes it more accessible to a larger number of people. It also is open source and hosted on GitHub, like all of our websites are too. New documents can be written in Markdown, as we did it with our Phoenix Docs, which makes it easy to contribute. In these areas it is great. But it is based on a bloated framework, its design is very boring and optimised for mobile with bad readability on Desktop (too wide etc.) and the author was not fond of any suggestion for improvement from my side (thus I had to do it on my own).

There were more approaches than these. I remember a specific Gothic Editing website, which I guess is offline now, but if anyone finds the address we may be able to link it here through the Internet Archive. 

But what all of these approaches have in common is something that I just have no understanding for: They all start from scratch, simply ignoring the official documentation by the Mad Scientists. A documentation which is both valuable and very well written. So why is it ignored? 

The entire Gothic Modding Community exists primarily thanks to them and Nico Bendlin. The Mad Scientists have written the engine. They have written the script language Daedalus. They have created the Spacer and they have finally written most of the documentation and brought us the ModKit. But instead of respecting their work and taking their documentation as the foundation for further research and additional tutorials, their work is ignored. 

The only reasoning I can come up with for why that is, may be the focus of a majority of todays modding community on the (so-called) "Gothic 2" and its Modkit, which does not contain said documentation. They may ignore it because they simply don't care for the actual, original Gothic. 

So what I wanted to do instead with this website, is...
* ... to give justice to the original documentation of the Mad Scientists by translating it into English in its entirety and taking it as the foundation upon which to build our own, developing it further, not replacing it.
* ... to give justice also to their simple html documentation design, in that I preserve the original design, only transferring it into a kind of dark-mode styling in accordance with Gothic, our Archive and our other websites.
* ... to link the documentation directly with our update of the Mod Development Kit (MDK) itself, that we curate since 2019, which contains the necessary scripts and assets to modify, as well as with all the relevant tools created by the community; this is the reason that our Menu is split into three sections: /GDATA (Gothic files), /Documentation and /tools.
* ... to serve thereby not only as an international modding documentation that is easy to contribute via Markdown, but also as an international ZenGin Modding Hub.
* ... obviously, just as the Gothic Archive and the entire Phoenix project, it is limited to the original GOTHIC.  


## What we changed about the original design and why

* For readability as well as to reduce strain on the eyes and in order to fit better to the overall gothic style and the rest of our websites, we re-interpreted the original html documentation in a dark-mode. Therefore: The white background turns black, light grey backgrounds into dark grey, and light blue backgrounds into dark blue; text and link colours are adjusted accordingly. 
* In order to be able to differentiate the original documents by the Mad Scientists from new documents written by us and others, we introduced two different link colours. Light blue links connote original documentation (just translated by me), green links connote new documents. 
* TODO: Back in the day when the original documentation was written, a font-size of 10pt appeared larger on these smaller screens with much smaller resolutions than they do today. Instead of sticking to the very same font-size, we have to choose a font-size that offers an equivalent readability on modern screens. Therefore we increased the font-size to ~14px for regular text. 
* TODO: While we consciously stick and appreciate the retro design in almost every regard, there is at least one design aspect that we do not consider to be reasonable and that is a lack of space. The oldschool tables and borders are fine, but they have to have more padding to give room to the content (e.g. text). 