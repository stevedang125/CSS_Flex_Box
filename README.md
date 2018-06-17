# CSS_Flex_Box
## Advanced Responsive Layout with CSS Flexbox

https://github.com/stevedang125/CSS_Flex_Box.git

### Topics include:

#### 1. Creating Flexbox-powered menus.

#### 2. Building a responsive card layout.

#### 3. Marking up and styling the holy grail layout.

#### 4. Changing displays.

#### 5. Showing and hiding the sidebar.

#### 6. Animating content.

### Quick links:

#### Chapter 3.3: Using Flexbox to create a grid of cards
#### https://github.com/stevedang125/CSS_Flex_Box/blob/chapter3-card-layout/Chapter_03/03_03/CSS/card-styles.css

#### Create evenlt width cards with the same height based on the
#### content's length of the longest article

```
HTML
<section class="cards">
                
    <article class="card">
        <a href="#">
            <figure class="thumbnail">
                <img src="images/cropped/banana-wide.jpg" alt="A banana that looks like a bird">
            </figure>

            <div class="card-content">
                <h2>The Banana Bird</h2>
                <p>This banana looks a lot like a bird, doesn't it? When originally posted there was some debate whether it was a hummingbird, a seagull, or a crow. I stand by my earlier statement that it is a banana.</p>
            </div><!-- .card-content -->
        </a>
    </article><!-- .card -->

</section><!-- section -->
===================================================================
/* Flexbox stuff */

.cards{
    /* Default horizontal items */
    display: flex;
    /* Divide items evenly, but not filled the whole width*/
    justify-content: space-between;
    /* Move items to the next line if there's less space */
    flex-wrap: wrap;
}

.card{
    /* Grow 0, Shrink 1, width 33% with 1em between  */
    flex: 0 1 calc(33% - 1em);
    /* Older browser */
    /* width: calc(33% - 1em); */
}    
```

#### Chapter 3.3: Using Flexbox to add responsive breakpoints
#### https://github.com/stevedang125/CSS_Flex_Box/blob/chapter3-card-layout-responsive-breakpoints/Chapter_03/03_03/CSS/card-styles.css

```
=====================================================================
/*  On mid screen at 640px, 2 columns*/
@media screen and (min-width: 40em){
    .cards{
        /* Default horizontal items */
        display: flex;
        /* Divide items evenly, but not filled the whole width*/
        justify-content: space-between;
        /* Move items to the next line if there's less space */
        flex-wrap: wrap;
        margin-top: -1em;
    }
    
    .card{
        /* Grow 0, Shrink 1, width 50% with 1em between  */
        flex: 0 1 calc(50% - .5em);
        /* Older browser */
        /* width: calc(50% - 1em); */
        margin-bottom: 1em;
    }
}

/* On bigger screen (Desktop) 960px or more 3 columns */
@media screen and (min-width: 60em){
    .cards{
        margin-top: inherit;
    }
    .card{
        /* Grow 0, Shrink 1, width 33% with 1em between  */
        flex: 0 1 calc(33% - 1em);
        /* Older browser */
        /* width: calc(33% - 1em); */
        margin-bottom: 2em;
    }
}
```