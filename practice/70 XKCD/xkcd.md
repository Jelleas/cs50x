# XKCD

## Goal

Create a website that looks up XKCD comics based on user input. This exercise focuses on learning Flask templates.

## Background

If you don't know the webcomic XKCD, check that out first (and come back to this exercise at some point):
[XKCD](https://xkcd.com/979/)

You're going to work with Flask for this exercise. You might want to have a look at this video:
![embed](https://www.youtube.com/embed/X0dwkDh8kwA)

## Getting started

    cd ~/workspace/practice/
    wget https://cs50x.mprog.nl/course/practice/70%20XKCD/XKCD.zip
    unzip XKCD.zip
    rm XKCD.zip
    cd ~/workspace/practice/XKCD

## Exercise 1

The framework you downloaded consists of two files: A simple webserver, `application.py`; and a Flask-template, `index.html`. You can start the webserver by typing

	$ flask run

in the directory `~/workspace/practice/XKCD`.

### Application

The file `application.py` contains one route for the index, with a both a `POST` and `GET` method. 

- The GET method looks up XKCD comic number 1144 and renders the `index.html` template with this comic.

- The POST method does the same with comic number 1.

### Index

The `index.html` is a template for the index page that displays the comic provided by `application.py`. It also contains a form that is not yet being used.

### Step 1

Run the website by typing `flask run` and have a look at it.

> When you look at the website, what happens when you press the 'enter' key? Why?

### Step 2

Implement the form. In `application.py` read the data from the input field. If it is a number, retrieve the XKCD comic for the corresponding number and display that comic on the website.

> What happens when you enter something else then a number (e.g., the string "hello")?

Make sure your website doesn't crash with invalid input.

> What happens when you enter a number for which there is no XKCD comic?

Make sure it displays an appropriate error message if the comic does not exists.

## Exercise 2

Now we would like to be able to get a whole bunch of comics at once. E.g., if we enter the list `12,13,15` in the input field, it should show all three corresponding comics.

> Before you start implementing, write down on a piece of paper which parts of code should be changed to implement this functionality.

### Step 1

Change the Flask code in such a way that it accepts a list of comma-seperated numbers. Tip: have a look at the python function `split()`: [https://docs.python.org/2/library/stdtypes.html#str.split](https://docs.python.org/2/library/stdtypes.html#str.split).

### Step 2

Retrieve a list of comics corresponding to the provided numbers and pass the comic list to the `render_template()` function. 

### Step 3

Change the `index.html` template in such a way that it first diplays only the first element of the comic list (similar to what you did in Exercise 1).

> What happens when you enter the list `12,13,15`?

> What happens when you enter an empty list?

> What happens when one of the elements in the list is not a number (e.g. "hello")?

### Step 4

Change the `index.html` in such a way that it shows not only the first, but all comics in the list.

## Exercise 3

Add a personal touch to your website.

Have a look at the JSON that is being generated by the XKCD website: [https://xkcd.com/1/info.0.json](https://xkcd.com/1/info.0.json)

It contains more information than only the comic URL and `alt` tag. Think what information you'd find interesting to know about the comic, and display that information along with the image.
