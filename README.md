Montmartre
==========

Presentation framework inspired by (and borrowing a thing or two, three, four, five from) (RevealJS)[https://github.com/hakimel/reveal.js] from (Hakim el Hattab)[http://lab.hakim.se/]. 

- Use Montmartre whether your presentation is testing the classic boundaries of the presentation paradigm or you want your slide transitions to be controlled even when some of your slides contain complex logic and/or styling. 

- Use Montmartre when your creation is sailing the ambiguous seas between a *presentation* and *website*, where one can reasonably argue that *some material in there is not really a slide* any more, but rather *something else*, i.e. a full-blown web page or form/control surface. 

Montmartre uses (BeatMaster)[https://github.com/GerHobbelt/BeatMaster] as a fundament.


## What does using this bugger solve for me?

> 
>          When the sleigh is heavy
>          and the timber wolves are getting bold,
>          you look at your companions
>          and test the water of their friendship
>          with your toe.
>          They significantly edge
>          closer to the gold.
>          Each man has his price, Bob,
>          and yours was pretty low.
> 
>          Roger Waters (in: Too much rope)
>

Working on and with (RevealJS)[https://github.com/hakimel/reveal.js] (and several other presentation frameworks) uncovered a few hard to tackle issues:

- for a large deck, the CSS3 animations become a big bother due to artifacts in the overview mode.

  Current Chrome still semi-randomly 'hides' many of your slides when the overview zooms out significantly, say to a width of a slide or 7. This problem is extant since 2011 or thereabouts already and still isn't fixed in Canary. 

  > 
  > Do note that this is a *browser* (possibly in conjunction with the *graphics card driver*) issue, *not* a (RevealJS)[https://github.com/hakimel/reveal.js] issue: this issue pops up on many sufficiently complex pages with CSS3 animations.
  > 
  > I have not been able to find a decent fix for this which consistently removes the issue. 
  >
  > All we are left with are hacks, work-arounds and other half-baked nasties. As far as I can tell by now, the issue is due to rear its ugly head once you have CSS3 3D transforms on nested (parent + child / children) DOM elements.
  >

- also the CSS3 animations depend in very subtle ways on when you access the DOM to deliver the size or offset of some element in your code, i.e. on the *exact* moment your code triggers a *repaint*: when your own code does this sort of thing (often **implicitly** thanks to some jQuery plugin or other) the animations might not happen!

  This is not a survivable situation when your presentation happens to be (part of) a complex application where there's a strong demand for treating the various application components as 'black boxes' in order to keep the entire software maintainable. 

  My answer to this conundrum is:

  + on the one side, to use a (BeatMaster)[https://github.com/GerHobbelt/BeatMaster]-like framework and **require** all components used to facilitate the desirable separation of 'repaint-triggering DOM inquiries' (such as `$element.offset()`) and 'DOM changing activity' (e.g. `$el.html(html_string)`) -- which may sound ridiculous but is a major factor to assist achieving good UI/UX performance for complex web apps anywhere, and 

  + on the other hand to fall back to JavaScript-driven animations rather than using the CSS3 animation feature, even while browsers may optimize the latter by using hardware acceleration. (This is similar to using direct CSS3 versus a JavaScript-centric animation framework like (GSAP)[http://greensock.com/gsap].)

- as I wanted to keep the slides' JavaScript code manageable through using (RequireJS)[https://github.com/jrburke/requirejs] and related tooling, it clashed with the lazyloader in (RevealJS)[https://github.com/hakimel/reveal.js], so I modified (RevealJS)[https://github.com/hakimel/reveal.js] to be based on RequireJS instead. 

  This is a continuation of that work, which is more suitable for 'large applications development'.


> [*] Yes, yes, I hear y'all and 
> the slaps of [facepalm](http://fc05.deviantart.net/fs71/i/2012/032/3/5/star_trek_facepalm_fail_by_kutpuppy27-d4odfxz.png) 
> all around...
>
> Forget about the Laws of Presenting for a second here and bear with me: 
> I was re-purposing the system for other means. The introduction above mentions 'testing the boundaries of the paradigm' for a reason ;-)
>




