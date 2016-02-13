+++
title = "Extracting a code from some text"
date = "2012-10-17T14:43:50"
+++
## Calculation functions in Reconcilable

I’ll be the first to admit that Reconcilable’s column calculation function has ’til now been basic. In fact I originally developed it to solve a single problem:- calculate the net of values from separate debit and credit columns so that the net value could easily be used for matching.
<!--more-->

But out in the wild, you’re likely to have a wider range of uses for calculated columns, so I’m currently working on expanding the calculation repertoire. I’m starting with a clean slate for the new ‘function language’, which is great! It means I can design functions *specifically to suit reconciliation work*, so reconciliation-related tasks become much easier in Reconcilable than they are in generic data management tools such as Excel, Access or SQL.

## Extracting useful codes

For example, when working with data for reconciliation you often want to extract a code or word out of a field containing a longer piece of text. Extracting a code enables you to easily match with it or use mapping, sorting, etc. just on the code.  Therefore I’m creating a single function, EXTRACT, that does exactly this.

If you’re working in Excel et al. you’ll need to struggle with a handful of text-manipulation functions (LEFT, RIGHT, SEARCH, LEN, etc.) whilst handling error conditions, resulting in a very complex formula for something that can be expressed quite easily in English.

Here’s how it’s currently shaping up. Compare the functions in Excel to the new equivalent in Reconcilable:

### Extract the security code from ‘/US/265178′ and ‘/JPN/6524170′

Note that the codes to be extracted are of different lengths, as are the prefix elements that need to be discarded.

<table>
<tr><td>Excel</td><td>=IFERROR(RIGHT(A1,LEN(A1) -FIND(“/”,A1, 2)), “”)</td></tr>
<tr><td>Reconcilable</td><td>(EXTRACT FROM [Col1] START AFTER LAST ‘/’)</td></tr>
</table>

### Extract the cheque number from ‘CUSB06_20120427CH882053.’ and ‘CUB15_20120501CH2563.’

<table>
<tr><td>Excel</td><td>=IFERROR(MID(A9,FIND(“CH”,A9)+2, LEN(A9)-FIND(“CH”,A9)-2), “”)</td></tr>
<tr><td>Reconcilable</td><td>(EXTRACT FROM [Col1] START AFTER ‘CH’ END BEFORE ‘.’)</td></tr>
</table>

Clearly, building and understanding the EXTRACT function is far simpler than trying to do the same thing using generic text functions, which will translate into quicker, more reliable reconciliations for you.
