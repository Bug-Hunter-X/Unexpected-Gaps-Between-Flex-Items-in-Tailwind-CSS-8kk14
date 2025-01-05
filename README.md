# Unexpected Gaps Between Flex Items in Tailwind CSS

This repository demonstrates a subtle bug in Tailwind CSS related to flexbox layout. When using fractional widths (`w-1/2`, `w-1/3`, etc.) within a flex container, rounding errors can sometimes introduce small gaps between the flex items. This issue is often overlooked and difficult to debug.

## Bug Description
The problem arises from the way browsers handle floating-point numbers in calculating flexbox sizes.  Minor discrepancies in calculations can lead to accumulated gaps, particularly noticeable when using multiple flex items.

## Solution
The solution involves using `space-x-0` (or its equivalents `space-x-reverse-0` and `space-x-0`) utility class to explicitly set the spacing between flex items to zero, overriding the potential gap introduced by the rounding errors. Adding `flex-shrink-0` and `flex-grow-0` to the inner divs can also help resolve the issue.