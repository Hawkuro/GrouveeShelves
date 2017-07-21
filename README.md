# GrouveeShelves

GrouveeShelves is an implementation of [Grouvee's](grouvee.com) shelf widgets into a simple page which is entirely contained within one HTML file. Just clone the repo and open the Games.html file in a modern browser.

## Configuration

Of course, the shelves included in the repo are my own, and while it may indeed be interesting to follow my progress through my backlog of games, I doubt that's what most users will be very interested in.

I thus recommend you fork the project to create your own personalized page of shelves. The changes needed are fairly easy.

First off, open Games.html and head to line 83. There you'll see an object called shelfTabs that looks like this:

    var shelfTabs = {
        "Active": [[141977,142193,142000,141979],[141976,141978]],
        "Archived": [[141975,148530]]
    };

The strings "Active" and "Archived" define the names of the tabs on the page. Each tab will have one or more column of shelves. In the active tab, the first column has four shelves, and the second has two. The archived tab has one column with two shelves.

To make it your own, replace my shelf ids with your own (detailed below), and mix up the tab names and tab/column/row number as you like. Everything is sized automagically, but you can of course take a look at the CSS to tweak the look and sizing.

### Shelf ids

Each shelf has an Id that you'll need to find on your profile. This can be found by going to the shelf's page and looking at the URL, which is formatted like so:

    https://www.grouvee.com/user/[username]/shelves/[shelf id]-[shelf name in lower kebab case]/?num=25
    
Just copy the [shelf id] bit from the URL and place it in the array where you want it to appear. Do this for each shelf you want and you're good to go.

### Settings

Below the shelf tab lists is a small settings object with two settings:

 - `hideEmptyShelves`: Whether or not empty shelves are shown or hidden (default: hide empty shelves)
 - `showTabBar`: Whether or not the tab bar is shown (default: show if there are more than one tab)
