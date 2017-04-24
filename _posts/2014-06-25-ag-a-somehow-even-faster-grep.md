---
id: 486
title: Ag. A (somehow even) faster grep
date: 2014-06-25T12:43:53+00:00
author: Jonathan Howard
layout: post
guid: http://staringispolite.com/blog/?p=486
permalink: /blog/2014/06/25/ag-a-somehow-even-faster-grep/
excerpt: AG, aka &#8220;The Silver Searcher&#8221;, somehow embarrasses ack on performance, the same way ack embarrassed grep years ago. It also knows about .gitignore files and can plug in to vim and TextMate just like ack...
categories:
  - Uncategorized
---
<div class="wp-caption aligncenter" style="width: 630px">
  <img title="The Silver Surfer (creative commons image)" src="http://i.imgur.com/bh8slgi.jpg" alt="The Silver Surfer (creative commons image)" width="620" height="337" />
  
  <p class="wp-caption-text">
    The Silver Surfer (Marvel Comics)
  </p>
</div>

I still remember when I used <a href="http://beyondgrep.com/" target="_blank">ack</a> for the first time. It was shortly after I moved to SF, and <a href="https://twitter.com/brianrue" target="_blank">Brian Rue</a> swore by it. I was as skeptical before trying it as I was blown away after &#8211; usually at least 10x faster than grep, and better at ignoring useless files by default.

