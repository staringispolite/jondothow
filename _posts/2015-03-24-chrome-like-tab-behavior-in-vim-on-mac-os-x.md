---
id: 551
title: Chrome-like Tab behavior in Vim on Mac OS X
date: 2015-03-24T15:48:46+00:00
author: Jonathan Howard
layout: post
guid: http://staringispolite.com/blog/?p=551
permalink: /blog/2015/03/24/chrome-like-tab-behavior-in-vim-on-mac-os-x/
categories:
  - educational
  - programming
  - technology
---
Google Chrome has trained my brain that Ctrl+T, and ⌘+⌥+[arrows] will move me to the next and previous tabs. Here's how to make vim work the same way. In .vimrc...

<pre style="margin-bottom: 14px;">""""" TAB BEHAVIOR
" Ctrl+t to open new tab
" Note: this overwrites a shortcut for the tag stack, if you use tags
nnoremap &lt;C-t&gt; :tabnew

" Chrome-like shortcuts for prevtab and nexttab
" (Meaning ⌘+⌥+[arrows])
nnoremap &lt;ESC&gt;[1;9D gT
nnoremap &lt;ESC&gt;[1;9C gt</pre>

YMMV on the exact mappings to use, see below on how to figure it out for yourself. I found a lot of solutions that didn't work for me, including pressing the key combo in vim under Visual Line mode, so it would show me vim's notation for what keys it's getting. But the problem was three things failing in some combination:

-- The terminal was mangling the input before it got to vim

-- Vim wasn't showing me the starting "^[" (escape key)

-- Vim wasn't displaying the [1; section of the input either. Just ":9C" or ":9D"

After <a href="https://twitter.com/staringispolite/status/580258932381216768" target="_blank">a lot of searching</a>, I finally found <a href="http://stackoverflow.com/questions/7501092/can-i-map-alt-key-in-vim/24047539#24047539" target="_blank">this simple solution</a> to figure out what the terminal is actually sending, and translate to vim speak, all in one. Using the terminal on my Macbook Pro, it's surprisingly simple:

<pre style="margin-bottom: 14px;">&gt; sed -n l
[Press whatever key combination you want]</pre>

The output it showed me was &#8220;^[[1;9D&#8221;, so my key signature to map was &#8220;<ESC>[1;9D&#8221;

You can see <a href="https://github.com/staringispolite/dotfiles" target="_blank">my entire .vimrc file on Github</a>. Hat tip to <a href="https://twitter.com/mrmrs_" target="_blank">Adam Morse</a> for the warning on Ctrl+T and the tag stack.
