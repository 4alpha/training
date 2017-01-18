[CSS Quick Reference] (http://www.w3schools.com/css/default.asp)

A CSS rule-set consists of a selector and a declaration block:

#1. CSS - selector, declaration { property: value } 

p {
    color: red;
    text-align: center;
}

#2. The id Selector

#para1 {
    text-align: center;
    color: red;
}

#3. The class Selector

.center {
    text-align: center;
    color: red;
}

#4. Grouping Selectors

h1, h2, p {
    text-align: center;
    color: red;
}

#5. CSS Comments

 p {
    color: red;
    /* This is a single-line comment */
    text-align: center;
}

/* This is<br />
a multi-line<br />
comment */

#6. Cascading Order

What style will be used when there is more than one style specified for an HTML element?

Generally speaking we can say that all the styles will "cascade" into a new "virtual" style sheet by the following rules, where number one has the highest priority:

    1. Inline style (inside an HTML element)
       <h1 style="color:blue;margin-left:30px;">This is a heading.</h1>
    2. (in the head section)
       Internal style sheets
       <style>
        h1 {
            color: orange;
        }
        </style>
       and
       External style sheets
       <link rel="stylesheet" type="text/css" href="mystyle.css">
    3. Browser default

So, an inline style (inside a specific HTML element) has the highest priority, which means that it will override a style defined inside the head tag, or in an external style sheet, or a browser default value.

#7. CSS styles

Colors, Backgrounds, Borders, Margins, Paddings, Height & Width

#8. The CSS Box Model

All HTML elements can be considered as boxes. In CSS, the term "box model" is used when talking about design and layout.

The CSS box model is essentially a box that wraps around every HTML element. It consists of: margins, borders, padding, and the actual content. 

