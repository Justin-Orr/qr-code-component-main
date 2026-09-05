# What you're proud of?

# Would do differently, what challenges you ran into and how you got past them?
### figure element margin issue
The default browser setting for this element was adding default settings
```css
figure {
    margin-block: 1em;
    margin-inline: 40px;
}
```
This led to position issues, and was placed in the `reset.css` file to correct it.
### content-box vs border-box
Wanted to make the padding inside the card 1 rem on all sides and 2.5 rem for the bottom. The size of the overall box of the qr card was stretched to 22 rem instead of 20 rem because the content size and the padding were added together. This is because of `box-sizing` property. Thiss is by default `content-box` which makes the parent container the width if the content inside INCLUDING the padding. To solve this we need to set the `box-sizing` property to `border-box` as shown in the `reset.css`:
```css
*,
*::before,
*::after {
    box-sizing: border-box;
}
```
The tags are used instead of being placed in the root element because `box-sizing` is not an inherited property. Setting `box-sizing` on the root `<html>` element does not automatically make every element use border-box. The tags in the snippet above accounts for every element, every element's `::before` pseudo-element, and every element's `::after` pseudo-element respectively.

# Where you'd like feedback?
- Is the file structure and importing for the css files acceptable for industry standards? Recently I was learning NextJS and the component based structure is similar but for a simple 1 paged application are my files structure considered overkill?
- Should I have reset more elements by default within the reset.css file for good practice?