---
title: CSS values and units
slug: Learn/CSS/Building_blocks/Values_and_units
page-type: learn-module-chapter
---

{{LearnSidebar}}{{PreviousMenuNext("Learn/CSS/Building_blocks/Overflowing_content", "Learn/CSS/Building_blocks/Sizing_items_in_CSS", "Learn/CSS/Building_blocks")}}

CSS rules contain [declarations](/en-US/docs/Web/CSS/Syntax#css_declarations), which in turn are composed of properties and values.
Each property used in CSS has a **value type** that describes what kind of values it is allowed to have.
In this lesson, we will take a look at some of the most frequently used value types, what they are, and how they work.

> **Note:** Each [CSS property page](/en-US/docs/Web/CSS/Reference#index) has a syntax section that lists the value types you can use with that property.

<table>
  <tbody>
    <tr>
      <th scope="row">Prerequisites:</th>
      <td>
        Basic computer literacy,
        <a
          href="/en-US/docs/Learn/Getting_started_with_the_web/Installing_basic_software"
          >basic software installed</a
        >, basic knowledge of
        <a
          href="/en-US/docs/Learn/Getting_started_with_the_web/Dealing_with_files"
          >working with files</a
        >, HTML basics (study
        <a href="/en-US/docs/Learn/HTML/Introduction_to_HTML"
          >Introduction to HTML</a
        >), and an idea of how CSS works (study
        <a href="/en-US/docs/Learn/CSS/First_steps">CSS first steps</a>).
      </td>
    </tr>
    <tr>
      <th scope="row">Objective:</th>
      <td>
        To learn about the different types of values and units used in CSS
        properties.
      </td>
    </tr>
  </tbody>
</table>

## What is a CSS value?

In CSS specifications and on the property pages here on MDN you will be able to spot value types as they will be surrounded by angle brackets, such as [`<color>`](/en-US/docs/Web/CSS/color_value) or [`<length>`](/en-US/docs/Web/CSS/length). When you see the value type `<color>` as valid for a particular property, that means you can use any valid color as a value for that property, as listed on the [`<color>`](/en-US/docs/Web/CSS/color_value) reference page.

> **Note:** You'll see CSS value types referred to as _data types_. The terms are basically interchangeable — when you see something in CSS referred to as a data type, it is really just a fancy way of saying value type. The term _value_ refers to any particular expression supported by a value type that you choose to use.

> **Note:** CSS value types tend to be enclosed in angle brackets (`<`, `>`) to differentiate them from CSS properties.
> For example there is a {{cssxref("color")}} property and a [`<color>`](/en-US/docs/Web/CSS/color_value) data type.
> This is not to be confused with HTML elements, as they also use angle brackets, but this is something to keep in mind that the context should make clear.

In the following example, we have set the color of our heading using a keyword, and the background using the `rgb()` function:

```css
h1 {
  color: black;
  background-color: rgb(197, 93, 161);
}
```

A value type in CSS is a way to define a collection of allowable values. This means that if you see `<color>` as valid you don't need to wonder which of the different types of color value can be used — keywords, hex values, `rgb()` functions, etc. You can use _any_ available `<color>` values, assuming they are supported by your browser. The page on MDN for each value will give you information about browser support. For example, if you look at the page for [`<color>`](/en-US/docs/Web/CSS/color_value) you will see that the browser compatibility section lists different types of color values and support for them.

Let's have a look at some of the types of values and units you may frequently encounter, with examples so that you can try out different possible values.

## Numbers, lengths, and percentages

There are various numeric value types that you might find yourself using in CSS. The following are all classed as numeric:

<table class="standard-table no-markdown">
  <thead>
    <tr>
      <th scope="col">Data type</th>
      <th scope="col">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <code><a href="/en-US/docs/Web/CSS/integer">&#x3C;integer></a></code>
      </td>
      <td>
        An <code>&#x3C;integer></code> is a whole number such as
        <code>1024</code> or <code>-55</code>.
      </td>
    </tr>
    <tr>
      <td>
        <code><a href="/en-US/docs/Web/CSS/number">&#x3C;number></a></code>
      </td>
      <td>
        A <code>&#x3C;number></code> represents a decimal number — it may or may
        not have a decimal point with a fractional component. For
        example, <code>0.255</code>, <code>128</code>, or <code>-1.2</code>.
      </td>
    </tr>
    <tr>
      <td>
        <code
          ><a href="/en-US/docs/Web/CSS/dimension">&#x3C;dimension></a></code
        >
      </td>
      <td>
        A <code>&#x3C;dimension></code> is a <code>&#x3C;number></code> with a
        unit attached to it. For example, <code>45deg</code>, <code>5s</code>,
        or <code>10px</code>. <code>&#x3C;dimension></code> is an umbrella
        category that includes the
        <code><a href="/en-US/docs/Web/CSS/length">&#x3C;length></a></code
        >, <code><a href="/en-US/docs/Web/CSS/angle">&#x3C;angle></a></code
        >, <code><a href="/en-US/docs/Web/CSS/time">&#x3C;time></a></code
        >, and
        <code
          ><a href="/en-US/docs/Web/CSS/resolution">&#x3C;resolution></a></code
        >
        types.
      </td>
    </tr>
    <tr>
      <td>
        <code
          ><a href="/en-US/docs/Web/CSS/percentage">&#x3C;percentage></a></code
        >
      </td>
      <td>
        A <code>&#x3C;percentage></code> represents a fraction of some other
        value. For example, <code>50%</code>. Percentage values are always
        relative to another quantity. For example, an element's length is
        relative to its parent element's length.
      </td>
    </tr>
  </tbody>
</table>

### Lengths

The numeric type you will come across most frequently is [`<length>`](/en-US/docs/Web/CSS/length). For example, `10px` (pixels) or `30em`. There are two types of lengths used in CSS — relative and absolute. It's important to know the difference in order to understand how big things will become.

#### Absolute length units

The following are all **absolute** length units — they are not relative to anything else, and are generally considered to always be the same size.

| Unit | Name                | Equivalent to            |
| ---- | ------------------- | ------------------------ |
| `cm` | Centimeters         | 1cm = 37.8px = 25.2/64in |
| `mm` | Millimeters         | 1mm = 1/10th of 1cm      |
| `Q`  | Quarter-millimeters | 1Q = 1/40th of 1cm       |
| `in` | Inches              | 1in = 2.54cm = 96px      |
| `pc` | Picas               | 1pc = 1/6th of 1in       |
| `pt` | Points              | 1pt = 1/72nd of 1in      |
| `px` | Pixels              | 1px = 1/96th of 1in      |

Most of these units are more useful when used for print, rather than screen output. For example, we don't typically use `cm` (centimeters) on screen. The only value that you will commonly use is `px` (pixels).

#### Relative length units

Relative length units are relative to something else, perhaps the size of the parent element's font, or the size of the viewport. The benefit of using relative units is that with some careful planning you can make it so the size of text or other elements scales relative to everything else on the page. Some of the most useful units for web development are listed in the table below.

<table class="standard-table no-markdown">
  <thead>
    <tr>
      <th scope="col">Unit</th>
      <th scope="col">Relative to</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>em</code></td>
      <td>
        Font size of the parent, in the case of typographical properties like
        <code><a href="/en-US/docs/Web/CSS/font-size">font-size</a></code
        >, and font size of the element itself, in the case of other properties
        like <code><a href="/en-US/docs/Web/CSS/width">width</a></code
        >.
      </td>
    </tr>
    <tr>
      <td><code>ex</code></td>
      <td>x-height of the element's font.</td>
    </tr>
    <tr>
      <td><code>ch</code></td>
      <td>
        The advance measure (width) of the glyph "0" of the element's font.
      </td>
    </tr>
    <tr>
      <td><code>rem</code></td>
      <td>Font size of the root element.</td>
    </tr>
    <tr>
      <td><code>lh</code></td>
      <td>Line height of the element.</td>
    </tr>
    <tr>
      <td><code>rlh</code></td>
      <td>Line height of the root element. When used on the <code><a href="/en-US/docs/Web/CSS/font-size">font-size</a></code> or <code><a href="/en-US/docs/Web/CSS/line-height">line-height</a></code
        > properties of the root element, it refers to the properties' initial value.</td>
    </tr>
    <tr>
      <td><code>vw</code></td>
      <td>1% of the viewport's width.</td>
    </tr>
    <tr>
      <td><code>vh</code></td>
      <td>1% of the viewport's height.</td>
    </tr>
    <tr>
      <td><code>vmin</code></td>
      <td>1% of the viewport's smaller dimension.</td>
    </tr>
    <tr>
      <td><code>vmax</code></td>
      <td>1% of the viewport's larger dimension.</td>
    </tr>
    <tr>
      <td><code>vb</code></td>
      <td>1% of the size of the initial containing block in the direction of the root element's <a href="/en-US/docs/Web/CSS/CSS_Logical_Properties#block_vs._inline">block axis</a>.</td>
    </tr>
    <tr>
      <td><code>vi</code></td>
      <td>1% of the size of the initial containing block in the direction of the root element's <a href="/en-US/docs/Web/CSS/CSS_Logical_Properties#block_vs._inline">inline axis</a>.</td>
    </tr>
    <tr>
      <td><code>svw, svh</code></td>
      <td>1% of the <a href="/en-US/docs/Web/CSS/length#relative_length_units_based_on_viewport">small viewport</a>'s width and height, respectively.</td>
    </tr>
    <tr>
      <td><code>lvw, lvh</code></td>
      <td>1% of the <a href="/en-US/docs/Web/CSS/length#relative_length_units_based_on_viewport">large viewport</a>'s width and height, respectively.</td>
    </tr>
    <tr>
      <td><code>dvw, dvh</code></td>
      <td>1% of the <a href="/en-US/docs/Web/CSS/length#relative_length_units_based_on_viewport">dynamic viewport</a>'s width and height, respectively.</td>
    </tr>
  </tbody>
</table>

#### Exploring an example

In the example below, you can see how some relative and absolute length units behave. The first box has a {{cssxref("width")}} set in pixels. As an absolute unit, this width will remain the same no matter what else changes.

The second box has a width set in `vw` (viewport width) units. This value is relative to the viewport width, and so 10vw is 10 percent of the width of the viewport. If you change the width of your browser window, the size of the box should change. However this example is embedded into the page using an [`<iframe>`](/en-US/docs/Web/HTML/Element/iframe), so this won't work. To see this in action you'll have to [try the example after opening it in its own browser tab](https://mdn.github.io/css-examples/learn/values-units/length.html).

The third box uses `em` units. These are relative to the font size. I've set a font size of `1em` on the containing {{htmlelement("div")}}, which has a class of `.wrapper`. Change this value to `1.5em` and you will see that the font size of all the elements increases, but only the last item will get wider, as its width is relative to that font size.

After following the instructions above, try playing with the values in other ways, to see what you get.

{{EmbedGHLiveSample("css-examples/learn/values-units/length.html", '100%', 900)}}

#### ems and rems

`em` and `rem` are the two relative lengths you are likely to encounter most frequently when sizing anything from boxes to text. It's worth understanding how these work, and the differences between them, especially when you start getting on to more complex subjects like [styling text](/en-US/docs/Learn/CSS/Styling_text) or [CSS layout](/en-US/docs/Learn/CSS/CSS_layout). The below example provides a demonstration.

The HTML illustrated below is a set of nested lists — we have two lists in total and both examples have the same HTML. The only difference is that the first has a class of _ems_ and the second a class of _rems_.

To start with, we set 16px as the font size on the `<html>` element.

**To recap, the em unit means "my parent element's font-size"** in the case of typography. The {{htmlelement("li")}} elements inside the {{htmlelement("ul")}} with a `class` of `ems` take their sizing from their parent. So each successive level of nesting gets progressively larger, as each has its font size set to `1.3em` — 1.3 times its parent's font size.

**To recap, the rem unit means "The root element's font-size"** (rem stands for "root em"). The {{htmlelement("li")}} elements inside the {{htmlelement("ul")}} with a `class` of `rems` take their sizing from the root element (`<html>`). This means that each successive level of nesting does not keep getting larger.

However, if you change the `<html>` element's `font-size` in the CSS you will see that everything else changes relative to it — both `rem`- and `em`-sized text.

{{EmbedGHLiveSample("css-examples/learn/values-units/em-rem.html", '100%', 1100)}}

#### Line height units

`lh` and `rlh` are relative lengths units similar to `em` and `rem`. The difference between `lh` and `rlh` is that the first one is relative to the line height of the element itself, while the second one is relative to the line height of the root element, usually `<html>`.

Using these units, we can precisely align box decoration to the text. In this example, we use `lh` unit to create notepad-like lines using [`repeating-linear-gradient()`](/en-US/docs/Web/CSS/gradient/repeating-linear-gradient). It doesn't matter what's the line height of the text, the lines will always start in the right place.

```css hidden
body {
  margin: 0;
  display: grid;
  grid-template-columns: 1fr 1fr;
  padding: 24px;
  gap: 24px;
  background-color: floralwhite;
  font-family: sans-serif;
}

@supports not (height: 1lh) {
  body::before {
    grid-column: 1 / -1;
    padding: 8px;
    border-radius: 4px;
    background-color: tomato;
    color: white;
    content: "You browser doesn’t support lh unit just yet";
  }
}
```

```css
p {
  margin: 0;
  background-image: repeating-linear-gradient(
    to top,
    lightskyblue 0 2px,
    transparent 2px 1lh
  );
}
```

```html
<p style="line-height: 2em">
  Summer is a time for adventure, and this year was no exception. I had many
  exciting experiences, but two of my favorites were my trip to the beach and my
  week at summer camp.
</p>

<p style="line-height: 4em">
  At the beach, I spent my days swimming, collecting shells, and building
  sandcastles. I also went on a boat ride and saw dolphins swimming alongside
  us.
</p>
```

{{EmbedLiveSample("line_height_units", "100%", "370")}}

### Percentages

In a lot of cases, a percentage is treated in the same way as a length. The thing with percentages is that they are always set relative to some other value. For example, if you set an element's `font-size` as a percentage, it will be a percentage of the `font-size` of the element's parent. If you use a percentage for a `width` value, it will be a percentage of the `width` of the parent.

In the below example the two percentage-sized boxes and the two pixel-sized boxes have the same class names. The sets are 40% and 200px wide respectively.

The difference is that the second set of two boxes is inside a wrapper that is 400 pixels wide. The second 200px wide box is the same width as the first one, but the second 40% box is now 40% of 400px — a lot narrower than the first one!

**Try changing the width of the wrapper or the percentage value to see how this works.**

{{EmbedGHLiveSample("css-examples/learn/values-units/percentage.html", '100%', 1000)}}

The next example has font sizes set in percentages. Each `<li>` has a `font-size` of 80%; therefore, the nested list items become progressively smaller as they inherit their sizing from their parent.

{{EmbedGHLiveSample("css-examples/learn/values-units/percentage-fonts.html", '100%', 800)}}

Note that, while many value types accept a length or a percentage, there are some that only accept length. You can see which values are accepted on the MDN property reference pages. If the allowed value includes [`<length-percentage>`](/en-US/docs/Web/CSS/length-percentage) then you can use a length or a percentage. If the allowed value only includes `<length>`, it is not possible to use a percentage.

### Numbers

Some value types accept numbers, without any unit added to them. An example of a property which accepts a unitless number is the `opacity` property, which controls the opacity of an element (how transparent it is). This property accepts a number between `0` (fully transparent) and `1` (fully opaque).

**In the below example, try changing the value of `opacity` to various decimal values between `0` and `1` and see how the box and its contents become more or less opaque.**

{{EmbedGHLiveSample("css-examples/learn/values-units/opacity.html", '100%', 600)}}

> **Note:** When you use a number in CSS as a value it should not be surrounded in quotes.

## Color

There are many ways to specify color in CSS, some of which are more recently implemented than others. The same color values can be used everywhere in CSS, whether you are specifying text color, background color, or whatever else.

The standard color system available in modern computers supports 24-bit colors, which allows the display of about 16.7 million distinct colors via a combination of different red, green and blue channels with 256 different values per channel (256 x 256 x 256 = 16,777,216). Let's have a look at some of the ways in which we can specify colors in CSS.

> **Note:** In this tutorial we will look at the common methods of specifying color that have good browser support; there are others but they don't have as good support and are less common.

### Color keywords

Quite often in examples here in the learn section or elsewhere on MDN you will see the color keywords used, as they are an intuitive way of specifying color. There are a number of these keywords, some of which have fairly entertaining names! You can see a full list on the page for the [`<color>`](/en-US/docs/Web/CSS/color_value) value type.

**Try playing with different color values in the live examples below, to get more of an idea how they work.**

{{EmbedGHLiveSample("css-examples/learn/values-units/color-keywords.html", '100%', 800)}}

### Hexadecimal RGB values

The next type of color value you are likely to encounter is hexadecimal codes. Each hex value consists of a hash/pound symbol (#) followed by six hexadecimal numbers, each of which can take one of 16 values between 0 and f (which represents 15) — so `0123456789abcdef`. Each pair of values represents one of the channels — red, green and blue — and allows us to specify any of the 256 available values for each (16 x 16 = 256).

These values are a bit more complex and less easy to understand, but they are a lot more versatile than keywords — you can use hex values to represent any color you want to use in your color scheme.

{{EmbedGHLiveSample("css-examples/learn/values-units/color-hex.html", '100%', 800)}}

**Again, try changing the values to see how the colors vary.**

### RGB and RGBA values

The third scheme we'll talk about here is RGB. An RGB value is a function — `rgb()` — which is given three parameters that represent the red, green, and blue channel values of the colors, in much the same way as hex values. The difference with RGB is that each channel is represented not by two hex digits, but by a decimal number between 0 and 255 — somewhat easier to understand.

Let's rewrite our last example to use RGB colors:

{{EmbedGHLiveSample("css-examples/learn/values-units/color-rgb.html", '100%', 800)}}

You can pass a fourth parameter to `rgb()`, which represents the alpha channel of the color, which controls opacity. If you set this value to `0` it will make the color fully transparent, whereas `1` will make it fully opaque. Values in between give you different levels of transparency.

> **Note:** Setting an alpha channel on a color has one key difference to using the {{cssxref("opacity")}} property we looked at earlier. When you use opacity you make the element and everything inside it opaque, whereas using RGB with an alpha parameter colors only makes the color you are specifying opaque.

In the example below, we have added a background image to the containing block of our colored boxes. We have then set the boxes to have different opacity values — notice how the background shows through more when the alpha channel value is smaller.

{{EmbedGHLiveSample("css-examples/learn/values-units/color-rgba.html", '100%', 900)}}

**In this example, try changing the alpha channel values to see how it affects the color output.**

> **Note:** In older versions of CSS, the `rgb()` syntax didn't support an alpha parameter - you needed to use a different function called `rgba()` for that. These days you can pass an alpha parameter to `rgb()`, but for backwards compatibility with old websites, the `rgba()` syntax is still supported, and has exactly the same behavior as `rgb()`.

### HSL and HSLA values

An alternative way to specify colors is the HSL color model. Instead of red, green, and blue values, the `hsl()` function accepts hue, saturation, and lightness values, which are used to distinguish between the 16.7 million colors, but in a different way:

- **Hue**: The base shade of the color. This takes a value between 0 and 360, representing the angles around a {{glossary("color wheel")}}.
- **Saturation**: How saturated is the color? This takes a value from 0–100%, where 0 is no color (it will appear as a shade of grey), and 100% is full color saturation
- **Lightness**: How light or bright is the color? This takes a value from 0–100%, where 0 is no light (it will appear completely black) and 100% is full light (it will appear completely white)

We can update the RGB example to use HSL colors like this:

{{EmbedGHLiveSample("css-examples/learn/values-units/color-hsl.html", '100%', 800)}}

Just like with `rgb()` you can pass an alpha parameter to `hsl()` to specify opacity:

{{EmbedGHLiveSample("css-examples/learn/values-units/color-hsla.html", '100%', 900)}}

> **Note:** In older versions of CSS, the `hsl()` syntax didn't support an alpha parameter - you needed to use a different function called `hsla()` for that. These days you can pass an alpha parameter to `hsl()`, but for backwards compatibility with old websites, the `hsla()` syntax is still supported, and has exactly the same behavior as `hsl()`.

You can use any of these color values in your projects. It is likely that for most projects you will decide on a color palette and then use those colors — and your chosen method of specifying color — throughout the whole project. You can mix and match color models, however for consistency it is usually best if your entire project uses the same one!

## Images

The [`<image>`](/en-US/docs/Web/CSS/image) value type is used wherever an image is a valid value. This can be an actual image file pointed to via a `url()` function, or a gradient.

In the example below, we have demonstrated an image and a gradient in use as a value for the CSS `background-image` property.

{{EmbedGHLiveSample("css-examples/learn/values-units/image.html", '100%', 900)}}

> **Note:** There are some other possible values for `<image>`, however these are newer and currently have poor browser support. Check out the page on MDN for the [`<image>`](/en-US/docs/Web/CSS/image) data type if you want to read about them.

## Position

The [`<position>`](/en-US/docs/Web/CSS/position_value) value type represents a set of 2D coordinates, used to position an item such as a background image (via [`background-position`](/en-US/docs/Web/CSS/background-position)). It can take keywords such as `top`, `left`, `bottom`, `right`, and `center` to align items with specific bounds of a 2D box, along with lengths, which represent offsets from the top and left-hand edges of the box.

A typical position value consists of two values — the first sets the position horizontally, the second vertically. If you only specify values for one axis the other will default to `center`.

In the following example we have positioned a background image 40px from the top and to the right of the container using a keyword.

{{EmbedGHLiveSample("css-examples/learn/values-units/position.html", '100%', 800)}}

**Play around with these values to see how you can push the image around.**

## Strings and identifiers

Throughout the examples above, we've seen places where keywords are used as a value (for example `<color>` keywords like `red`, `black`, `rebeccapurple`, and `goldenrod`). These keywords are more accurately described as _identifiers_, a special value that CSS understands. As such they are not quoted — they are not treated as strings.

There are places where you use strings in CSS. For example, [when specifying generated content](/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements#generating_content_with_before_and_after). In this case, the value is quoted to demonstrate that it is a string. In the example below, we use unquoted color keywords along with a quoted generated content string.

{{EmbedGHLiveSample("css-examples/learn/values-units/strings-idents.html", '100%', 600)}}

## Functions

In programming, a function is a piece of code that does a specific task.
Functions are useful because you can write code once, then reuse it many times instead of writing the same logic over and over.
Most programming languages not only support functions but also come with convenient built-in functions for common tasks so you don't have to write them yourself from scratch.

CSS also has [functions](/en-US/docs/Web/CSS/CSS_Functions), which work in a similar way to functions in other languages.
In fact, we've already seen CSS functions in the [Color](#color) section above with [`rgb()`](/en-US/docs/Web/CSS/color_value#rgb_function) and [`hsl()`](/en-US/docs/Web/CSS/color_value#hsl_function) functions.

Aside from applying colors, you can use functions in CSS to do a lot of other things.
For example [Transform functions](/en-US/docs/Web/CSS/CSS_Functions#transform_functions) are a common way to move, rotate, and scale elements on a page.
You might see [`translate()`](/en-US/docs/Web/CSS/transform-function/translate) for moving something horizontally or vertically, [`rotate()`](/en-US/docs/Web/CSS/transform-function/rotate) to rotate something, or [`scale()`](/en-US/docs/Web/CSS/transform-function/scale) to make something bigger or smaller.

### Math functions

When you are creating styles for a project, you will probably start off with numbers like `300px` for lengths or `200ms` for durations.
If you want to have these values change based on other values, you will need to do some math.
You could calculate the percentage of a value or add a number to another number, then update your CSS with the result.

CSS has support for [Math functions](/en-US/docs/Web/CSS/CSS_Functions#math_functions), which allow us to perform calculations instead of relying on static values or doing the math in JavaScript.
One of the most common math functions is [`calc()`](/en-US/docs/Web/CSS/calc) which lets you do operations like addition, subtraction, multiplication, and division.

For example, let's say we want to set the width of an element to be 20% of its parent container plus 100px.
We can't specify this width with a static value — if the parent uses a percentage width (or a relative unit like `em` or `rem`) then it will vary depending on the context it is used in, and other factors such as the user's device or browser window width.
However, we can use `calc()` to set the width of the element to be 20% of its parent container plus 100px.
The 20% is based on the width of the parent container (`.wrapper`) and if that width changes, the calculation will change too:

{{EmbedGHLiveSample("css-examples/learn/values-units/calc.html", '100%', 500)}}

There are many other math functions that you can use in CSS, such as [`min()`](/en-US/docs/Web/CSS/min), [`max()`](/en-US/docs/Web/CSS/max), and [`clamp()`](/en-US/docs/Web/CSS/clamp); respectively these let you pick the smallest, largest, or middle value from a set of values.
You can also use [Trigonometric functions](/en-US/docs/Web/CSS/CSS_Functions#trigonometric_functions) like [`sin()`](/en-US/docs/Web/CSS/sin), [`cos()`](/en-US/docs/Web/CSS/cos), and [`tan()`](/en-US/docs/Web/CSS/tan) to calculate angles for rotating elements around a point, or choose colors that take a [hue angle](/en-US/docs/Web/CSS/hue) as a parameter.
[Exponential functions](/en-US/docs/Web/CSS/CSS_Functions#exponential_functions) might also be used for animations and transitions, when you require very specific control over how something moves and looks.

Knowing about CSS functions is useful so you recognize them when you see them. You should start experimenting with them in your projects — they will help you avoid writing custom or repetitive code to achieve results that you can get with regular CSS.

## Test your skills!

You've reached the end of this article, but can you remember the most important information? You can find some further tests to verify that you've retained this information before you move on — see [Test your skills: Values and units](/en-US/docs/Learn/CSS/Building_blocks/Values_tasks).

## Summary

This has been a quick run-through of the most common types of values and units you might encounter. You can have a look at all of the different types on the [CSS Values and units](/en-US/docs/Web/CSS/CSS_Values_and_Units) reference page — you will encounter many of these in use as you work through these lessons.

The key thing to remember is that each property has a defined list of allowed value types, and each value type has a definition explaining what the values are. You can then look up the specifics here on MDN. For example, understanding that [`<image>`](/en-US/docs/Web/CSS/image) also allows you to create a color gradient is useful but perhaps non-obvious knowledge to have!

In the next article, we'll take a look at how [items are sized](/en-US/docs/Learn/CSS/Building_blocks/Sizing_items_in_CSS) in CSS.

{{PreviousMenuNext("Learn/CSS/Building_blocks/Overflowing_content", "Learn/CSS/Building_blocks/Sizing_items_in_CSS", "Learn/CSS/Building_blocks")}}
