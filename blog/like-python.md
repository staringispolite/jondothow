---
id: 146
title: Like, Python
date: 2012-03-07T23:10:00+00:00
author: Jonathan Howard
layout: page
guid: http://staringispolite.com/blog/?page_id=146
---
**Like, Python**_(alpha)
  
_ 

Like making computers do your bidding?
  
Enjoy Python features like lambdas? Indent-grouping? List comprehensions?
  
Tired of **Old Man Python** telling you what you can and can&#8217;t say to **your** computer?

It&#8217;s about time programming languages understood what the kids are typing these days. So let&#8217;s start with a baby step in that direction: _Like, Python_.

_Like, Python_ was created by Jonathan Howard in February 2010 while drinking and reviewing code for an upcoming project with a coworker. At a certain point, higher-level explanations devolved into just flat-out reading Python code like they were actually speaking the language normally &#8211; complete with like&#8217;s, um&#8217;s, whatever&#8217;s, etc &#8211; making it completely impractical awesome for work. It was then that Jonathan realized he should perhaps stop for the night. And START creating _Like, Python_.

## EXAMPLE

_Like, Python_ uses Python&#8217;s own tokenizer to essentially add keywords to Python&#8217;s lexical understanding. Python is a subset of _Like, Python_, so any script you&#8217;ve already written in Python is valid _Like, Python_and will run in the interpreter. But you can also write like you&#8217;d speak. For example, the following is a fully-functional &#8220;hello world&#8221; script, included in the download as hello_world.lp:

<pre>#!usr/bin/python
  # My first Like, Python script!

  yo just print like "hello world" bro</pre>

Here&#8217;s a version that asks you for your name, then says hi. (Note that &#8216;yo&#8217; is a _Like, Python_ keyword but the interpreter actually understands real Python syntax, so the &#8216;yo&#8217; in the input string works just fine.

<pre>#!usr/bin/python
  uh from sys import exit

  # Grab the user's name.
  ok so like name = raw_input("yo! what's your name?" ) right

  # Make sure they entered something, then say hi.
  if name.strip() is actually like "":
      toootally just exit()
  else:
      um yeah
      print like "Hi %s, nice to meet you." % name</pre>

A full list of _Like, Python_ keywords is below (swearing optional):

  * Valleygirl: omg, so, like, totally, right, toootally
  * Frat guy: friggin, fuckin, dude, man, bro, broheim, broseph
  * Internets: lol, rofl, teh, ohai, plz
  * Snoop: yo, homey, homeboy, sup, dog, shit, girl, ma, biatch, ho, shiiit
  * Local: wicked, hella, anyways
  * Misc: just, hey, yeah, ok, um, uh, ah, actually, something

&nbsp;

## INSTALLATION

To install on Mac OSX and Linux, just unzip, make sure you have admin privileges on your machine and, type the following from inside your likepython directory:

<pre>~/downloads/likepython&gt; sudo cp ./likepython /usr/bin/
  ~/downloads/likepython&gt; sudo chmod 555 /usr/bin/likepython</pre>

If everything went well, you can now code in _Like, Python_! Test it on hello_world.lp (included) like so:

<pre>~/downloads/likepython&gt; likepython hello_world.lp</pre>

## VERSION

This is version 0.1, the stable alpha release. If you like it, let me know! jon[at]staringispolite.com

Or, you know, if not, you can like, tell me what you think could be improved. Especially new words Like, Python should include. Bro &#8211; it could like totally be in the next release.

## LICENSE

The MIT License
  
Copyright (c) 2010 Jonathan Howard

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the &#8220;Software&#8221;), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED &#8220;AS IS&#8221;, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.