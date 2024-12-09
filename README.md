# Lua pairs iterator skipping elements during modification

This repository demonstrates a common error in Lua involving the `pairs` iterator and table modification.  The `pairs` iterator can skip elements if the table being iterated over is modified during iteration.  This is particularly problematic in recursive functions where a modification in a subtable can cause the main iterator to lose track of elements.

The example shows a simple recursive function that iterates through a nested table.  Under normal circumstances, it would print all the values.  However, the modification of a subtable during iteration causes the problem shown in `bug.lua`.

The solution (`bugSolution.lua`) demonstrates a safe approach using a copy of the table to prevent the modification issue.