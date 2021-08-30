## Flexbox practice

**Starter code screenshot:**  

<img src="/starter_code.png" width="500"  />


### The goal of this project is to practice working with Flexbox in CSS

We will use HTML and CSS for our project. After doing the project, have a look at [the best website to test Flexbox](https://flexbox.help/). **Save it in your favourites!**  Also, we have added cheat sheets on how parent and child containers work (see folder cheat-sheets).

**Basic functionality:** we want to practice using Flexbox with the basic starter code in this repo. The instructions are very long this time, because the README contains both explanations and exercises. Feel free to do just one of the sections.

### For starters

1. Clone this repository onto your local computer, to get the two files with starter code. You can also create an index.html file a style.css file yourself, and copy the starter code manually into these files.
1. Run the code with LiveServer, and then you should see the image above
1. To use Flexbox, you have to add the property `display: flex` to the container element from the HTML. The container is the **parent** of the five numbered items (those five are the children, or child elements).
1. The five child elements have a group class (`item`) and in addition a specific class (`item-1`, `item-2`, etc.). With class `item` we can set properties for the group of five items, and with the other class name we can set properties for one specific item.
1. The first part of this exercise is about the parent properties: flex-direction, align-items and justify-content.
1. Don't forget that the **content** of a container determines its size unless you set the size. This can cause surprises sometimes.

---

### Parent properties

**Flex-direction**  
1. The `flex-direction` property is used to set the horizontal or vertical direction of the items. **Default** direction is `row` (horizontal direction). If you add `flex-direction: row` to the CSS code for the container, you will see that nothing happens because it is the default.
1. Change the flex-direction to `column` and you will see the items are arranged vertically, in a column. This means you change the **axis** for alignment of items from horizontal (= main axis) to vertical (= cross-axis).
1. If you design an app for a small screen, using `column` will make all items stack on top of each other.
1. This concept of flex-direction is really important, so remember: 
    1. when the flex-direction is set to row (= default), the main axis is the horizontal axis (also called x axis).
    1. when the flex-direction is set to column, the main axis is the vertical axis (also called y axis).
1. You can reverse the sequence of the items in the container: try this by adding `row-reverse` (the x axis changes from left to right into right to left, and the items are put in reverse order) or `column-reverse` (the y axis changes from bottom to top instead of top to bottom).

**Justify-content**  
1. The `justify-content` property defines how the flex items are stacked along the main axis.
1. Set the flex-direction back to row, and add `justify-content: center` to the CSS for the container. You will see that the items are stacked in the center of the window.
1. The value `center` does not define the space between the items: this is defined by the margin we have set in the `item` selector. You can check this: comment out `margin: 10px;` in the CSS for `.item` and you will see the items are packed together (and still centered).
1. Make sure you have uncommented `margin: 10px;` in the CSS for `.item` before you continue.
1. The next value is `space-between`. Add `justify-content: space-between` to the CSS for the container. You will see that now the space between the items is **evenly distributed** automatically. **Note:** this also adjusts to the size of the window - it is responsive.
1. Now we will comment out `margin: 10px;` in the CSS for `.item` to show the effect of the next value: `space-around`. Add `justify-content: space-around` to the CSS for the container. You will see that the space between the items changes. It is no longer evenly distributed: Flexbox has now created an **equal amount of space on both the left and right side** of the flex items. The space between the items is twice the amount of the space that is on both the left and right side. Try resizing the browser window to see the effect.
1. There is another value called `space-evenly`. When you use `justify-content: space-evenly`, the space is automatically divided between the items plus the left and right side of the window. This means all spaces are the same.
1. Two more values for `justify-content` that are similar: the `flex-start` and `flex-end` values. Flex-start is the default value. Now uncomment the `margin: 10px;` in the CSS for `.item` so you can see the effect of `justify-content: flex-start`. Then change this to `flex-end` and see the difference.
1. Don't get confused between `row-reverse` and `flex-end`: `row-reverse` will **reverse** (= invert) the order of the flex-items. With `flex-end` you only move the items to the end of the container but the order of the items remains the same.

**Align-items**  
1. Just like `justify-content` aligns the items along the main axis, the `align-items` property aligns the items along the cross axis (the y axis).
1. Try this property out by making one of the items bigger than the rest by using the selector `.items-3` in your CSS and adding `height: 150px;` to this. Also set `justify-content` for the container back to `center`.
1. You will see that all items now have a height of 150 pixels, not just item 3. This happens because the default value for `align-items` is **stretch**. When `align-items` has the default value, the flex elements will stretch to cover from top to bottom.
1. Now add `align-items: center` to the CSS for the container. You will now see the difference in height between the items. Because `align-items: center` centers the items across the cross axis, the larger item is centered in perfect alignment with the height of the container.
1. Change the value to `flex-start` and `flex-end`, and see what happens.
1. When `align-items` is used with the `stretch` value, all flex items will match the height of the tallest item. Try this out.
1. The last value for the `align-items` property is called `baseline`. To show the effect, we first increase the font size of an item. Select item four and increase its font size to 70 pixels.
1. Change the value of `align-items` to `baseline`. You will see that it aligns all the flex items along the text inside item four, as if there is an invisible line. The items are aligned according to their baselines (= the line upon which the text 'sits').

**Using align-items and justify-content when the flex-direction is column**  
1. Comment out the CSS for .items-3 and .items-4. You will again see the grey container with five red squares positioned in the middle with some margin between them.
1. Change `flex-direction` to `column`. You will see the main axis has changed to the y axis.
1. The items are now positioned in the center of the container. This is because of `align-items: center`: it centers the items vertically (`justify-content:center` has no effect here, you can check that by commenting it out).
1. Try changing the value to `flex-end` and to `flex-start`, and see how the items are aligned.
1. To test the various justify-content values with `flex-direction: column`, first give the container a height of 1400 pixels.
1. Now change the container CSS to `justify-content: space-between`. You will see that the space between the items has been distributed as before, but in the vertical direction.

---

### Child properties

We use the previous code. In the CSS for the container, set `flex-direction: row`, remove the height and set `justify-content:center` and `align-items: center`.

**Align-self**  
1. The `align-self` property is similar to the `align-items` property. But instead of collectively aligning items, the `align-self` will align only one flex item along the cross axis. **Important**: `align-self` can overrule the `align-items` property that is set in the parent element.
1. To try this out, use the `.item-3` selector and add a height of 150 pixels. This item 3 will be your reference point (more on this later).
1. Apply `align-self` to item 4: use the `.item-4` selector and add the `align-self` property and set this to `flex-start`. Try out `flex-end` as well.
1. Now set the value to `stretch`. You will see that item 4 stretches to the same size as item 3 (that is why it is the reference point).
1. Test out what happens if you use `align-self: space-between` and other values such as `center`, `space-around`, etc.

**Order**  
1. The `order` property is used to change the position of flex items in a parent container.
1. To test this, we are going to create selectors for all flex items and change their order.
1. Add the selectors `.item-1`, `.item-2` and `.item-5`. Remove the code from selectors `.item-3` and `.item-4`. Now you should have selectors for item-1 to item-5.
1. The initial order of the items is set to zero: `order: 0`. This is important: by defaut, we start to count from index 0.
1. We can set the order property for each item and change their position. Now change the order: move item-1 to position 3, item-2 to position 4, item-3 to position 0, item-4 to position 1 and item-5 to position 2.
1. The order of the item numbers in the row is now 3 - 4 - 5 - 1 - 2. Try moving the items in different ways.

**Flex-grow**  
1. First remove all the `order` properties from the five flex items.
1. The `flex-grow` property enables an item to grow. We can specify an integer, just like with the `order` property.
1. We will use this in the `.item` selector: add to the CSS for this selector `flex-grow: 1;`. You will see that all five items have become bigger. They are occupying the **maximum space** available inside the container. If you comment out the `margin: 10px;` again, you will see this better (don't forget to uncomment it again).
1. You can change the value to for example 100, but the result will be the same because the value only matters in relation to the rest.
1. Test how the value matters: add `flex-grow: 3;` to item-4. You will see that item-4 becomes three times bigger than the other items. This means the flex-grow property works relatively. **Important:** because this is also relative to the space, the sizes will change when the window changes. Try resizing your browser window and see what happens, to understand this.

**Flex shorthand property: `flex-grow`, `flex-basis`, `flex-shrink`**  
1. By default, when we use `display: flex` in the parent container, the following values are set: `flex-grow: 0;` `flex-shrink: 1;` `flex-basis: auto;`. Sometimes we want to override these defaults that the child items receive.
1. The `flex` property is a shorthand to set three flex properties at once: the `flex-grow`, `flex-basis` and `flex-shrink` properties. The syntax is `flex: [flex-grow] [flex-shrink] [flex-basis]`. For exampe: `flex: 1 1 150px;` 
1. If you use `flex` with just one value, you automatically declare the flex-grow value.
1. **flex-basis:** the `flex-basis` can be used instead of the `width` property. It can be used with a percentage-based value or a pixel-based value.
1. Test this by adding `flex-basis: 75%;` to the CSS for `.item-5`.
1. **flex-shrink:** the `flex-shrink` property can prevent shrinking of items when reducing the device viewport (screen width).
1. Remove the flex-grow property from item-4 to practice `flex` as shorthand property.
1. Now change the `flex-basis` value for `.item-5` to 700 pixels and slowly make the computer window smaller. You will see that `.item-5` will start shrinking at a certain moment, even though we have set the value to 700px.
1. When we declare the `flex-shrink` property with a value of zero, this shrinking is prevented.
1. The `flex-shrink` property accepts only binary values: one or zero. By default, it is set to 1 and that means the flex item will shrink at a certain point.
1. Now set the `flex-shrink` property to 0 and see what happens when you increase and decrease the screen width.
1. We see that `.item-5` is not shrinking. But it means that the items are overflowing the container (see *Handling many items in a flex container* section for the solution).
1. Each of these shorthand values impact the other and that is why it is recommended to use this shorthand rather than setting these values independently of one another: you will be more aware of how they impact each other.

**Is the flex shorthand confusing you? Let's try another explanation**  
1. You can keep in the back of your mind: `flex: [max] [min] [ideal size];` because that is how the properties [flex-grow] [flex-shrink] [flex-basis] relate. Remember the default values: `flex: 0 1 auto;` And also remember: if the content of a container changes, this can affect the container size - and also impact the way these properties work together.
2. **Flex-grow:** Usually, we do not want an item to grow and that is why the default is: `flex-grow: 0`. With `flex-grow: 1` we allow all the elements to take up an equal portion of the parent element.
3. If you want one item to grow, you can use either one of these two methods:
```css
.child-three {
  flex: 3 1 auto;
}
```
or
```css
.child-three {
  flex-grow: 3;
}
```
4. **Flex-shrink:** The second value in `flex: 0 1 auto;` is for `flex-shrink`. This tells the browser what the minimum size of an element should be. The default value is 1 which means the element will take up the same amount of space always.
5. If we set this second value to 0, the element will not shrink at all. 
6. **Flex-basis:** The third value is for `flex-basis`. This is used to set an element to an ideal size. By default, it is set to auto, which means the element will use the full height or width of the contents.
7. To make all the elements take up the **full space of the parent**, we can set the child elements to `width: 100%`, or we can set `flex-basis: 100%`, or we can set `flex-grow to 1`.
8. If we set a value instead of using `auto`, we want the item to take up that space if possible. If there is not enough space, the element will take up that much space proportionally to the other elements. 

---

### Handling many items in a flex container: flex-wrap
1. Right now, there are five flex items in the container. Add five more in the HTML file (copy/paste and set the class names from item-6 to item-10).
1. Undo the styling of the individual items in your CSS. In the browser, you will now see that nine items have identical size - but not item 10. Remember why this is?
1. Now you have 10 flex items in the container, and when you minimize the browser window the items will start to overflow.
1. The `flex-wrap` property can overcome this issue. Its value is set in the flex container (the parent). The default value is `no-wrap`. Now add `flex-wrap: wrap` to the CSS for the container, and check what happens. 
1. When you delete a property, its value returns to the default value. Delete `flex-grow: 1` from the CSS for `.item`. What happens if `flex-grow` is back to its default?
1. Add CSS for `.item-10` and set `flex` to 1. You will see that item-10 now takes up its maximum space in the row. To see more clearly what is happening, change the padding of `.item` to `padding: 30px;`. Now resize the browser window. You will see that the flex wrap property will automatically wrap the flex items more and more, to ensure the items fit into the container. For this, items are moved to new rows.
1. It is something that can be very useful for responsive design, when there is less space in the screen.
1. Let's test something else. Increase the height of the container, and set it to 600px. You will see that when you make the screen bigger than mobile size, big gaps come up between the rows. Try solving this.
1. Did you manage to fix the issue? We need `align-content: flex-start` for that, as you probably found out. The align-content property aligns the rows on the cross axis (the y axis), and with flex-start the alignment is at the top of the container.
1. Now try some more things yourself: test the `align-items`, `align-self` and `align-content` with different values and see how these work with the flex-wrap.



--- 

### For more advanced students
**Build this webpage with Flexbox:**

<img src="/challenge_image.png" width="800"  />  


You can use any pictures and images you like, but you have to stick to the layout of the page as seen in the example, using Flexbox. The pictures you see in the image above, are found when using the searchterm 'box' on Pexels. [This is the website](https://www.pexels.com/search/box/) (some photos may not be for free, so look for the ones you can use for free). If you do not want to search for pictures, you can use the photos that are in the `assets` folder in this repository.

---
