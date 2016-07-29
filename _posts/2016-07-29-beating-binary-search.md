---
layout: post
title: Beating Binary Search
date: 2016-07-29
---

Reviewing some concepts in CLRS, I noticed my natural method for searching for a specific page is not binary search. Generally I flip to a page that I estimate to be the about right, then flip forward and back again and again, turning fewer pages at a time as I get closer.

I imagine this is more efficient than simple binary search, since binary search doesn't have the additional knowledge about the problem that I do.

My method certainly takes less time that me implementing binary search, but I want to see how much more efficient it is by the number of actions it requires.

I'll try three methods:
1. Binary search, as best I can do. I will estimate where I think the middle is and turn to there.
2. "Improved" binary search, where I start with more reasonable higher and lower bounds for the number supplied.
3. My natural method, where I guess and then keep guessing.

My criteria for success will be the average number of page flips or checks. I will run 10 trials for each method, because more will be boring. My copy of CLRS has 1180 pages excluding the preface, which I have excluded with a bookmark. Generating a random page to turn to in Python. In case I get better at selecting pages as I go on, I will alternate between the three methods each trial.

Results:
1. Binary Search: 8.3 flips on average
2. Improved Search: 6.8 flips on average
3. My Method: 5.1 flips on average

Binary search wasn't as slow as I thought it would be! The biggest problem/annoyance is its inability to capitalize on getting *really close* to the correct page. Part of the reason my method's average was so low was the probability of getting lucky, which can be defined as the correct page plus or minus a few. With binary search, luckiness is defined as the correct page only.

Not changing my method of turning to pages. I do wonder what the actual best method is. Probably not a well-defined question; it surely depends on how well you can estimate the page thickness.
