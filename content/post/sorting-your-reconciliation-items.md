+++
title = "Sorting your reconciliation items"
date = "2012-10-02T00:36:34"

+++
Reviewing reconciliation data and searching for matching items are where most user’s time is spent when using reconciliation software, so for a great user experience it’s vital that these tasks are efficient. Since making great reconciliation software is my aim, I’ve gone to great lengths to perfect Reconcilable’s Edit workspace.

This is the first in a series of posts on how the design of Reconcilable’s Edit workspace works towards making it the best reconciliation software in the world. See the whole series here.

## Sorting

![Multi-column sort applied to a reconciliation table in Reconcilable.](/img/sorting-multi1.png)

Sorting is necessary for working with reconciliation data, so how can it be optimized?

- You should be able to implement a sort as fast as you can think about it, as far as possible.
- Multi-column sorting should be as easy as sorting on a single column.
- It should be obvious how a table is sorted, without having to either read the table data or re-enact the sort just to be sure you’re seeing what you want.

Surprisingly, I’ve never seen an application that achieves these goals so I had to think afresh how to control sorting in Reconcilable.

## How it works

- ![Unused sort control](/img/single-sort-unused.png) Each column contains its own sort control. A single click on one of the arrows applies sorting on that column in ascending or descending order.

- ![Sort control, rank 1 ascending](/img/single-sort-ascending.png) Sorted columns and sort direction are identified by a solid colour arrow in the sort control, together with a number representing the column’s rank in a multi-column sort. Change sort direction just be clicking on the opposite arrow.

- ![Removing a column from the sort](/img/single-sort-delete.png) Move your mouse over the rank number and click to remove sorting from that column. When multiple columns are used for sorting, any of them can be removed from the sort in this way and the rank of other sorted columns will adjust automatically. Therefore, the easy way to modify sort order is simply to remove and add sorting columns in the order you need.

Can this be improved? Let me know if you think it can.
