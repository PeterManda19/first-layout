# first-layout
A basic web page layout

A basic layout
To put put basic HTML elements on the screen is easy, but putting elements on specific places on a web page is much harder. Mastering web page layouts is a skill you need to master in your quest of becoming a web developer. In this section we will explore the basics of web layouts using floats, flexbox & grid frameworks such as simplegrid.

Elements on a web page flows from top to bottom by default. To get elements laid out differently some CSS is needed.

This exercise is based of techniques discussed in this article http://learnlayout.com - use it as a reference when needed.

HTML containers
Using container elements is a core technique to master to be able to layout web pages.

Container elements are HTML elements that contains other HTML elements.

Container elements makes it easier to layout web pages. As they can be moved around on the web page with all their containing elements.

A basic web page layout
A basic web page layout might be like this.

A page with:

a header that spans across the top of the page with a menu,
a side bar on the left,
some content to the right of the side bar,
a footer at the bottom that span across the whole page.
When the page is small all the sections display underneath each other.

That means the page is responsive web page. The layout of a Resposive web pages changes based on the width of the web page in the device it's displayed in. When the same web page is open on a PC screen elements might be displayed next to each other, where the same elements might be displayed below each other on the small screen of a smart phone for example.

Creating this layout
To create this web page we will need four container elements:

The main container that will contain all the elements,
a header container that contains,
the header,
and the menu
a content container that contains,
the side-bar container,
the main-content container,
and a footer container that's at the bottom of the page.
Setup files & folders
Create a folder in your projects folder called first-layout. In that folder create a file called index.html - you can use touch index.html

Open the first-layout folder in VS Code from the terminal like this:

code .
Once inside of VS Code open the index.html file and type html:5 and press tab.

This will create the HTML template below:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
Add a style tag to index.html header tag add all the css in there:

<style>

</style>
Create the containers
Create the containers as like this:

<div class="container" >
    <div class="header" >
    
    </div>
    <div class="main" >
        <div class="side-bar" >
    
        </div>
        <div class="content" >
    
        </div>
    </div>
    <div class="footer" >
        
    </div>
</div>
Put content inside the containers
Next let's add some content to the containers.

<div class="container" >
    <div class="header" >
        <h1>Main heading</h1>
        <ul class="menu">
            <li><a href="#" >Menu item 1</a></li>
            <li><a href="#" >Menu item 2</a></li>
            <li><a href="#" >Menu item 3</a></li>
        </ul>
    </div>
    <div class="main" >
        <div class="side-bar" >
            <h2>side bar</h2>
            this is the side bar
        </div>
        <div class="content" >
            <h2>Main content</h2>
            this is the main content
        </div>
    </div>
    <div class="footer" >
        <h4>@footer inc</h4>
    </div>
</div>
Styling each container
Let's style each container to see where each container is located in our layout.


body {
    /* you can use a more complete font-family from VSCode as well */
    font-family: arial;
}

.header {
    background-color: lightgreen;
    padding: 1em;
}

.main {
    background-color : lightseagreen;
}

.footer {
    background-color: lightgreen;
    padding: 1em;
}

Position the side-bar & content
Now position the side-bar next to the content section. Use a float for that.

Float the side-bar to the left. For the float to work you need to give the side-bar element a width as well.

.side-bar {
    float: left;
    width: 25%;
}
The side bar is using 25% of the available screen width currently.

Keep the footer at the bottom
You will note that the footer is not staying at the bottom of the page. And it's messing with the layout of the sidebar. You need to clear the float to keep the footer at the bottom of the page. Use a clearfix on the containing container to fix the layout.

Add this css:

.clearfix {
  overflow: auto;
  zoom: 1;
}
And add the clearfix class to the main containter:

<div class="main clearfix" >
    <!-- content here -->       
</div>
This will push the footer container down. And keep it below the main container.

Add more content
At this stage you should add more text to your side-bar and content elements to see if the layout is working as it should.

Copy the text below once into the side-bar and four times into the content areas.

Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
Pellentesque nec nam aliquam sem et tortor consequat id. 
Elit scelerisque mauris pellentesque pulvinar pellentesque habitant. 
Aliquam ut porttitor leo a. Quis eleifend quam adipiscing vitae proin. 
Ut faucibus pulvinar elementum integer enim neque volutpat. 
Pellentesque diam volutpat commodo sed egestas egestas. 
Vel fringilla est ullamcorper eget nulla facilisi etiam dignissim diam. 
Augue mauris augue neque gravida in fermentum et sollicitudin ac. 
Metus aliquam eleifend mi in. 
Tortor aliquam nulla facilisi cras fermentum odio eu feugiat pretium. 
Lobortis mattis aliquam faucibus purus in massa. 
Morbi tristique senectus et netus et. Sed id semper risus in. 
Ut sem nulla pharetra diam sit. 
Nibh venenatis cras sed felis eget velit aliquet.
How does it look?

Add some space around the edges
The text needs some space around the edges of the side-bar and the content.

Add some space inside the two elements using padding.

.side-bar {
    // other properties
    padding: 1em;
}

.content {
    padding: 1em;
}
Making it responsive
You will note that if you resize the page the containers are staying next to each other.

To fix that you will need to move the css that floats the side-bar next to the content section into a media query.

This media query causes the css to only apply for web pages that is 800px - (800 pixels) or wider. If it's narrower than that the CSS wont apply.

@media(min-width:800px){
    .side-bar {
        float: left;
        width: 25%;
    }
}
Something to try: practice media queries by creating a web page called media.html that change a div's background-color to green (< than 400px) , blue (< than 800px) & orange (> 1000px) . Try it. Let the mentors know if you are getting stuck with this.

Keep the css that adds space around the side-bar outside of the media query.

    .side-bar {
        padding: 1em;
    }
The page will now be responsive and the side-bar will move above the content section on a narrow screen.

Moving the side-bar
Note that you can add the side-bar on the right of the main content page by floating it right instead of left.

Or you could add another content section on the right of the page that is floated right.

Styling the menu
Next style the menubar.

Remove the dots from the list items.

    .menu li {
        list-style: none;
        margin: 0em;
        padding: 0em;
    }
Style the menu URL's

    /* remove the list item dots*/
    .menu li {
        list-style: none;
    }
    
    
    .menu a {
        /* Ensure one can click anyware in the li for the link */
        padding: 1em;
        display: block;
        width: 6em;
    }

    .menu a:hover {
        /* Change the menu color to darker green when hovering over a link*/
        background-color : lightseagreen;
    }
Flexbox
Flexbox is a modern way to layout web pages and can be used instead of floats. Floats & Flexbox can be used together as well though.

Use flexbox to put the menu items next to each other when the screen is wide.

@media(min-width:800px){
    /* Other css is here still */

    .menu {
        display: flex;
    }
}
Deploy to GitHub pages
Deploy this webpage to GitHub using GitHub pages. To do that add the first-layout to GitHub.

Follow this steps in the first-layout folder:

git init
git add .
git commit -m "initial commit"
Now create a new blank GitHub repo in GitHub.

Link this repo to your newly created GitHub repository.

git remote add origin <your github repo link here>
After that's done create a gh-pages branch and change into it.

git branch gh-pages
git checkout gh-pages
git push origin gh-pages
At this point your page should be deployed at: http://<your github username>.github.io/first-layout
