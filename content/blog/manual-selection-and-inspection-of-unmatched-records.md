+++
title = "Manual selection and inspection of unmatched records"
date = "2012-11-05T14:35:21"
type = "post"

+++
This is the fourth entry in my series on aiming to make the best reconciliation software in the world. Previous ones were on sorting reconciliation items, useful filters when matching and finding transactions that sum to a value.

## Status Bar Sum

When reconciling in Excel, a feature that many accountants use is the **Sum** value shown in the *Status Bar*:

{{< figure title="Sum value shown in Excel's status bar" src="/img/excel-status-bar-sum.gif" >}}

This conveniently shows the sum of all numbers currently selected in the worksheet, and updates instantly as the selection changes. Therefore, as you click and drag with your mouse down a column of numbers you can know their total immediately. You’d probably use this to find out whether the selected numbers add up to a known sum, perhaps dragging up and down to include or exclude more numbers in the selection.

This is obviously a pretty useful feature when you’re finding or checking matches so Reconcilable borrows from this idea.

## Improving on Excel

<img style="float:right;" alt="Multi" src="/img/drag-multi-select.gif"/>

We found a couple of ways to improve on Excel’s selection-sum display.

**Firstly**, the mechanics of Reconcilable’s record selection are better. As with Excel you can easily select multiple records by clicking and dragging up or down one of your reconciliation tables. The displayed total of the selected records updates instantly as you go.

However, unlike Excel, Reconcilable makes it just as easy to de-select one or many records. Just click on an already-selected row and it deselects. By dragging, you can deselect many records.

Drag-selecting in Reconcilable is also *non-destructive* of prior state. This is a little hard to explain in words, but it goes like this:- What happens if you drag-select over a row that is already selected? Since your current action is selection, the row remains selected, forming part of your selected set. But if you drag back up, de-selecting rows again, then any rows that were originally selected remain selected. i.e. They don’t lose their initial state. The same happens in reverse if you are dragging to deselect.

Incidentally, using double-click to select is definitely a mistake. It’s *very* unergonomic. Not only does double-clicking not allow drag-selecting multiple records, it’s also a really tiresome action to have to perform lots of times. Does anyone else remember the physical strain of using the old *Cognos Impromptu*, which was driven by endless double-clicking? My wrist-muscles still twitch at the memory.

**Secondly**, you can’t fail to notice Reconcilable’s selection summary. It’s easily visible, comfortably sized and always shows the number and value of records currently selected for each table.

![Selection summary in Reconcilable.](/img/selection-summary-notmatched.png)

Much better, I think, than squinting down at the bottom of the Excel window to pick out the Sum value. Some other reconciliation applications also relegate selection totals to the edge of the screen or camouflage them amongst sets of other numbers. This is *fundamental data* for the match-editing screen and as such needs to be clear and obvious.

So there you have it. I find that record selection in Reconcilable is fast and efficient, but let us know if you can think of ways to make it even better.
