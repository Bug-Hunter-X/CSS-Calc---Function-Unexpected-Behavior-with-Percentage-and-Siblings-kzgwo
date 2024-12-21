# CSS Calc() Function Unexpected Behavior with Percentage and Siblings

This repository demonstrates an uncommon issue that can arise when using the `calc()` function in CSS with percentage values and sibling selectors.  The problem lies in how the calculation is performed relative to the parent element's width.

## The Problem

The CSS file (`bug.css`) contains a `container` element with a width of 50% and a `sibling` element whose width is calculated using `calc(50% - 10px)`. The expected behavior would be that the sibling is 10px narrower than the container. However, this assumption is only true if the container occupies the full width of its parent. If the parent has padding, margin or other elements that make its available space less than 100%, then the 50% calculation will be relative to the reduced space and the 10px subtraction won't have the expected visual effect.

## The Solution

The solution (`bugSolution.css`) addresses this by ensuring a clear understanding of the context and available width for the calculation.