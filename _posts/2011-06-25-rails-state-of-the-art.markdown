---
layout: post
title: rails state of the art
---

<iframe width="500" height="314" src="http://www.youtube.com/embed/cGdCI2HhfAU?rel=0&amp;hd=1" frameborder="0" allowfullscreen></iframe>

my comment on the somewhat controversal last railsconf talk by rails founder david heinemeier hansson (i recommend you watch his talk first if you haven't yet).

### magic 13

    13 files in one directory -> :(
    13 methods in one class   -> :(

true.

### asset pipeline
nice for big sites like the 37signals ones, but again a hassle for smaller sites. and a lot of sites start rather small. this might push even more developers towards sinatra.

### code cops
and what's about david heinemeier hanssons's initial talk about ruby with freedom and risk and monkeypatching and stuff, now he is talking about laws, enforcements and code cops :(

### asset structure
however filing the js- and css-files in a perfect folder structure on the backend and then serving them combined, minimized (and cached) is rather neat: lower filesize, fewer ttp requests, faster development.

### unix
some critizise that the learning curve for rails is becoming steeper and steeper, possibly turning a lot of developers away from it.

but might this not be just like with unix? a steep learning curve which always pays off in the end? only to a certain extent because unix allows simple flexible solutions whereas rails has this enforcing structure (convention over configuration).

### vendor libraries
divorcing self written js from vendor js libs is a good idea.
now you can install js libs also as gems and don't need to have them hang around in your directory structure. the only downside i see in this is that for quick code lookup in those files while development you have to get it from somewhere else.

and the same works equally well for css frameworks (if you use them^^)

### coffeescript
the inclusion of coffeescript isn't necessary, couldn't the just enable easy coffeescript integration?

-> they help make coffeescript a standard which i myself appreciate

but don't you have to have node.js installed on the server for coffeescript? this could become a huge problem for people tied to shared hosting environments. but hey, lets push those companies towards the future and demand it!

(btw: the coffeescript compiler is written in coffeescript which is totally awesome)

and they have automatic recompilation of changed .coffee-files already built in which is also totally awesome.

### updated generators
when you generate a new controller, the generator autogenerates coffee & scss-files for you. while this could generate some unnecessary files, for the scope of applications rails targets for js is propably needed for every controller.

### automatic parser chaining

    posts.css.scss.erb

this says that posts.css should be parsed by erb and then by scss. thats very nice, dynamic css just got easier.

### default libraries
although scss is the default css library you can easily witch to less e.g. by changing one config file. good for everyone!

### defaults over no-defaults
rails stands for faster and easier development vs for example the classical unix approach: more configuration, but more flexibility. now what do you prefer?

i prefer both. can't we have both?

### framework vs library
framework: have features enabled by default. disable what you don't need
library: have nothing enabled by default. pick and configure what you need.

### middleware
this js/css compiling, minifying, filename-based-caching is cool, but do you know if they have this implemented as an independent racks middleware? would be cool to use in also not-rails-projects.

