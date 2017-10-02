---
layout: post
title:  "The Call Stack"
date:   2017-10-01 23:41:29 -0400
---


The call stack is a concept in general programming that is useful for understanding recursion.

**Stack** is a simple data structure. It works exactly like how you would imagine it in real life -- when you add an sheet of paper to a stack of papers, it gets added to the top of the stack. When you remove an sheet of paper from a stack of papers, you remove the topmost (most recent) paper. This is essentially two actions: `push` and `pop`.

Computers use an internal stack called the **call stack**. Suppose we have this function:

```
def shoes(kind)
  puts "I will wear #{kind} today."
  shoes_color(kind)
  puts "Have a great day!"
end

def shoes_color(kind)
  puts "My #{kind} today will be brown."
end

shoes("boots")
```

When `shoes("boots")` gets called, the computer allocates a box of memory for the function. Let's pretend this box is a blank sheet of paper. Next, the variable `kind` is set to `boots`. Now, the blank sheet of paper has the words `kind: boots`. This saves in memory and now the sheet of paper is placed on the table to begin the stack.

Next, the computer references that first sheet of paper saved in memory and prints out `I will wear boots today.`

The following line calls the function `shoes_color(kind)`. Since this is a new function call, the computer allocates a new box of memory just like what happened for the first function. In our real life example, this would be a second sheet of paper that is initially blank. The variable `kind` is again, set to `boots` on this second sheet of paper and is subsequently added on top of the first sheet of paper. The stack now has two sheets of paper.

The computer will now have the second sheet of paper to reference since it is now added to the stack. It can now print out `My boots today will be brown.`

Once we return from the `shoes_color` function call, the topmost paper (the second sheet) becomes popped off / removed, leaving the first sheet of paper remaining in the stack.

Since the first function called a second function within it, the first function became paused until the second function completed. It is said to be in a paused state because everything that was saved in memory still exists while the functions on the sheets above it executed.

The first sheet of paper is now unpaused after the sheet on top was removed. Now, `Have a great day!` is printed. We can now return from the function call since there is nothing else to be done. Since we are returning, we now remove the first sheet of paper from the stack.