<a href="http://mrmrs.cc/" target="_blank">Adam Morse</a> just told me about <a href="https://github.com/ggreer/the_silver_searcher" target="_blank">Ag (aka &#8220;The Silver Searcher&#8221;)</a>, which somehow embarrasses ack on performance, the same way ack embarrassed grep years ago. It also knows about .gitignore files, and can plug in to vim and TextMate just like ack.

On mac, it&#8217;s just&#8230;

Install <a href="http://brew.sh/" target="_blank">homebrew</a>

> <pre><code id="selectable">ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"</code></pre>

&nbsp;

Install Ag

>     brew install the_silver_searcher

&nbsp;

And you&#8217;re off! (<a href="https://github.com/ggreer/the_silver_searcher" target="_blank">other install methods available</a>). I don&#8217;t have time for extensive performance tests, but at first glance, `ag` looks 20 times faster than `ack`, and 200 times faster than `grep`

<table dir="ltr" border="1" cellspacing="0" cellpadding="0">
  <colgroup> <col width="100" /> <col width="100" /> <col width="100" /> <col width="100" /> <col width="100" /></colgroup> <tr>
    <td rowspan="1" colspan="2" data-sheets-value="[null,2,&quot;time grep -inrH \&quot;testing\&quot; .&quot;]">
      time grep -inrH &#8220;testing&#8221; .
    </td>
    
    <td data-sheets-numberformat="[null,4,&quot;\&quot;$\&quot;#,##0.00&quot;]">
    </td>
    
    <td rowspan="1" colspan="2" data-sheets-value="[null,2,&quot;time grep -inrH \&quot;emissary\&quot; .&quot;]">
      time grep -inrH &#8220;emissary&#8221; .
    </td>
  </tr>
  
  <tr>
    <td data-sheets-value="[null,2,&quot;real&quot;]">
      real
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m2.875s&quot;]" data-sheets-numberformat="[null,4,&quot;\&quot;$\&quot;#,##0.00&quot;]">
      0m2.875s
    </td>
    
    <td data-sheets-numberformat="[null,4,&quot;\&quot;$\&quot;#,##0.00&quot;]">
    </td>
    
    <td data-sheets-value="[null,2,&quot;real&quot;]">
      real
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m2.922s&quot;]">
      0m2.922s
    </td>
  </tr>
  
  <tr>
    <td data-sheets-value="[null,2,&quot;user&quot;]">
      user
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m2.420s&quot;]">
      0m2.420s
    </td>
    
    <td>
    </td>
    
    <td data-sheets-value="[null,2,&quot;user&quot;]" data-sheets-numberformat="[null,4,&quot;\&quot;$\&quot;#,##0.00&quot;,1]">
      user
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m2.358s&quot;]">
      0m2.358s
    </td>
  </tr>
  
  <tr>
    <td data-sheets-value="[null,2,&quot;sys&quot;]">
      sys
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.170s&quot;]">
      0m0.170s
    </td>
    
    <td>
    </td>
    
    <td data-sheets-value="[null,2,&quot;sys&quot;]">
      sys
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.230s&quot;]">
      0m0.230s
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
    </td>
    
    <td>
    </td>
    
    <td>
    </td>
    
    <td>
    </td>
  </tr>
  
  <tr>
    <td rowspan="1" colspan="2" data-sheets-value="[null,2,&quot;time ack testing&quot;]">
      time ack testing
    </td>
    
    <td>
    </td>
    
    <td rowspan="1" colspan="2" data-sheets-value="[null,2,&quot;time ack emissary&quot;]">
      time ack emissary
    </td>
  </tr>
  
  <tr>
    <td data-sheets-value="[null,2,&quot;real&quot;]">
      real
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.303s&quot;]">
      0m0.303s
    </td>
    
    <td>
    </td>
    
    <td data-sheets-value="[null,2,&quot;real&quot;]">
      real
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.293s&quot;]">
      0m0.293s
    </td>
  </tr>
  
  <tr>
    <td data-sheets-value="[null,2,&quot;user&quot;]" data-sheets-numberformat="[null,4,&quot;\&quot;$\&quot;#,##0.00&quot;,1]">
      user
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.267s&quot;]">
      0m0.267s
    </td>
    
    <td>
    </td>
    
    <td data-sheets-value="[null,2,&quot;user&quot;]">
      user
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.265s&quot;]">
      0m0.265s
    </td>
  </tr>
  
  <tr>
    <td data-sheets-value="[null,2,&quot;sys&quot;]">
      sys
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.026s&quot;]">
      0m0.026s
    </td>
    
    <td>
    </td>
    
    <td data-sheets-value="[null,2,&quot;sys&quot;]">
      sys
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.024s&quot;]">
      0m0.024s
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
    </td>
    
    <td>
    </td>
    
    <td>
    </td>
    
    <td>
    </td>
  </tr>
  
  <tr>
    <td rowspan="1" colspan="2" data-sheets-value="[null,2,&quot;time ag testing&quot;]">
      time ag testing
    </td>
    
    <td>
    </td>
    
    <td rowspan="1" colspan="2" data-sheets-value="[null,2,&quot;time ag emissary&quot;]">
      time ag emissary
    </td>
  </tr>
  
  <tr>
    <td data-sheets-value="[null,2,&quot;real&quot;]">
      real
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.013s&quot;]">
      0m0.013s
    </td>
    
    <td>
    </td>
    
    <td data-sheets-value="[null,2,&quot;real&quot;]">
      real
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.014s&quot;]">
      0m0.014s
    </td>
  </tr>
  
  <tr>
    <td data-sheets-value="[null,2,&quot;user&quot;]" data-sheets-numberformat="[null,4,&quot;\&quot;$\&quot;#,##0.00&quot;,1]">
      user
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.007s&quot;]">
      0m0.007s
    </td>
    
    <td>
    </td>
    
    <td data-sheets-value="[null,2,&quot;user&quot;]">
      user
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.008s&quot;]">
      0m0.008s
    </td>
  </tr>
  
  <tr>
    <td data-sheets-value="[null,2,&quot;sys&quot;]">
      sys
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.009s&quot;]">
      0m0.009s
    </td>
    
    <td>
    </td>
    
    <td data-sheets-value="[null,2,&quot;sys&quot;]">
      sys
    </td>
    
    <td data-sheets-value="[null,2,&quot;0m0.009s&quot;]">
      0m0.009s
    </td>
  </tr>
</table>
