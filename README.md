#DBCSS
When CSS positioning gets hard this may take away some of the pain!


## Inline

Inline is the default value for display and makes the element act something like a span tag where it will display next to the closest child rather than on top.

## <a href="examples/inline-block.html">Inline-Block</a>

Inline block is a very commonly used positioning property for navigation or HTML elements that need to be, as we'd expect, inline with each other. This is done by adding the `display: inline-block;` to each element that you would like inline.

I targeted the HTML `div` element which I do not recommend doing becuase of CSS Specificity. When possible always use a class or id selector.

Something like this:

<pre>
  <code>
  &lt;nav class="navigation"&gt;
    &lt;ul class="nav-links"&gt;
      &lt;li class="nav-items"&gt;&lt;/li&gt;
      &lt;li class="nav-items"&gt;&lt;/li&gt;
      &lt;li class="nav-items"&gt;&lt;/li&gt;
      &lt;li class="nav-items"&gt;&lt;/li&gt;
    &lt;/ul>
  &lt;/nav>
  </code>
</pre>

<pre>
  <code>
  nav .nav-links .nav-items{
    display: inline-block;
  }
  </code>
</pre>

## Block
Display block is a way to ask the HTML element to act as it should and override any default inline style.

## <a href="examples/display-visible.html">Display vs Visibility</a>

Both of these attributes hide the targeted element but in different ways. `display:none;` will hide the element and WILL NOT take up the space it was assigned. `visibility:hidden;` just like `display:none;` but it WILL retain the space that the elemnt was assigned.

## Inherit

Inherit is used exactly as it sounds. It inherits the display or position property from its closest parent.





## <a href="examples/relative.html">Relative Positioning</a>
Relative position does not actually change the position of the element in any kind of way except that the element will be exactly where you define it in your DOM tree.

## <a href="examples/absolute.html">Absolute Positioning</a>

The absolute property is a little tricky but only in a couple ways. Just like relative you have access to the top, right, bottom, left properties. Absolute positioning is contained to its closest parent with a relative position. In this example the closest relative parent is the Window object but if we were to wrap it in a div with position relative it will be contained in it's height and width.
<a href="examples/absolute-2.html">Example</a>

I used an Atomic style format by adding the classes I need in order to place each element where I need it and can now be reused keeping our code DRY for the future.

I also prefer to use percentages when centering an element so I can ensure that the element will be positioned correctly based on most browser resolutions.

## Fixed

The Fixed Position keeps the element in the exact specified location regardless of the browser size, children or parent elements.

## Static

The static property acts just like relative positioning; however, it does not have access to the top, right, bottom, left properties.




## <a href="examples/z-index.html">Z-index</a>

Z-Index is way to tell one HTML element that it should be displayed above or below the element it is layered with. In the example we'd expect the green box to cover the red box without any properties on it. When we add the Z-index property we use a 2 on red and 1 on green which places the red box above the green, which overwrites the default behavior.




## <a href="examples/floats.html">Floats</a>

Floats are worth face value: it has 3 values `none`, `left`, `right`. These all do exactly as they seem, they float the element to the desired side of its parent element. 
* Left floats the element to the furthest left position.
* Right floats the element to the furthest right position.
* None does exactly that and removes any inherited floats depending on CSS Specificity.




## Media Queries

Media queries are the way that we target specific devices with specific browser resolutions. They are commonly and really only ever used for responsive web design and development. In this example I will create a a basic media query for an iPhone 6.


This handles both potrait and landscape but we can also target specific orientatiosn with the `orientation` property.
<pre><code>
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px) 
  and (-webkit-min-device-pixel-ratio: 2) { 
}</code></pre>

### Landscape
<pre><code>
@media only screen 
  and (min-device-width: 375px)
  and (max-device-width: 667px)
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: landscape) {

}
	</code>
</pre>

### Portrait
<pre>
	<code>
@media only screen 
  and (min-device-width: 375px)
  and (max-device-width: 667px)
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: portrait) {
}
	</code>
</pre>