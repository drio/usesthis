A spin-off of the [usesthis](http://usesthis.com/) site.

The Setup is a website of nerdy interviews, asking people what they use to get
the job done. It's a tiny static site, generated by
[Salt](http://github.com/waferbaby/salt/), my equally little site generator.

Interested in cloning the site for your own interviews, similar or otherwise?
HELL YEAH! These are the questions I email people:

	1) Who are you, and what do you do? (Try to keep this brief!)
	2) What hardware do you use?
	3) And what software?
	4) What would be your dream setup?

#### structure:

```
config
        config stuff: currently nginx conf
data/links
        community: other setup pages and personal.
        It will go away?
data/wares
        yml descriptions for hardware and software.
        referenced later on the interviews
lib/
        code that generates the site (uses salt gem)
pages/
        404, about, community, interview landing pages. (erb templating)
posts/
        Markdowns of the interviews. New interviews go here in the format:
        2012-02-22-robert.bohnke.interview

public/
        images and stylesheets
site/
        static generated site.
tasks/
        scripts that use code in lib/ to perform ... tasks.
templates/
        Umm.. templates :)
```

#### tasks

To build the site:

`$ rm -rf site/ ; /usr/local/Cellar/ruby/2.0.0-p247/bin/ruby tasks/build && cd site && python3 -m http.server 7777`
