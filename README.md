Montmartre
==========

Presentation framework inspired by (and borrowing a thing or two from) RevealJS from Hakim el Hattab. 

Use Montmartre whether your presentation is testing the classic boundaries of the presentation paradigm or you want your slide transitions to be controlled even when some of your slides contain complex logic and/or styling. 

Uses BeatMaster as a fundament.


## What does using this bugger solve for me?

> 
>          When the sleigh is heavy
>          and the timber wolves are getting bold,
>          you look at your companions
>          and test the water of their friendship
>          with you toe.
>          They significantly edge
>          closer to the gold.
>          Each man has his price, Bob,
>          and yours was pretty low.
> 
>          Roger Waters (in: Too much rope)
>

Working on and with RevealJS uncovered a few hard to tackle issues:

- for a large deck, the CSS3 animations become a big bother due to artifacts in the overview mode (current Chrome still 'hides' many of your slides when the overview zooms out significantly, say to a width of a slide or 7; this problem is extant since 2011 or thereabouts already) and 

- also the CSS3 animations depend in very subtle ways on when you access the DOM to deliver the size or offset of some element in your code: when your own code does this sort of thing (often **implicitly** thanks to some jQuery plugin or other) the animations might happen.

- as I wanted to keep the slides' JavaScript code manageable through using RequireJS, it clashed with the lazyloader in RevealJS, so I modified RevealJS to be based on RequireJS instead. This is a continuation of that work, which is more suitable for 'large applications development'.


> [*] Yes, yes, I hear y'all and 
> the slaps of [facepalm](http://fc05.deviantart.net/fs71/i/2012/032/3/5/star_trek_facepalm_fail_by_kutpuppy27-d4odfxz.png) 
> all around...
>
> Forget about the Laws of Presenting for a second here and bear with me: 
> I was repurposing the system for other means. The introduction above mentions 'testing the boundaries of the paradigm' for a reason ;-)
>




