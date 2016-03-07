# Using CSS transitions
One thing I've always been in awe of is the seemless transitions some sites havebetween different styles. I don't think it's super common, or all that noticable for that matter, but it is definitely a nice detail. Recently, I've seen it happen when sites reduce their font sizes on smaller screens for responsive designs. As the screen real estate shrinks, so do font sizes. Typically, the switch is quite abrupt between bigger fonts and the smaller ones. A well placed CSS transition, however, can make it so, so sexy.

The property is actually quite easy. Its one style defintion (well maybe a few if you include vendor prefixing) with three properties if you use the shorthand notation.

This is how you'd define it:
```
.transition {
  transition: [transition property] [transition duration] [transition type]
}
```
The transition property could be set to either all or a specific property, such as font size. The duration is the amount of time you can specify for the transition to take to complete. For the transition type, the most common one seems to be 'ease' and I think it looks really slick.

In order for the transition to take place, there has to be some sort of event to trigger the changes in styling. In the case I listed above, a responsive design would include a media query to detect the width of a browser window. Let's see how the CSS for such a transition could look.

``
.transition {
  font-size: 50px;
  transition: font-size .5s ease;
}

@media all and (max-width: 550px){
  .transition {
    font-size: 36px;
    transition: font-size .5s ease;
  }
}
```
Notice there is a transition on the first definition as well. This is important because a user may size the window back and forth around the 550px mark where the font sizes will change. By stating this in both spots, we ensure that any time the font size changes the transition will take place, making the switch seem much more seemless.

This will be something I'll practice moving foward with my projects. It adds some visual flare to an otherwise boring event. I can't wait to see what else I could use transitions on, because I'm sure it'll be much more than just changes in font-size!
