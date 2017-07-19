# GrouveeShelves

GrouveeShelves is an implementation of [Grouvee's](grouvee.com) shelf widgets into a simple page which is entirely contained within one HTML file. Just clone the repo and open the Games.html file in a modern browser.

## Configuration

Of course, the shelves included in the repo are my own, and while it may indeed be interesting to follow my progress through my backlog of games, I doubt that's what most users will be very interested in.

I thus recommend you fork the project to create your own personalized page of shelves. The changes needed are fairly easy.

### Tabs

First off, the page is split into two tabs, active and archived. The content of each tab is, unsurprisingly, contained in a .tabcontent div, which contains one or more .grouvee_box div, which are used to split the shelves into columns (the width of which need to be manually defined in CSS, if you can read CSS, this should be fairly easy to figure out).

You can either keep the tabs as they are (easiest, just replace my shelves with your own), remove them (just remove the .tab_bar div), or edit the setup to your liking (won't help you there, can be done fairly easily if you know your HTML/CSS)

Myself, I've split the shelves into "Active" shelves, of games that I'm playing and intend to play in future, and "Archived" shelves, games I've finished or quit.

### Shelves

Inside the .grouvee_box divs you'll find the grouvee widgets, each widget looks like this:

    <div id="grouvee_widget_[shelf id]">
    </div>
    <script src="https://www.grouvee.com/widgets/shelf/[shelf id]/?number=20" type="text/javascript" charset="utf-8"></script>

This is an edited version of the widget as it appears on the Grouvee site, omitting the CSS (which is elsewhere in the file) and the initial shelf content. The widget will fetch the shelf content when the page is loaded.

You'll need to replace the [shelf id] bits with the numerical id of the shelf. This can be found by going to the shelf's page and looking at the URL, which is formatted like so:

    https://www.grouvee.com/user/[username]/shelves/[shelf id]-[shelf name in lower kebab case]/?num=25
    
Just copy the [shelf id] bit from the URL and place it in the two spots (marked in the HTML above with "[shelf id]") in the widget. Do this for each shelf and you're good to go.
