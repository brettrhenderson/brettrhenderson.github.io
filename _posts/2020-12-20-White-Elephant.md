---
layout: post
title: "Gift Exchange Randomizer"
thumbnail: xmas_tree.jpg
blurb: "A random number generator for a Covid Christmas party, posing as a retro website."
---

{% include image.html url="/images/white_elephant/header.png" description="" width=800 %}


# A Covid Christmas Party
Every year, the Paci research group at UVic holds a Christmas party, complete with white 
elephant gift exchange. Despite the pandemic, this year would be no different. However, 
the mechanics of running a gift exchange would be. We kept our social distance by having
a virtual gathering and arranged for the gifts to be distributed safely after the fact. 
With those particulars decided, we could enjoy each other's company, egg nog in hand, from
the comfort of our own homes. 

# The Rules of Engagement
Before I go any further, it's worth briefly explaining the rules of our gift exchange. These
may differ from how your run your gift exchanges, but who cares! It's meant to be for fun,
anyways. Here they are, in roughly the order that they come up in play. 

1. Everyone who wants to participate buys, makes, or finds a gift (we cap the value at $15).
2. Everyone wraps their gifts and brings them to the gathering, where they are piled in the center of the room.
3. The host fills a hat or bowl with folded strips of paper with numbers on them from 1 to the number
of participants.
4. One by one, participants draw (without peeking) a number from the hat.
5. In number order (lowest to highest), participants have the option to 
    - Unwrap a gift in the center
    - Steal an already unwrapped gift from someone else. However, an individual gift may only be stolen twice.
6. Once everyone has a gift, the exchange is over, and participants take home whatever they ended up with.

At least that's how a game would normally run...

# A Random Conundrum
Obviously some of these game procedures would need to be adapted to a virtual gathering. For one, 
a big part of the normal exchange is that when selecting a wrapped gift, participants can manipulate the
package to get some sense of its contents (at least their mass, whether they're solid, etc.) before selecting
the item. Well, this year we decided that to start the game, everyone would give a vague description of
their gift verbally to allow everyone the same information they could get by feeling. But there was another 
issue as well.

Our normal method of drawing numbers from a hat wouldn't really work. "One person could just draw for everyone!"
you may say. Or "Why not just use a random number generator online!?" you may wonder. Or maybe you come up with
some clever scheme to order by age or name or how close you guess to a number that the gamekeeper has
written down in secret. All fine ideas, I'd say. But I also thought there was a potentially more amusing route
to take. Plus, it was the holidays, and I was very bored...

# The Solution
Instead of taking the easy or the efficient or the smart way, I decided to take the fun way. I wanted
to make a retro-themed website where users could input their gift exchange participant names and get out
a randomized list of numbers to determine the order of the game. I wanted it to be absurdly over-the-top and, 
hopefully, a lot of fun for everyone.

## Using The Flask Web Microframework
First, I downloaded the very simple [Flask template](https://github.com/brettrhenderson/SimpleFlask) that I had 
generated from previous web-based projects. For those unfamiliar, [Flask](https://flask.palletsprojects.com/en/1.1.x/)
is a web microframework for Python. It is a really flexible way to generate web applications with a Python backend
and even has it's own development server for debugging your app locally. Just to be up front here, I am not a 
web developer by any means. I have used Flask for a couple of small projects in the past and found their
documentation and the excellent [Flask Mega-Tutorial](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world)
by Miguel Grinberg to be enough to get going. 

## Moving Pictures
One thing I get a kick out of in a lot of older websites is the number of gifs and animations. I wanted my 
site to have an egregious number of animations, so I started by taking an animated Romanian flag (our research
supervisor is Romanian) and tiling the whole background with it. Flames were also a must, so I threw some in
behind the site heading, with some sparkling gift boxes to really convey the Christmas spirit

{% include image.html url="/images/white_elephant/flames.gif" description="Spicy!" %}

## Obnoxious Font
Naturally, the site also needed some loud, completely unnecessary font, so I went with
[Press Start 2P](https://fonts.google.com/specimen/Press+Start+2P?preview.text_type=custom). For good measure,
I was also sure to add some color changes to the title. Alternating between red and green seemed festive!

{% include image.html url="/images/white_elephant/title_green.png" description="" width=400 %}
{% include image.html url="/images/white_elephant/title_red.png" description="Yep, that's about right." width=400 %}

## Music
I thought a little Christmas music would be a nice touch, so I also added littler music players with some
classic tunes (along with the Romanian national anthem). I played around a little bit with the styling to 
get them to look a bit more retro, too!

{% include audio.html url="/sounds/jingle_bells.mp3" title="Jingle Bells" %}

## Pop-ups
Another I knew the site needed was some pop-ups to distract us from the task at hand. I rigged a couple
of modals to pop up whenever a person drew either the best number (going last) or the worst (going first). 
For the positive pop-up, users were greeted with the sound of trumpets and some fireworks gifs. And for the
sad one, well...they got this (crying sounds not included):
 
{% include image.html url="/images/white_elephant/crybaby.png" description=":(" width=800 %}

## Visitor Count
Finally, I had to add an (artificially padded) visitor counter at the bottom of the page, just to let everyone
know how popular the site was.

{% include image.html url="/images/white_elephant/visitor.png" description="Dang, that's a lot!" width=400 %}

# The Finished Product
Everyone had quite a laugh when I had our research supervisor navigate to where I had hosted
the site and we got a face full of this...

{% include image.html url="/images/white_elephant/finished.png" description="Pretty spiffy, right?...Right?" width=800 %}

Pretty spiffy right? (Jokes). You may notice that there is a checkbox asking whether "John" is playing. This
little Easter egg essentially rigs the game for any participants named "John" to get last choice of gifts.
If you decide to edit the code, you can get it to rig the game for anyone, such as a young child, who might 
get a kick out of getting the coolest gift!


# See It For Yourself
If you want to experience the full glory of the site, you can check it out at 
[pythonanywhere](http://bhenderson.pythonanywhere.com/).

## Run it Locally 
If you think you'd have fun running the code locally and playing around with it, you can run

```
git clone git@github.com:brettrhenderson/WhiteElephant.git
```

Then, set up a virtual environment (I used python 3.8.5 when developing and have not tested with other
releases) and install the dependencies with.

```
pip install -r requirements.txt
```

You can serve up the webpage with

```
python wsgi.py
```

and then navigate to the site at [http://localhost:5000](http://localhost:5000).

Have Fun!