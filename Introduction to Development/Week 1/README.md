# Welcome to the Week 1 of Learner's Space React & NextJS! 

A warm welcome to the course!  This course mostly focuses on React and NextJS, but as you may be aware, they are built on JavaScript, therefore you must master HTML, CSS, and JavaScript from scratch in order to comprehend them.  

This tutorial assumes that you have a basic knowledge of HTML like tags, attributes, etc. If you want to learn about HTML, have a look at [this](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics). You might also want to see aditional resources from [**W3 Schools**](https://www.w3schools.com/htmL/html_basic.asp). If you'd like to learn from a video tutorial, then [**this**](https://www.youtube.com/watch?v=qz0aGYrrlhU&ab_channel=ProgrammingwithMosh) video tutorial is the best to learn the basics in the shortest time possible.  

Outline of our learning goals for this week is as follows:
- Visual Studio Code (VS Code) installation
- CSS
    - Bootstrap
    - Tailwind CSS
- Basics of JavaScript

## Visual Studio Code (VS Code) Installation: 

Microsoft created Visual Studio Code, often known as VS Code, which is a source code editor. Use of it is absolutely free! It includes added features like embedded git, smart suggestions, and debugging. VS Code is a robust IDE that is highly useful for programming. You may choose any other IDE as well, but for the sake of this course, we strongly recommend you guys to use VS Code. We bet you are gonna fall in love with it!

We would learn how to install and set up Visual Studio Code in this session.

It is entirely up to you which approach you choose from the two possible ones. Actually, it makes no difference which approach you take. In order to give you an idea of how quickly and simply packages, applications, and much more can be installed using terminal, we've included two approaches.

The two ways to install VS Code are as follows:

##### Through Graphical User Interface (GUI)
This method is best suited for MacOS and Windows. You can still use this method but if you are a Linux user, you might want to try out the other method as well to have an experience on how useful the terminal is. 
Go onto [**download page**](https://code.visualstudio.com/download) of VS Code community to download the suitable file for your OS. Install the package by following the prompt. Wait for it to install and VIOLA! You're done for now and ready to code!

##### Through Command Line Interface (CLI)


###### For Linux
Type the following code in the terminal:  

`wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -` 

`sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"`  

`sudo apt update`

`sudo apt install code`

By now, VS Code should be installed on your system and you are ready to go code with it.

Since, now we are done with the installation part, you can visit the beginners' guide to VS Code [here](https://code.visualstudio.com/docs/introvideos/basics) in order to get familiar with its use.

## CSS

We have finished installing VS Code and feel comfortable using it. Now that we have VS Code, we can start writing the code. 

So what is CSS?
CSS is the acronym for **Cascading Style Sheet**. 
Cascading Style Sheets is a style sheet language used for describing the presentation of a document written in a markup language such as HTML or XML
CSS actually controls/determines how the webpage looks like, or how the contents of the webpage are displayed like font color, size, background color, div size, hover animations, etc.

There are actually two ways to write CSS code: One that invloves embedding the CSS code in the HTML file itself using the `<style>` tag itself and second: that requires making a new document for CSS with file extension `.css`. 
The second approach is significantly better than the first since it keeps your code clean and helps you organise it better.
We are going to follow the second approach in this tutorial. 

So, the first question: How to make a CSS file and write code in it?
CSS file extension is `.css`. So just think of a name for the file and give it this extension to create an empty CSS file. 
After making the file, all that's left is to get started with writing some CSS code. Have a look [**here**](https://developer.mozilla.org/en-US/docs/Web/CSS) at the CSS documentation to have an in-depth idea of CSS syntax and functionality. 

### Bootstrap

To style our web pages, CSS is a great style-sheet language. However, writing the same type of code repeatedly may get incredibly tedious and exhausting. For instance: Let's say you want to add a navbar to your website, but implementing the corresponding code would undoubtedly take some time, if not a lot. Then, how about a framework that allows you to create a navbar with all of your customizations while using less code? That would be fantastic and time-saving, right?
Bootstrap, a frontend CSS framework, is available to help with that use. A free and open-source CSS framework called Bootstrap is designed for front-end web development that prioritises mobile responsiveness. It includes design templates for typography, forms, buttons, navigation, and other interface elements that are based on HTML, CSS, and JavaScript.

Using Bootstrap saves a lot of time and makes the things a lot easier making it well-worthy to learn. You can start learning about Bootstrap from it's [**documentation**](https://getbootstrap.com/docs/5.2/getting-started/introduction/). If you feel like you need more understanding of Bootstrap, then you can view [**webpage**](https://www.w3schools.com/bootstrap5/) to learn more of it. Also, [**this**](https://youtu.be/-qfEOE4vtxE) video tutorial makes it really indulging and fascinating to learn Bootstrap 5. 

### Tailwind CSS

 In essence, Tailwind CSS is a utility-first CSS framework for quickly creating unique user experiences. It is a low-level CSS framework that is extremely adaptable and provides all the building blocks required to create custom designs without requiring you to struggle to overcome obnoxious opinionated styles.
Why do we need another CSS framework when Bootstrap will do? Well, there are a few major benefits to utilising it over Bootstrap, such as:
 - Tailwind provides predesigned widgets so that users may quickly customise a site's user interface from scratch. Bootstrap, on the other hand, has a selection of pre-styled, responsive, mobile-first components that have a distinct UI kit.
 - Compared to Bootstrap, Tailwind CSS provides far more customization options. 

You can start learning Tailwind CSS by following [**this link**](https://tailwindcss.com/docs/installation). You might also want to view [**this** playlist](https://youtube.com/playlist?list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw) to learn Tailwind CSS. 


