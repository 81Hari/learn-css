# Suggestions to Organize Your CSS

## Follow Your Team
- Programmer need to follow the standards of the cuurent team.

---

## Use comments to create headers
- It helps the other programmers to read, write and collabrate with your project in ease.
- It also helps the programmer to read the code after months in ease
- Example:
```CSS
/* || RESET */
/* || VARIABLES */
/* || UTILITY CLASSES */
/* || GENERAL STYLES */

```
---
## Sort Properties Alphabetically
- One of the method is to sort properties alphabatically. (There is a pre-defined sort function in VS code(palette)) 
  - It helps to check for double entry
  ```CSS
    {
        display:block;
        min-width:10px;
        min-width:20px; /*Double Entry*/
        text-decoration: none;
    }
  ```
- But each programmer follow thier own order.
---
## Naming Covention
- Larger projects follow a naming convention methodology. 
- For example: BEM - Block, Element, Modifier

## BEM
- We need to start styling from Element, Block and Modifier


    ### **Block**
    - a.k.a Components
    - Next we need to style the .class (Block-Level)

    ### **Modifiers** (Incremental Style Change)
    - Blocks With Modifiers
      - The naming convention recommended for modifiers is use the block-name(Prefix) followed with two hypen(Seperator) followed with modifier-name.
      - **Prefix:** block-name, **Seperator:** -- .
      - <code>block-name--modifier-name</code>
      ```CSS
      .btn{
        /*Block*/
      }
      .btn--secondary{
        /*Modifier*/
      }
      .btn--border-lg {
        /*Modifier*/
        }
      ```
      - ***Note:** Single hypen is ued for joining two words and Double hypen is used to join block and modifier*

    ### **Element**
    - If Element is inside some other element and its dependent on that element then we need to name them with the name of that parent class(Prefix) followed with two underscore(Seperator)  followed with the name of the class.
    - **Prefix:** parent-element-name, **Seperator:** -- .
    ```CSS
        /*
            "nav" and "btn" are inside header.

            - "nav" is used only inside header so it is dependent on header. So we should use the prefix
            - But "btn" is used throughtout CSS, so it can be named independently without the prefix. 
        */
        .header{
            /*Parent Element Class*/
        }

        .header__nav{
            /*Child Element Class*/
        }
        .btn{

        }
    ```
    - Note: we don't need to follow the structure , we just need to add the root elements name as prefix.
        ```HTML
            <header class="header">
                <h1 class="title"></h1>
                <nav class="header__nav">
                    <button class="header__btn"> <!-- we don't need to add prefix like header__nav__btn. We just need to add the root element as prefix--> 
                    </button>
                </nav>
            </header>
        ```

    ---
    # Why <code> .class element </code> is not recommended to use?

    - It is good have specificity equal while nesting
    - Eg:
       ```CSS
            .header button{
                /*
                .header has specificity 10
                 button has specificity 1
                 Total 11

                 Not recommended
                 */
            }

            .header .btn{
                /*
                .header, .btn has specificity 10

                 Recommended
                 */
            }
            
        ```