# design

static sites are typically simple pages consisting of text where content probably doesn't need to take up multiple pages, most static sites could probably be embedded into a single page.  the whole premise behind static.js is that all content is squeezed into a single page and intelligent client side code helps to navigate and render the right information to the user at the right time, for example, when a user clicks a link to an article, the article has actually already been loaded with the opening of the site, but is merely hidden, but when requested static.js could render this view.  the downside is that this would cause a larger amount of data to be downloaded upfront since the user's getting all the articles as opposed to just downloading a single article, but assuming most static sites are not that massive (mostly text which favorably compresses) and that modern networks including mobile can handle this amount of data very effectively, this would therefore simplify the number of files needed which would lead to simpler caching structures, development processes, maintenance, etc.

static.js is a minimalist framework that can be used to orchestrate navigation and rendering of content.

## rules

* the static compiler should pack all data to js, that way there's more flexibility in rendering views, need to evaluate the memory costs compared to storing things in html
* since all articles are embedded in a single page (index.html), there needs to be a way to navigate via hashtags to each article.  this unique hashtag/id would simply be a 32 character hash of the content
* since the view needs to be manipulated by client side code, there is a short duration of time for the rendering to take place, there should be a simple landing page to cover up this duration
* there is an id called `main` which shows a list of all the article links and can show a brief synopsis of the article
* there is also an id called `page` which shows a singular article
* timestamps for articles should have convenience functions to help make timestamps relative to the user, e.g. since or ago processing (nice to have)
* a method to minimalize client memory like compression should be considered
* article information is already embedded into the page as html
