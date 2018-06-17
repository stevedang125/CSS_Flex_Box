# CSS_Flex_Box
Practice for CSS course in Lynda.com.

## Advanced Responsive Layout with CSS Flexbox by Morten Rand-Hendriksen
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
`
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
`

#### Chapter 2.4: Using Flexbox to control advanced menu layout
#### https://github.com/stevedang125/CSS_Flex_Box/blob/master/Chapter_02/02_03/CSS/nav-single-level.css
`
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
`