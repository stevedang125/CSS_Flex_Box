# CSS_Flex_Box
https://github.com/stevedang125/CSS_Flex_Box.git
## Advanced Responsive Layout with CSS Flexbox
### Topics include:

#### 1. Creating Flexbox-powered menus.

#### 2. Building a responsive card layout.

#### 3. Marking up and styling the holy grail layout.

#### 4. Changing displays.

#### 5. Showing and hiding the sidebar.

#### 6. Animating content.

### Quick links:

#### Chapter 2.3: Using Flexbox to control single level menu layout
#### https://github.com/stevedang125/CSS_Flex_Box/blob/master/Chapter_02/02_03/CSS/nav-single-level.css
```
/* Styles for Single Level Menu */

@media screen and (min-width: 30em){
    .single-nav ul {
        /* default for flex: align to the left, next to each other */
        display: flex;
        /* make all the items float to the right */
        justify-content: flex-end;
        /* center */
        /* justify-content: center; */
        /* When there is no space for the items, 
        wrap/put them down to another line */
        flex-wrap: wrap;
        /* evenly space  */
        /* justify-content: space-around; */
        /* take away the space on the right and left side  */
        /* justify-content: space-between; */
        
    }

    /* stretch to fit the space */
    .single-nav li{
        /* the justify-content won't work anymore with this line */
        flex: 1 0 auto;
        /* prevent text to float to the left */
        text-align: center;
    }
    
}
====================================================================
<section class="menu-section"> 
    <h2 class="menu-heading">Single Level Menu</h2>
    <nav id="single-nav" class="single-nav menu" role="navigation">
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">Food</a></li>
            <li><a href="#">Classes</a></li>
            <li><a href="#">Recipes</a></li>
            <li><a href="#">News</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav><!-- #single-nav .single-nav -->
</section><!-- menu-section -->
```

#### Chapter 2.4: Using Flexbox to control advanced menu layout
#### https://github.com/stevedang125/CSS_Flex_Box/blob/master/Chapter_02/02_04/CSS/nav-advanced.css
```
/* Styles for Advanced Menu */
.advanced-nav li a {
    /* Default display items by horizontal */
    display: flex;
    /* Items float to the left */
    justify-content: flex-start;
    /* Make the items in here fill out all the available space */
    width: 100%;    
}

.icon {
    /* Increase the size of the icon */
    font-size: 1.8em;
    /* flex-grow: 0;
    flex-shrink: 0;
    width: 1.5em; */
    /* Whatever happens to the flex box, the width of the icon will always be 1.5 ems */
    flex: 0 0 1.5em;

}

.button-text{
    /* Increase the size of the text */
    font-size: 1.8em;
}

/* Sub-title */
.button-text span{
    /* Make it appears on its own line */
    display: block;
    font-size: 40%;
    font-weight: lighter;
    font-style: initial;
}

@media screen and (min-width: 30em){
    .advanced-nav ul{
        /* Horizontal items in the list ul */
        display: flex;
        /* When there is no space, move/put items on the next line */
        flex-wrap: wrap;
        justify-content: center;
    }
    /* When the menu shrinks, it cannot pass 12 ems in width, 
    they will start looking weird if they do */
    /* 1: growth whenever possible */
    /* 12ems: if space available for each item's width is < 12ems,
    wrap down the items, instead of just shrink */
    .advanced-nav li {
        flex: 1 0 12em;
        /* make the items in here become flex, so that it'll fill out available space */
        display: flex;
    }
}

=================================================================
<section class="menu-section">
    <h2 class="menu-heading">Advanced Menu</h2>
    <nav id="advanced-nav" class="advanced-nav menu" role="navigation">
        <ul>
            <li>
                <a href="#">
                    <div class="icon">
                        <i class="fa fa-home"></i>
                    </div>
                    <div class="button-text">
                        Home
                        <span>is where the heart is</span>
                    </div>
                </a>
            </li>
            <li>
                <a href="#">
                    <div class="icon">
                        <i class="fa fa-cutlery"></i>
                    </div>
                    <div class="button-text">
                        Food
                        <span>is nourishment for the soul</span>
                    </div>
                </a>
            </li>

            <li>
                <a href="#">
                    <div class="icon">
                        <i class="fa fa-file-text"></i>
                    </div>
                    <div class="button-text">
                        Recipes
                        <span>guide you on your journey</span>
                    </div>
                </a>
            </li>
            <li>
                <a href="#">
                    <div class="icon">
                        <i class="fa fa-paper-plane"></i>
                    </div>
                    <div class="button-text">
                        News
                        <span>brings new things</span>
                    </div>
                </a>
            </li>
        </ul>
    </nav><!-- #advanced-nav .advanced-nav -->
</section><!-- .menu-section -->
```

