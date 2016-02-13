+++
title = "Finding transactions that sum to a value"
date = "2012-10-29T08:10:28"
+++
*This is the third entry in my series on making the best reconciliation software in the world. Previous ones were on sorting reconciliation items and useful filters when matching.*

## This is surprisingly hard

Match these transactions by value:

![Subset-sum unmatched](/img/subset-sum-unmatched.gif)

<!--more-->
These transactions match one-to-many, but the “receipts” don’t have any details that can be used to identify *which* match together with each “deposit”. (In this case, adding up the receipts by date doesn’t help.)

We can’t use a one-to-many matching rule because there’s not enough detail for the rules engine to work with. However, matching manually is also a problem. Give it a go – how quickly can you find a match?

## Subset-sum

Solving the problem by inspection, or intuition, isn’t fun. Not for me anyway. It’s just too time-consuming and requires a lot of concentration. The problem here is that, even with just 11 receipt transactions, there are 2,047 ways of combining them. This is called the subset-sum problem – the problem of finding which numbers from a set of numbers sum to the required answer.

The reason that this problem has its own name in mathematics is that it’s very hard to solve quickly, not just for people but for computers too. As the number of transactions grows, the number of ways of combining them grows exponentially. In fact, for n transactions there are 2n – 1 ways of combining them. e.g.

-for 10 transactions there’s roughly 1,000 combinations
-but for 30 transactions there are over a *billion* combinations.

Even for a computer, it could take a darn long time to find the combination you want if you are looking through more than about 30 transactions. But this is hardly a large number of transactions in an average reconciliation.

Fortunately for you, I’ve added a clever *Match Finder* to Reconcilable that (often) solves this for you in just a second or two.

## Match Finder

Here’s how it works:

1. Turn on the *Match Finder* and select one or more transactions from one of the tables.  
![Subset-sum select 1](/img/subset-sum-select1.gif)

2. Match Finder searches for single or multiple transactions in the opposite table that sum to the value of your selection:  
![Subset-sum match finder](/img/subset-sum-match-finder.gif)

3. and immediately selects the first combination of transactions that match by value, like this:  
![Results: the matching subset found by the Match Finder](/img/subset-sum-results.gif)

4. The selection summary shows that the selected rows do indeed have the same values and can be matched immediately by clicking *Match*.  
![Summary of matching transactions found by Match Finder](/img/subset-sum-summary.gif)

*Match Finder* searches for all possible solutions and, if more than one is found, lets you flick through each alternative by clicking the arrow buttons.

This practical solution to the subset-sum problem when reconciling data is a feature which you may never need to use. But for the times when you do need it, it’s a real time-saver :)
