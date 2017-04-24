---
id: 305
title: 'Today I learned that creating getters &#038; setters in PHP more than doubles execution time.'
date: 2012-07-11T09:10:38+00:00
author: Jonathan Howard
layout: post
guid: http://staringispolite.com/blog/?p=305
permalink: /2012/07/11/today-i-learned-that-creating-getters-setters-in-php-more-than-doubles-execution-time/
categories:
  - programming
---
From reddit, I found this command-line snippet: http://pastie.org/638732. It reminded me that in general I want to do more of these kinds of tests. It&#8217;s bound to lead to interesting discoveries.

Any ideas what I should test myself?

&nbsp;

<table border="0" cellspacing="0" cellpadding="0">
  <tr>
    <td>
    </td>
    
    <td>
      <pre>&gt; php -d implicit_flush=off -r  '\
  class dog {\
    public $name = "";\
    public function setName($name) { $this-&gt;name = $name; }\
    public function getName() {return $this-&gt;name; }\
  }\
  $rover = new dog();\
  for ($x=0; $x&lt;10; $x++) {\
    $t = microtime(true);\
    for ($i=0; $i&lt;1000000; $i++) { \
      $rover-&gt;setName("rover");\
      $n = $rover-&gt;getName();\
    }\
  echo microtime(true) - $t;\
  echo "\n";}'
1.48462200165
1.49136686325
1.48365998268
1.47310495377
1.46616101265
1.44583415985
1.42663908005
1.43124985695
1.42830300331
1.42891597748

&gt; php -d implicit_flush=off -r  '\
  class dog { \
    public $name = "";\
  }\
  $rover = new dog();\
  for ($x=0; $x&lt;10; $x++) {\
    $t = microtime(true); \
    for ($i=0; $i&lt;1000000; $i++) { \
      $rover-&gt;name = "rover"; \
      $n = $rover-&gt;name;\
    }\
  echo microtime(true) - $t;\
  echo "\n";\
}'
0.700392007828
0.686674118042
0.687913894653
0.693347930908
0.697072982788
0.708423852921
0.709672927856
0.704964876175
0.704661130905
0.708118915558</pre>
    </td>
  </tr>
</table>