#### Chapter 2.5: Using Flexbox to control multilevel menus with dropdowns
#### https://github.com/stevedang125/CSS_Flex_Box/blob/master/Chapter_02/02_05/CSS/nav-multi-level.css
```
html file:
Open/Close behavior for drop down menu
<script type="text/javascript" src="JS/libs/jquery-2.1.3.min.js"></script>
<script type="text/javascript" src="JS/menu-toggle.js"></script>

=====================================================================

CSS:

/* Styles for Single Level Menu */
@media screen and (max-width: 30em){
    .multi-level-nav ul ul li a {
        padding-left: 2em;
    }

    .dropdown-toggle {
        display: none;
    }
}

@media screen and (min-width: 30em){
    /* Adding more code here */
    .multi-level-nav ul {
        /* Default horizontal items */
        display: flex;
        /* Put items to the next line if there's not enough space */
        flex-wrap: wrap;
        /* Justify the content to the left */
        /* justify-content: flex-start; */
        /* Divide evenly but won't fill up the available space  */
        justify-content: space-between;
        
    }   

    .multi-level-nav li {
        /* Fill up all the available space */
        flex: 1 0 auto;
        position: relative;
    }

    li.has-children > a {
        padding-right: 0;
    }

    .multi-level-nav ul ul {
        display: none;
        position: absolute;
        z-index:100;
    }

    .multi-level-nav ul ul li {
        /* Flex items since the changed below, 
        tell them to prevent weird shrink  */
        flex: 1 1 auto;
    }

    .multi-level-nav ul .toggled-on {
        /* Change from block - flex will display the items in the drop down menu,
        match the same width as its parent, Food or Classes Tabs */
        /* display: block; */
        display: flex;
    }

    .dropdown-toggle {
        margin: 0;
        padding: 0 .5em;
        border: 0;
        font-family: 'FontAwesome';
        content: "";
        text-transform: lowercase; /* Stop screen readers to read the text as capital letters */
        background-color: transparent;
    }

    .dropdown-toggle:after {
        position: relative;
        top: 0;
        left: 0;
        width: 42px;
        color: white;
        content: "\f107";
        line-height: 1em;   
    }

    .dropdown-toggle:hover,
    .dropdown-toggle:focus {
        background: hsl(0, 0%, 25%);
    }

    .dropdown-toggle.toggle-on:after {
        content: "\f106";
    }
}

============================================================
<section class="menu-section">
    <h2 class="menu-heading">Multi-level (Drop-Down) Menu</h2>
    <nav id="multi-level-nav" class="multi-level-nav menu" role="navigation">
        <ul>
            <li><a href="#">Home</a></li>
            <li class="has-children">
                <a href="#">Food<button class="dropdown-toggle" aria-expanded="false"><span class="screen-reader-text">Expand child menu</span></button></a>
                <ul class="sub-menu">
                    <li><a href="#">Chef for Hire</a></li>
                    <li><a href="#">Catering</a></li>
                    <li><a href="#">Restaurant</a></li>
                </ul>
            </li>
            <li class="has-children">
                <a href="#">Classes<button class="dropdown-toggle" aria-expanded="false"><span class="screen-reader-text">Expand child menu</span></button></a>
                <ul class="sub-menu">
                    <li><a href="#">Class Schedule</a></li>
                    <li><a href="#">Register</a></li>
                    <li><a href="#">Breakfast Class</a></li>
                    <li><a href="#">Brunch Class</a></li>
                    <li><a href="#">Lunch Class</a></li>
                    <li><a href="#">Dinner Class</a></li>
                    <li><a href="#">Dessert Class</a></li>
                    <li><a href="#">Baking Class</a></li>
                    <li><a href="#">Canning Class</a></li>
                    <li><a href="#">Shopping Class</a></li>
                    <li><a href="#">Tools Class</a></li>
                </ul>
            </li>
            <li><a href="#">About</a>
                <ul class="sub-menu">
                    <li><a href="#">The Eat Story</a></li>
                    <li><a href="#">Meet the Chef</a></li>
                    <li><a href="#">Meet the Team</a></li>
                    <li><a href="#">Our Vendors</a></li>
                    <li><a href="#">Legal</a></li>
                </ul>
            </li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav><!-- #multi-level-nav .multi-level-nav -->
</section><!-- .menu-section -->

```
#### Chapter 2.6: Using Flexbox to create social media menu
#### https://github.com/stevedang125/CSS_Flex_Box/blob/social-media-menu/Chapter_02/02_06/CSS/nav-social.css
```
/* ==================== Flexbox Stuff ============================ */

.social-menu ul{
    /* Default horizontal items */
    display: flex;
    /* Put items to the new line if space shrinks */
    flex-wrap: wrap;
    /* Justify items to the right */
    justify-content: flex-end;
}

/* ==================== This will be used for the mix menu ======== */

<section class="menu-section">
    <h2 class="menu-heading">Social Menu</h2>
    <nav id="social-menu" class="social-menu menu" role="navigation">
        <ul>
            <li><a href="http://twitter.com/mor10"><span class="screen-reader-text">Twitter</span></a></li>
            <li><a href="http://facebook.com"><span class="screen-reader-text">Facebook</span></a></li>
            <li><a href="http://linkedin.com"><span class="screen-reader-text">LinkedIn</span></a></li>
            <li><a href="http://youtube.com"><span class="screen-reader-text">YouTube</span></a></li>
            <li><a href="http://instagram.com"><span class="screen-reader-text">Instagram</span></a></li>
        </ul>
    </nav><!-- .social-menu -->
</section><!-- .menu-section -->
```
#### Chapter 2.7: Using Flexbox to create mixed (social media + dropdowns)
#### https://github.com/stevedang125/CSS_Flex_Box/blob/social-media-menu/Chapter_02/02_06/CSS/nav-social.css
```
/* Styles for mixed menu (drop-down + social) */

/* Get the big div .nav-mixed */
/* Then grab the multi level nav ul and play with it */
.nav-mixed .multi-level-nav ul{
    background: tomato;
}

/* Same here for Social Menu */
.nav-mixed .social-menu ul{
    background: aqua;
}

/* Get the two nav-bar into one line by flex */
.nav-mixed {
    /* Default horizontal items */
    display: flex;
    /* Move items to the next line if there are not enough space */
    flex-wrap: wrap;
    /* Divide evenly the items, but not filled the total width */
    justify-content: space-between;
    background: hsl(0, 0%, 15%);
}
============================================================
<section class="menu-section">
    <h2 class="menu-heading">Mixed Menus (drop-down &#43; social)</h2>
    <div class="nav-mixed menu">
        <nav id="multi-level-nav" class="multi-level-nav" role="navigation">
            <ul>
                <li><a href="#">Home</a></li>
                <li class="has-children">
                    <a href="#">Food<button class="dropdown-toggle" aria-expanded="false"><span class="screen-reader-text">Expand child menu</span></button></a>
                    <ul class="sub-menu">
                        <li><a href="#">Chef for Hire</a></li>
                        <li><a href="#">Catering</a></li>
                        <li><a href="#">Restaurant</a></li>
                    </ul>
                </li>
                <li class="has-children">
                    <a href="#">Classes<button class="dropdown-toggle" aria-expanded="false"><span class="screen-reader-text">Expand child menu</span></button></a>
                    <ul class="sub-menu">
                        <li><a href="#">Class Schedule</a></li>
                        <li><a href="#">Register</a></li>
                        <li><a href="#">Breakfast Class</a></li>
                        <li><a href="#">Brunch Class</a></li>
                        <li><a href="#">Lunch Class</a></li>
                        <li><a href="#">Dinner Class</a></li>
                        <li><a href="#">Dessert Class</a></li>
                        <li><a href="#">Baking Class</a></li>
                        <li><a href="#">Canning Class</a></li>
                        <li><a href="#">Shopping Class</a></li>
                        <li><a href="#">Tools Class</a></li>
                    </ul>
                </li>
                <li><a href="#">About</a>
                    <ul class="sub-menu">
                        <li><a href="#">The Eat Story</a></li>
                        <li><a href="#">Meet the Chef</a></li>
                        <li><a href="#">Meet the Team</a></li>
                        <li><a href="#">Our Vendors</a></li>
                        <li><a href="#">Legal</a></li>
                    </ul>
                </li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav><!-- #multi-level-nav .multi-level-nav -->

        <nav id="social-menu" class="social-menu" role="navigation">
            <ul>
                <li><a href="http://twitter.com"><span class="screen-reader-text">Twitter</span></a></li>
                <li><a href="http://facebook.com"><span class="screen-reader-text">Facebook</span></a></li>
                <li><a href="http://linkedin.com"><span class="screen-reader-text">LinkedIn</span></a></li>
                <li><a href="http://youtube.com"><span class="screen-reader-text">YouTube</span></a></li>
                <li><a href="http://instagram.com"><span class="screen-reader-text">Instagram</span></a></li>
            </ul>
        </nav><!-- .social-menu -->
    </div><!-- .mixed-menu -->
</section><!-- .menu-section -->
```
