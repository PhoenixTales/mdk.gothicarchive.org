# About this website and how to contribute

* Flosha
* 21.10.2024
{: .author-date }


## Why this website in this form

Several approaches has been made in the past to create an online Gothic modding documentation. 

One of them is the [Gothic Editing Wiki](https://wiki.worldofgothic.de/doku.php) at World of Gothic. It lacks various areas of modding, that it doesn't address and doesn't offer tutorials about. It is written in German, thereby making it hard to follow for the international modding community. It also contains very outdated information and, as it seems, is not updated anymore. 

A newer approach is the [GMC (Gothic Modding Community) website](https://gothic-modding-community.github.io/gmc/). It aims to address some areas, like modeling and animation, that other resources do not inform about. It is written in English, which makes it more accessible to a larger number of people. It also is open source and hosted on GitHub, like all of our websites are too. New documents can be written in Markdown, as we did it with our Phoenix Docs, which makes it easy to contribute. In these areas it is great. But it is based on a bloated framework, its design is very boring and optimised for mobile with bad readability on Desktop (too wide) and the author was not fond of any suggestion for improvement from my side. Thus I had to do it on my own.

There were more approaches than these. I remember a specific Gothic Editing website, which I guess is offline now, but if anyone remembers the address we may be able to link it here through the Internet Archive. 

But what all of these approaches have in common is something that I just have no understanding for: They all start from scratch, simply ignoring the official documentation by the Mad Scientists. 

A documentation which is both valuable and very well written. So why is it ignored? 

The entire Gothic Modding Community exists primarily thanks to them and Nico Bendlin. The Mad Scientists have written the engine. They have written the script language Daedalus. They have written the Spacer and they have finally written most of the documentation and brought us the ModKit. But instead of respecting their work and taking their documentation as the foundation for further research and additional tutorials, their work is ignored. 

The only reasoning I can come up with for why that is, may be the focus of a majority of todays modding community on the (so-called) "Gothic 2" and its Modkit, which does not contain said documentation. They may ignore it because they simply don't care for the actual, original Gothic. 

So what I wanted to do instead with this website, is...
* ... to give justice to the original documentation of the Mad Scientists by translating theit entire documentation into English and taking it as the foundation upon which to build our own, developing it further, not replacing it.
* ... to give justice also to their simple html documentation design, in that I preserve the original design, only transferring it into a kind of dark-mode styling in accordance with Gothic, our Archive and our other websites.
* ... to link the documentation directly with our update of the Mod Development Kit (MDK) itself, that we curate since 2019, which contains the necessary scripts and assets to modify, as well as with all the relevant tools created by the community; this is the reason that our Menu is split into these three sections: /GDATA (Gothic files), /Documentation and /tools.
* ... to serve thereby not only as an international modding documentation that is easy to contribute via Markdown, but also as an international ZenGin Modding Hub.
* ... obviously, just as the Gothic Archive and the entire Phoenix project, it is limited to the original GOTHIC.  


## How to contribute

Contribution is very simply.

Ideally (but optionally) you may get a local copy of the website. For this you install git, open the git console at the directory of your choice and type:

```
git clone https://...
```

You can now create new files, modify existing files etc. After you are done with your changes, you open the console again and type ``git status`` which shows you all the files you modified. 

Now you need to add them by
```
git add [insert file path / file name]
```

Then you need to commit via:

```
git commit -m "Your Message: My new document"
```

Then ``git push``. Take care to perform ``git pull`` beforehand in order to avoid any conflicts with changes that others have made. 

If this seems to complicated to you, don't worry. You also can contribute something via GitHub`s webinterface. Just write a markdown document on your computer in any random text editor of your choice, then create a new file in the web interface (click on the ``+``, then choose ``add file``). Safe it with the extension ``.md``.  


### How to write a document in Markdown

You can take this document here as an example. Just take a [look at it in the repository](https://github.com/PhoenixTales/mdk.gothicarchive.org/blob/main/docs/contribute.md). 

You begin a document by a first class heading. You create a heading via ``#``.

One ``#`` is the main title of the document and equals ``<h1>`` in html, into which it will automatically be transformed. ``##`` is for a suh-heading, then `###` and so forth. Example:

```

# My Document

```

Under the heading you should put your name as the author of the document and the date of its creation or publication under it. You do so by typing this:

```
* [Insert your Name]
* [Insert the current Date]
{: .author-date }
```

You just write these two informations behind the asterices. They make it a list. Via the class ".author-date" that you assign to the list above, the list is then automatically styled as you can see it in this document, to display author and version at the top of the document. 

Now you have to write the rest of your content. Add headings, lists as above or whatever you like. 

If you want to emphasize a word or a few words or a sentence, you can do so by putting a ``*`` in front and behind it, 

```
*like this*
```

The result will *be this - italics*.

If you want to make text bold, you can do so by using two asterices ``**``.

```
**like that**
```

The result will **be this - bold text**.

If you have something like a side note, a trivial annecdote or additional information that you would like to present a bit seperated from the main text, perhaps in a bit of a smaller font-size, just add this:

```
{: .note }
```
below the paragraph.  
The paragraph will then be styled automatically on the website and present the text as a side note. 

There are other tricks, like writing code, inserting links or including images or code passages, like I did above. But just look at this document in the repository, where you can switch between edit mode and preview, in order to understand how it's done. For more information just google Markdown and you will easily find whatever you need to know to write Markdown documents. 
