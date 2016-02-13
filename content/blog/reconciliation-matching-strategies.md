+++
date = "2015-11-27T08:10:17Z"
title = "reconciliation matching strategies"
draft = "true"

+++

How would you go about reconciling two sets of data?

Computers may be fast, but when looking for matches amongst a million records or more the matching process is not going to be completed immediately. So the strategy used could make a significant difference.
<!--more-->

Let's assume that you have two printed sets of records, a notepad and a pen. What would be the best way to proceed?

Well, it might depend on the content of the records and your insights into the meaning of some of the data, so we'll assume you can only match on a single numeric value in each list. Other assumptions are that matching should be one to one and values must match exactly and there may be some records without matches in either list.

## Method 1 - Pick and scan

Starting from the top of one list, work down it one record at a time, search through the other list and when you find the matching record, mark off the the line on each list.

This might take less than O(m * n) time.

## Method 2 - Sort and compare

If you could sort the items in your lists by value before printing them off, then maybe things would go more quickly. Sorting would take some time, but once done you would expect to be able to find the items you are looking for much more quickly. You start at the top of each list and mark off the ones that match and move down on each side until you find the next match. The thing with this approach is that you don't need to scan the second list when searching for matches - you only need to look in the range near the value you're looking for, and you can keep your finger at the position you've got to working downwards. There is no more searching.

You pay the penalty of sorting each list first but then the matching process should go much easier.

If the sorting takes a long time, then maybe you only need to sort one list. You then work down the non-sorted listed and for each line you look in the sorted list to find the match. Looking in the sorted list is obviously going to be much quicker because you can very quickly home in on the line your looking for.

Both of these sort-first techniques can be useful ways to speed up your search, although it takes a lot longer to find the first matching pair because you’ve got to complete the sorting before you even try to start matching.

There’s another approach you could take which you probably wouldn’t try at all if working manually but is actually reasonably practical in computer code. That is to work down both lists, and build an index that locates the lines in each list according to the information that you need to match on. Each entry in the index will hold a set of matching records. Once you’ve collected your match in the index entry, you can mark those entries as matched and remove the entry from the index. With this method, there is no need to pre-sort the data and you only need to work done each list once. You just need a good way of building the index.

