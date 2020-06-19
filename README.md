# CSS_Flexbox
CSS flexible box module: layout model Basic 

Requirement from CSS model: 
  -Block, for sections in a webpages 
  -Inline, for text -Table, for  two dimensional table data 
  -Positional, for explicit position of a element 
  
Flexbox Provide: 
  -A lot of flexibility 
  -Arrange items 
  -Spacing 
  -Alignment 
  -Order of items 
  -Bootstrap 4 is built on top of the flex layout
  
Terminology:
    In basic
        Whole outside: flex Container
        Items: flex items

        CSS
        <div class=”container’>
            <div> Item 1</div>
            <div> Item 2</div>
            <div> Item 3</div>
        </div>
Flexbox axes
    Main Axis
    Cross Axis
	
        ....................    Cross Start
        .                  .
        .                  .    
        .                  .    Cross Size
        .                  .
        .                  .    
        ....................    Cross ens
        Main	Main	Main
        start	Size	end	
        
Flex Container Properties
    1.	Display
    2.	Flex-direction
    3.	Flex-wrap
    4.	Flex-flow
    5.	Justify-content
    6.	Align-items
    7.  Align-content
    
    1. Display: Create either a block level or inline level flex container.
        1.  Flex
        2.  Inline-flex

    2. Flex-direction: Sets the direction of the main axis.
        1.  Row
        2.  Row-reverse
        3.  Column
        4.  Column-reverse

    3. Flex-wrap: Control the wrapping of flex item within the container.
        1.  Nowrap
        2.  Wrap
        3.  Wrap-reverse
    By default, flex-direction is row
    But we can wrap column wise also
        ·   Flex-direction: column;
        ·   Height:400px;

    4. Flex-flow: Shorthand for flex direction and flex wrap.
                Flex-flow: <flex-direction> <flex-wrap>

   5. Justify-content: Align items and distribute any extra spacing in the parent container.
    The alignment is always along the main-axis.
        1.  Flex-start
        2.  Flex-end
        3.  Center
        4.  Space-between
        5.  Space-around
        6.  Space-evenly

   6. Align-items: Align items along the cross axis.
        1.  Stretch (default)
        2.  Flex-start
        3.  Flex-end
        4.  Center
        5.  Baseline



   7. Align-content: Aligns lines of content along the cross axis and  distribute any extra spacing in the parent container.
        1.  Stretch (default)
        2.  Flex-start
        3.  Flex-end
        4.  Center
        5.  Space-between
        6.  Space-around
        7.  Space-evenly(works)

    Flex item properties:
    1. 	Order
        Control the order of item in the flex container.
        Take Integer value

    2. 	Flex-grow
        Dictates what amount of the available space inside the flex container the item should take up.
        Relative to the other items in the container.
        Default value is 0 – items do not grow.
        Flex-grow value of 1 – flex items grow evenly.

    3. 	Flex-shrink
        Dictates the shrink factor of the flex items when the default size of flex items is larger than the flex container.
        Relative to the other items in the container
        Default value is 1.

    4. 	Flex-basis
        Set the Initial size of a flex item.
        Pixels, percentages or relative unites.
        Default value is auto.

    5.  Flex
        Short hand for flex grow, flex shrink and flex basis.
        .item {
                    Flex-grow: 2;
                    Flex-shrink: 5;
                    Flex-basis: 200px;
        }
        It is compress by flex
        .item {
                    Flex: 2 5 200px;
        }
        
        Flex: <flex-grow> <flex-shrink> <flex-basis>
        Default values:
        .item {
                    Flex: 0 1 auto;
        }

        Examples:
        1.  Flex: 2; //one value, unitless: flex-grow
        2.  Flex: 10em;
        Flex: 30px; //one value, width/height: flex-basis
        //flex: none | initial | auto;
        3.  Flex: 1 30px; //two value: flex-grow | flex-basis;
        4.  Flex: 2 3; grow | shrink;
        5.  Flex: 2 5 10%; grow | shrink | basis


    6.  Align-self
    Align the items individually.
    Values like auto, flex-start, flex-end, center and stretch.
    Overrides the align-items value of the flex container.
    Use Cases
        1.  Navbar
        2.  Centering item
        3.  Unequal height column and card footers
        
        
