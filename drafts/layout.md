What type of site did I want? I knew I wanted a static blog, and liked the idea [proposed by Chris Holdgraf](https://predictablynoisy.com/posts/2020/sphinx-blogging/)
of using Sphinx with the [ablog extension](https://ablog.readthedocs.io/). In my case, I've never formally documented a Python package before, but it is something I 
look forward to being involved in at some point soon. Getting a handle on Sphinx seemed like a good idea, and the fact that it handled code examples well was a big
plus, as I primarily planned to blog about software engineering. 
The availability of a range of themes to choose from was also a plus, and I really liked Pradyun Gedam's [furo theme](https://pradyunsg.me/furo/). 

I also knew that I wanted a portfolio page, and really appreciated the simplicity of static pages like [Stargirl's](https://thea.codes/stuff.html).

Similarly, I admired static About Me pages like those of [Kenneth Love](https://thekennethlove.com/) and [David Thompson](https://thebeardydeveloper.com/). Particular credit is due to Love for [link styling](https://github.com/kennethlove/kennethlove.github.io/blob/master/themes/editor/static/src/kennethlove.scss).

One thing missing from all of the static sites above, was dynamic content. In addition to static code examples in this blog, I knew I wanted to feature interactive
code experiences as well. I simply love interactive scientific modules like Rowan Cockett's [Taylor Series](https://row1.ca/taylor-series) and Henri Drake's climate
models in Julia. This is how I love to learn, so I needed that ability.

I explored serving it by using Flask's `render_template()` to serve embedded Bokeh apps, as described [here](Bokeh github), but that didn't afford the layout
responsiveness I was after.

Enter React.

When I started this journey I didn't expect to be using JavaScript. But one thing leads to another, and here we are. Generally, I try to choose the most mainstream
tool for a given job, so charts like [this]() were helpful. These [awards](https://www.awwwards.com/websites/reactjsdah/) also gave me a sense of what was
possible. Clearly, React gave room to grow.
