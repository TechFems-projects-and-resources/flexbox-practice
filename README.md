## Flexbox practice

**Starter code**  

<img src="/starter_code.png" width="400"  />


### The goal of this project is to practice working with Flexbox in CSS

We will use HTML and CSS for our project.

**Basic functionality:** we want to practice using Flexbox with the basic starter code in this repo.

### For starters

1. Create a new folder on your local computer with the name: flexbox-practice.
1. Clone this repository to get the two files with starter code. You can also create an index.html file a style.css file and copy the starter code manually into these files, if you prefer.
1. Run the code with LiveServer, you should see the image above
1. To use Flexbox, you have to add the display property `flex` to the container. The container is the **parent** of the five items (those five are the children elements).
1. The first part of this exercise is about the parent properties: flex-direction, align-items and justify-content.

#### Parent properties

**Flex-direction**  
1. The `flex-direction` property is used to set the horizontal or vertical direction of the items. **Default** direction is `row`. If you add `flex-direction: row` to the CSS code for the container, you will see nothing happens because it is the default.
1. Change the flex-direction to `column` and you will see the items are arranged vertically, in a column. This means you change the **axis** for alignment of items from horizontal (= main axis) to vertical (= cross-axis).
1. If you design an app for a small screen, using `column` will make all items stack on top of each other.
1. Remember: 
  1. when the flex-direction is set to row (= default), the main axis is the horizontal axis (also called x axis).
  1. when the flex-direction is set to column, the main axis is the vertical axis (also called y axis).
1. You can reverse the sequence of the items in the container: try this by adding `row-reverse` (x axis changes from left to right into right to left and items are put in reverse order) or `column-reverse` (y axis changes from bottom to top instead of top to bottom).

**Justify-content**  
1. The `justify-content` property defines how the flex items are stacked along the main axis.
1. Set the flex-direction back to row, and add `justify-content: center` to the CSS for the container. You will see that the items are stacked in the center of the window.
1. The value `center` does not define the space between the items: this is defined by the margin we have set in the `item` selector. You can check this: comment out `margin: 10px;` in the CSS for `.item` and you will see the items are packed together (still centered).
1. Make sure you have uncommented `margin: 10px;` in the CSS for `.item` to continue.
1. Next value is `space-between`. Add `justify-content: space-between` to the CSS for the container. You will see that now the space between the items is **evenly distributed** automatically. **Note:** this also adjusts to the size of the window - it is responsive.
1. Now we will comment out `margin: 10px;` in the CSS for `.item` to show the effect of the next value: `space-around`. Add `justify-content: space-around` to the CSS for the container. You will see that the space between the items changes. It is no longer evenly distributed: Flexbox has now created an **equal amount of space on both the left and right side** of the flex items. The space between the items is twice the amount of the space that is on both the left and right side. Try resizing the browser window to see the effect.
1. There is another value called `space-evenly`. When you use `justify-content: space-evenly`, the space is automatically divided between the items plus the left and right side of the window. This means all spaces are the same.
1. Two more values for `justify-content` that are similar: the `flex-start` and `flex-end` values. Flex-start is the default value. Now uncomment the `margin: 10px;` in the CSS for `.item` so you can see the effect of `justify-content: flex-start`. Then change this to `flex-end` and see the difference.
1. Don't get confused between `row-reverse` and `flex-end`: `row-reverse` will **reverse** (= invert) the order of the flex-items. With `flex-end` you only move the items to the end of the container but the order of the items remains the same.

**Align-items**  
1. Just like `justify-content` aligns the items along the main axis, the `align-items` property aligns the items along the cross axis (the y axis).
1. Try this property out by making one of the items bigger than the rest by using the selector `.items-3` in your CSS and adding `height: 150px;` to this. Also set `justify-content` for the container back to `center`.
1. You will see that all items now have a height of 150 pixels, not just item 3. This happens because the default value is **stretch**. When `align-items` has the default value, the element will stretch to cover from top to bottom.
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

#### Child properties

1. We use the previous code. In the CSS for the container, set `flex-direction: row`, remove the height and set `justify-content:center` and `align-items: center`.
1. 


--- 

### For more advanced students
Build this web page with Flexbox:

<img src="/challenge_image.png" width="700"  />

You can use any picture you like. The pictures you see in the image above, are found when using the searchterm 'box' on Pexels. [This is the website](https://www.pexels.com/search/box/) (some photos may not be for free, so look for the ones you can use for free).

