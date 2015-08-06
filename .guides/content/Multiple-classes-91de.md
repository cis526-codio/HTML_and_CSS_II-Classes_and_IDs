Here we will see how to use multiple classes in order to achieve what we want.

First example : box-red and box-blue

Let says we want to have to style of boxes around our content some content has red boxes and some other content we will have blue boxes.
The most naive way of doing this would be :

```html
<p class="box-red"> I'm in a red box </p>
<p class="box-blue"> I'm in a blue box </p>
```

With the following css :

```css
.box-red {
  background-color:#e2a5a5;
  padding:20px;
  border:2px solid #960606;
  color:#960606;
}

.box-blue {
  background-color:#a5a8e2;
  padding:20px;
  border:2px solid #080696;
  color:#080696;
}
```

With a result looking like this :

![](.guides/img/illu1.png)

This is working and doesn't seem so bad, but imagine we have a third color "green" on our website and we also have 3 text alignments "left", "center", "right" ...

Using this technique we would end up with the following classes :

`.box-red-left`, `.box-red-center`, `.box-red-right`, `.box-blue-left`, `.box-blue-center`, `.box-blue-right`, `.box-green-left`, `.box-green-center`, `.box-green-right`

That's a lot of css classes and a lot of repetitions in the css, moreover it's not very "maintainable" .. What happens if the designer decides to change the shade of the colors ? We have to go and modify so many css classes ...

Here is a better way to do it, using multiple css classe :

```html
<p class="box red left"> I'm in a red box on the left </p>
<p class="box blue center"> I'm in a red box in the center </p>
<p class="box green right"> I'm in a green box on the right </p>
```
With the following css :
```css
.box {
  padding:20px;
  border-width:2px;
  border-style:solid;
}
.red {
  color:#960606;
  background-color:#e2a5a5;
  border-color:#960606;   
}
.blue {
  color:#080696;
  background-color:#a5a8e2;
  border-color:#080696;
}
.green {
  color:#069625;
  background-color:#a7e2a5;
  border-color:#069625;
}
.left { text-align:left; }
.right { text-align:right; }
.center { text-align:center; }
```

Which will look like this :

![](.guides/img/illu2.png)

And now if the designer wants to change the shade of the red color, we just have one class to change `.red` and it will be applied everywhere .. That's much more maintainable. Moreover there is absolutely zero repetitions.

|||info
### A little side note on how to layout your css rules

As you have seen in the previous css code, you can either write your rule on 1 line or on many lines. 

For example you can write :

```css
.green { color:#069625; background-color:#a7e2a5; border-color:#069625; }
```

Or : 

```css
.green { 
  color:#069625; 
  background-color:#a7e2a5; 
  border-color:#069625; 
}
```

The second option is recommanded, simply because it is more readable.

It is accepted to put a css rule on one line only when there is only one property in it, like this :

```css
.left { text-align:left; }
```

Any of these techniques will give the same result in the browser, but it is recommended to use the most readable way !

|||

Let's head to the next section for a little challenge about these concepts !

