## How to contribute

* Flosha
* 21.10.2024  
{: .author-date }

If you want to contribute your own research to the documentation, here is a little guide that has you covered from scratch. 

Contribution is very simple. Ideally (but optionally) you may get a local copy of the website. For this you install git, open the git console at the directory of your choice and type:

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

If this seems to complicated to you, don't worry. You also can contribute something via GitHub's webinterface. Just write a markdown document on your computer in any random text editor of your choice, then create a new file in the web interface (click on the ``+``, then choose ``add file``). Safe it with the extension ``.md``.  


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
