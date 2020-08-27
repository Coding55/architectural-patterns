# BEM - Blocks, Elements and Modifiers.

### Blocks:
Standalone entity that is meaningful on its own.
Example:

    <header>

##### Naming

Block names may consist of latin letters, digits, and dashes. To form a CSS class, add a short prefix for namespacing:  `.block`

##### CSS

-   Use class name selector only
-   No tag name or ids
-   No dependency on other blocks/elements on a page

`.block {color: #042;}`

### Elements:
 
A part of a block that has no standalone meaning and is semantically tied to its block.
Example:

    <h3 class="header__title"> This is a header </h3>

##### Naming
Block names may consist of Latin letters, digits, and dashes. To form a CSS class, add a short prefix for namespacing: `.block`
##### CSS

-   Use class name selector only
-   No tag name or ids
-   No dependency on other blocks/elements on a page

**Good**

    .block__elem { color: #042; }

**Bad**

    .block .block__elem { color: #042; }
    	div.block__elem { color: #042; }


### Modifiers:

A flag on a block or element. Use them to change appearance or behavior.
Example:

    <button class="header__button header__button--disabled">
	    No longer available
    </button>

##### Naming

Modifier names may consist of Latin letters, digits, dashes and underscores. CSS class is formed as block’s or element’s name plus two dashes:  `.block--mod`  or  `.block__elem--mod`  and  `.block--color-black`  with  `.block--color-red`. Spaces in complicated modifiers are replaced by dash.

##### CSS

Use modifier class name as selector:

    .block--hidden { }

To alter elements based on a block-level modifier:

    .block--mod .block__elem { }

Element modifier:

    .block__elem--mod { }


# COMPLETE EXAMPLE:

Suppose you have block form with modifiers `theme: "xmas"` and `simple: true` and with elements `input` and `submit`, and element `submit` with its own modifier `disabled: true` for not submitting form while it is not filled

##### HTML

    <form class="form form--theme-xmas form--simple">
      <input class="form__input" type="text" />
      <input
        class="form__submit form__submit--disabled"
        type="submit" />
    </form>

##### CSS

    .form { }
    .form--theme-xmas { }
    .form--simple { }
    .form__input { }
    .form__submit { }
    .form__submit--disabled { }