Use Cases
    1.	Navbar
    2.	Centering item
    3.	Unequal height column and card footers

   1. Navbar:
    HTML
        <nav>
            <ul>
                <li>Home</li>
                <li>Services</li>
                <li>Products</li>
                <li>Contact</li>
                <li>About Us</li>
            </ul>
        </nav>

    CSS
    nav {
        font-size: 2rem;
        background-color: rgb(181, 181, 211);
        border:0.1rem solid rgb(29, 29, 29);

    }
    nav ul {
        list-style-type: none;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: space-around;
    }
    nav ul li {
        cursor: pointer;
        padding: 0.5rem;
        flex: auto;
        text-align: center;
    }
    nav ul li:hover {
        background-color: rgb(77, 89, 100);
        color: white;
    }

    @media all and (max-width: 600px) {
        nav ul {
            flex-direction: column;
        }
        nav ul li {
            text-align: center;
        }
    }


   2. Centering Item:
    HTML
        <div class="container">
            <div class="item">
                Item
            </div>
        </div>

    CSS
    .container {
        height: 400px;
        width: 400px;
        border: 5px solid black;
        display: flex;
        justify-content: center;
        align-items: center;

    }
    .item {
        height: 80px;
        width: 80px;
        border: 3px solid #ff0000;
        display: flex;
        justify-content: center;
        align-items: center;
    }


   3. Variable Height:
    Example 1:
    HTML
        <div class="container">
            <div class="item1">What is Lorem Ipsum?</div>
            <div class="item1a">Lorem Ipsum is simply dummy text<div>
        </div>

    Basic CSS
    .container {
        font-size: 1.5rem;
    }
    .item1 {
        background-color: lightcoral;
        float: left;
        width: 30%;
    }

    .item1a {
        background-color: lightseagreen;
        float: right;
        width: 70%;
    }

    Flex
    .container {
        font-size: 1.5rem;
        display: flex;
    }
    .item1 {
        background-color: lightcoral;
    }

    .item1a {
        background-color: lightseagreen;
    }


    Example 2:
    HTML
        <div class="cards">
            <div class="card">
                <div class="main-body">
                    <p>What is Lorem Ipsum?</p>
                </div>
                <div class="footer">Footer</div>
            </div>
            <div class="card">
                <div class="main-body">
                    <p>Lorem Ipsum is simply dummy texts</p>
                </div>
                <div class="footer">Footer</div>
            </div>
        </div>

    CSS
    .cards {
        display: flex;
    }
    .card {
        font-size: 1.5rem;
        border: 4px solid rgb(6, 11, 15);
        margin: 5px;
        text-align: center;
        display: flex;
        flex-direction: column;

    }
    .card .footer {
        padding: 5px;
        background-color: rgb(143, 141, 139);
    }
    .card .main-body {
        flex: 1;
    }


    Layout









    HTML
    <body>
        <header class="flex-header">
            HEADER
        </header>
        <main class="flex-main">
            <nav class="flex-nav">
                SIDENAV
            </nav>
            <article class="flex-article">
                MAIN CONTENT
            </article>
            <aside class="flex-aside">
                SIDEBAR
            </aside>
        </main>
        <footer class="flex-footer">
            FOOTER
        </footer>
    </body>

    CSS
    * {
        margin: 2px;
    }

    body {
        font-size: 24px;
        color: white;
        height: 100vh;
        text-align: center;
        display: flex;
        flex-direction: column;
    }

    .flex-header {
        background-color: #5070B5;
        padding-top: 3rem;
        padding-bottom: 3rem;
    }

    .flex-main {
        display: flex;
        flex: 1;
    }

    .flex-nav {
        background-color: rgb(201, 126, 76);
        flex: 1 1 5rem;
        padding-top: 3rem;        
    }

    .flex-article {
        background-color: #a1a1a1; 
        flex: 3 3 ; 
        padding-top: 3rem;    
    }

    .flex-aside {
        background-color: rgb(201, 126, 76);; 
        flex: 1 1 5rem;
        padding-top: 3rem;          
    }

    .flex-footer {
        background-color: #4d4d4d;
        padding-top: 3rem;
        padding-bottom: 3rem;
    }

    @media all and (max-width: 540px) {
        .flex-main {
            flex-direction: column;
        }
    }

