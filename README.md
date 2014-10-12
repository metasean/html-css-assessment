html-css-assessment
===================

Draft of future related blog post...


# Overview

Between homework, classwork, job, and just general life, there won't be a lot of time to do recaps.  Regardless, I'm going to try to knock out an entry each week. It will probably be quick and dirty, with lots of room for improvement, but it will be better than nothing. :-)

Week one was spent covering the fundementals of git, github, html5, and CSS, and slightly beyond fundemantal CSS.  Most of our exercises focused on writing the html and css files for webpage mock-ups.  My favorite exercise was definitely the last one.

The last exercise, replicating the assessment.png had a couple of things I found challenging, including:
 1. Rounding specific corners
 2. The listo logo and icon
 3. Centering lists to the page
 4. The large, outlined "+" graphic
 5. Responsive design

#### The mockup to match:
 <a href="https://raw.githubusercontent.com/metasean/html-css-assessment/master/assessment.png" target="_blank"><img src="https://raw.githubusercontent.com/metasean/html-css-assessment/master/assessment.png" alt="assessment.png" /></a>

# My Challenges

## 1. Rounding specific corners
 
### Challenge

If you take a look at the target layout, you'll notice that the first and last list entries have two each of their corners rounded, while all the other corners for list entries are default 90° angles.

### Result

This turned out to be much easier than I expected!

I used the `:nth-child()` and `last-child` CSS selectors, and corner specific assignment.  The end result was:

``` css
.list .list-item:nth-child(2) {
	border-radius: 4px 4px 0 0 ;
	border-top-width: 2px;
}

.list .list-item:last-child {
	border-radius: 0 0 4px 4px;
}
```

## 2. The listo Logo and Icon

### Challenge

The 'listo' logo and icon are not standard glyphs.  Since we were supposed to do this with html & css, I took the generation of the logo and icon as a challenge.

### Result

My general concept was to take two glyphs that exist and morph them into an acceptable approximation of the listo glyph.  I used the triple equivalent symbol and a simple, lower-case letter "l" with an inverted color-scheme.  Positioning the two base glyphs turned out to be particularly challenging (and time-consuming) because of browser differences.  In the end, I think I did a pretty good job (at least, based on the latest Chrome Canary, Firefox, and Safari browsers).

``` css
.equivalent-symbol {
	z-index: 0;
	position: relative;
}

.equivalent-bar {
	z-index: 1;
	position: relative;
}

.title-bar .equivalent-symbol {
	vertical-align: -0.17em;
	font-size: 3em;
}

.title-bar .equivalent-bar {
	font-size: 1.75em;
	color: #000;
	vertical-align: -.15em;
	margin-left: -0.76em;
}

.button .equivalent-symbol {
	font-size: 1.5em;
	margin-right: -0.6em;
}

.button .equivalent-bar {
	font-size: 1.5em;
}
```

## 3. Centering Lists to the Page

### Challenge

If you look at my result[^will link when I can] and compare it to the target, especially while resizing the browser window, you'll notice that my list cards float to the left while the target image shows them centered, relative to the page.

### Result

I think this should be relatively simple operation, but it's kickin' my brain and I haven't resolved it yet.

Spent a study group trying to address this (including a fair bit of playing with http://the-echoplex.net/flexyboxes).   My "with flexbox" push is the result, but it still isn't what I envision :-(   

## 4. The large, outlined "+" graphic

### Challenge

Like the listo logo and icon, I took the the large, outlined "+" graphic in the "Create New List" box as a challenge.

### Result

Unlike the listo logo and icon, I couldn't just mix and match existing glyphs, but it wasn't for lack of trying.  The real challenge came with making three different glyph classes (one for the inner grey +, one for the middle white +, and one for the outer grey +) that had different and relative sizes, and then getting them to overlap properly.  I still haven't resolved it yet.



## 5. Responsive Design

### Challenge

In this day and age, websites should be responsive and accessible across browsers.  Unfortunately, browser inconsistencies make developing such sites challenging!

### Result

In this case, getting the basic list boxes and the listo logo/icon to be responsive (to screen sizes) and accessible (to user-controlled zooming) took a fair bit of tweek-it time, but it didn't require any super-special skills.

Strangely, getting the link text (`class="button"`) to right-align across browsers took some mental effort. (I think my very exhausted brain was confusing `flex` and `float`.)

# Summary

This was a great exercise, and will probably be one I revisit as a CSS Kata (or would it be a Koan[^kata-vs-koan]).

If anyone has suggestions on how I should tackle the centering of the list boxes or the grey and white plus graphic, I'd love to hear them!  



 [^will link when I can]: I'll link as soon as I can.  Until then, the repo is at https://github.com/metasean/html-css-assessment

 [^kata-vs-koan]: http://codekata.com/kata/kata-kumite-koan-and-dreyfus/