+++
title = "Thoughts on Hugo"
description = ""
tags = [
    "blog", "hugo",
]
date = "2022-05-29"

+++




I orginally found out about Hugo after browsing Hacker News (YCombinator) and coming across a blog with a footer containing a link to Hugo's site. You can scroll to the bottom to get an exact example of what I'm talking about. If you click on the link you can see Hugo advertised as: "One of the most popular open-source static site generators." Beforehand, I had been thinking about creating my own site and was researching what exactly I wanted to build my site with. Reading this I immediatley bookmarked it. Hugo also claims to be the world's fastest framework for building websites. Have no clue how true that is. Although Hugo is freakin fast once everything is set up. I specically wanted to create my site as a blog and hugo seemed perfect for that. If you look at the [themes](https://themes.gohugo.io/) for hugo it's mostly just blogs. 

Once I came across the hugo-dusk theme I decided that I was going to create my blog with Hugo. Before, I was considering Jekyll or Wordpress, but once I saw the hugo-dusk theme I made up my mind immediatley and installed Hugo. I started reading the documentation and came to conclusion that I wouldn't be too difficult. Once I actually started creating my site I quickly realized Hugo was kind of a pain in the ass. The [documentation sucks](https://news.ycombinator.com/item?id=30527884). To say it's confusing would be an understatment. I think part of the problem was that I'd never used a static site generator before so everything I was doing was brand new to me. 

Creatinga the site and implementing a theme locally were very easy. The two main issues I had was modifying the theme, and hosting the site. The way Hugo works is that you can either create your own theme or choose a theme created by someone else. Themes are usually hosted on github. You can just clone the repo into your themes folder. Easy enough. Everything works out great locally until you actually try to host the website. Right when you attempt to put it on Github, Github is like, "Hey this is something you got from github, you need to create a submodule." I could just delete the git file, but then I have the problem of not getting continuous updates from the theme's author. So I go ahead and create a submodule instead. The problem is now I don't actually have control of the theme. I can't directly modify it myself. Thankfully, with Hugo you can tell your site to overwrite the theme to your liking. The main problem with this is that it isn't that reliable and it's just a huge pain to get it to work.

The way Hugo works is that you choose a theme, add content, then have the Hugo generator to convert all your content into static HTML files so it can be properly hosted on the web. Here's what the file structure of my site [looks like](https://github.com/have-no-clue-what-im-doing/Broderic_Blog)

    User/Hugo/MyBlog  
	
    |- .git
	|- archetypes
	|- content
	|- data
	|- layouts
	|- public
	|- resouces
	|- static
	|- themes
	|- .gitmodules.txt
	|- config.toml
	|- netlify.toml
	|- README.md