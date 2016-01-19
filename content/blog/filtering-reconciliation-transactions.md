+++
title = "Reconciliation-specific transaction filtering"
date = "2012-10-12T14:51:27"
type = "post"

+++
The *Edit workspace* in Reconcilable is used to browse through reconciliation data and to edit matches one-by-one. (The reconciliation data itself can’t be edited of course.) *This post is part of the series the best reconciliation software in the world.*

Being determined to make Reconcilable the world’s best software for matching and reconciling, I want to make sure that each element of the user interface works as well as possible. So how could I make something mundane such as transaction filtering really fantastic? To answer that requires thinking about what it’s used for.

## Why filter rec transactions? 

The main purpose of the *workspace* is to find transactions that match together. So the purpose of filtering here is to

> show only data that might be a good candidate for a match.

This is subtly different to the the purpose of generic filtering, such as is found in Excel, which might be stated as

> show only data that meets a user-supplied set of conditions.

The difference is that *I know why* a user might be filtering data in Reconcilable, so I can make it really easy to use by providing the specific filter conditions that suit this purpose, i.e. that *enable likely matching transactions to be revealed*. This means it’s just easier and faster to use filtering in Reconcilable for the types of filters that people working on a reconciliation are likely to want.

These filter shortcuts are implemented in the context menu displayed when you right-click on a table value. Here are a couple of examples:

## Show transactions near a date 

<img alt="Filtering on or near a date" style="float:right;" src="/img/date-context-filter.gif"/>

It’s often the case when matching transactions that they will appear on both sides of the rec with either the same or a similar date. The context menu when filtering on a date allows you instantly to show transactions
- only on that date
- within some number of working days from the date
- only for the week containing the date
- only for the month containing the date

## Find contras 

<img alt="Finding contra-matches using a filter" style="float:left;" src="/img/number-context-filter.gif"/>

It’s commonplace for transactions to be matched with ‘equal but opposite’ counterparts. Finding contra transactions can be a bit of a pain because they obviously don’t sort next to each other when sorted by value. Fortunately Reconcilable’s contra filter enables you to find contras in just two clicks by choosing the *Show +/- number* filter option.


 I’m pleased with this. Right-click filtering is fast, easy and often enables you to zoom right into where you need to look to find a match.

Does it work for you? Let me know if I can make this even better.
