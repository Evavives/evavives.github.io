---
title: Découvrir la psychologie pour mieux enseigner
date: 2021-07-01
permalink: /posts/2021/cortecs
excerpt_separator: 
toc: true
tags:
  - cortecs
  - education
  - critical thinking
  - MOOC
---

Article available in French on [Cortecs website](https://cortecs.org/non-classe/decouvrir-la-psychologie-pour-mieux-enseigner/) on how states preempt separatist conflict, I needed to submit replication materials to the journal. I took my graduate quantitative methods sequence with the late [Tom Carsey](https://sites.google.com/view/tom-carsey/home), so I've long been a proponent replicability efforts in social science. I also had an hourly job in grad school replicating quantitative results for multiple political science journals, so I'm very familiar with best practices for replication. Unfortunately, in the four years since I wrote the first line of code for this project, somewhere in between defending my dissertation and starting a new job (ok, fine, almost immediately after writing that first line of code), I got a little lazy.



# Regular expressions

Luckily, I was able to take advantage of RStudio's built in support for [regular expressions](https://en.wikipedia.org/wiki/Regular_expression) to save myself from having to manually change each line of code that either loaded or saved a file. Regular expressions are a powerful way to search through and manipulate text. You can activate them in RStudio's find and replace dialog by checking the Regex box:

![](/images/posts/rstudio-regex/regex.png){: .align-center }

Once you've done that, certain characters in your search will no longer be interpreted literally. The most important difference is probably `.`, which is a stand-in for any character.[^newline] This is similar to how `*` is a wildcard in the Unix shell, e.g., you can use `ls *.R` to list all R script files in a folder. The main regular expression feature I used is the [capturing group](https://www.regular-expressions.info/refcapture.html), which allows you to identify and extract a subset of a line of text. You designate a capturing group by surrounding the desired text with parentheses. To fix all of the code loading RData files from the Figure Data folder, my regular expression looked like this:


