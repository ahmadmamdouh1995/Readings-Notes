### Why pair program?
While learning to code, developers likely study several programming languages. Similar to a foreign language class, there are four fundamental skills that help anyone learn a new language: Listening: hearing and interpreting the vocabulary Speaking: using the correct words to communicate an idea Reading: understanding what written language intends to convey Writing: producing from scratch a meaningful.

### 6 Reasons for Pair Programming:

1. Greater efficiency
It is a common misconception that pair programming takes a lot longer and is less efficient. In reality, when two people focus on the same code base, it is easier to catch mistakes in the making.

2. Engaged collaboration
When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone.

3. Learning from fellow students
Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of.

4. Social skills
Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key. 

5. Job interview readiness
A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen.

6. Work environment readiness
Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. 

### jQuery offers a simple way to achieve a variety of common JavaScript tasks quickly and consistently, across all major browsers and without any fallback code needed.

### WHY USE JQUERY?
1. SIMPLE SELECTORS
As you saw in Chapter 5, which introduced the
DOM, it is not always easy to select the elements
that you want to. For example:
• Older browsers do not support the latest
methods for selecting elements.
• IE does not treat whitespace between elements
as text nodes, while other browsers do.

2. COMMON TASKS IN LESS CODE
There are some tasks that front-end developers
need to do regularly, such as loop through the
elements that have been selected.
jQuery has methods that offer web developers
simpler ways to perform common tasks, such as:
• loop through elements
• Add I remove elements from the DOM tree
• Handle events
• Fade elements into I out of view
• Handle Ajax requests

3. CROSS-BROWSER COMPATIBILITY
jQuery automatically handles the inconsistent ways
in which browsers select elements and handle
events, so you do not need to write cross-browser
fa llback code (such as that shown in the previous
two chapters).

### GETTING ELEMENT CONTENT:

* . html()
When this method is used to retrieve information
from a jQuery selection, it retrieves only the HTML
inside the first element in the matched set, along
with any of its descendants.

* . text()
When this method is used to retrieve the text from
a jQuery selection, it returns the content from every
element in the jQuery selection, along with the text
from any descendants.

### UPDATING ELEMENTS :
* . html()
This method gives every element
in the matched set the same new
content. The new content may
include HTML.

* . text()
This method gives every element
in the matched set the same new
text content. Any markup would
be shown as text.

* .replaceWith()
This method replaces every
element in a matched set with
new content. It also returns the
replaced elements.

* . remove()
This method removes all of the
elements in the matched set.

### CHANGING CSS RULES:
1. The backgroundCo 1 or variable
is created. The jQuery selection
contains all <1 i >elements, and
the . css () method returns the
value of the background-co 1 or
property of the first list item.


2. The background color of
the first list item is written into
the page using the . append"()
method (which you met on
p318). Here, it is used to add
content after the "ul" element.

3. The selector picks all "li"
elements, and then the • css ()
method updates several
properties at the same time:
• The background color is
changed to brown
• A white border is added
• The color of the text is
changed to black
• The typeface is changed to
Georgia
• Extra padding is added on
the left
