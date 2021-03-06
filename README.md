# Bloody Mary

This theme was modified from Casper theme for Ghost blog. The design is the same except for some added features.

### [LIVE DEMO](https://bernardotaveira.com/)

# Added Features

**List of added features:**

- Disqus - add Disqus to posts as a commenting platform (you need to make adjustments described bellow)
- Font Awesome - Added support for [Font Awesome](https://fontawesome.com/)
- Social Links - Added new social buttons (instagram, github...) and support for new ones via font awesome
- Change estimated read time to date of publishing (commit here: [5aa6f73](https://github.com/bertaveira/Bloody-Mary/commit/5aa6f73433bd4db230bf2ea5a2a15809f5c97294) )

# Disqus

In the file post.hbs you have to replace the "EXAMPLE" in `s.src = 'https://EXAMPLE.disqus.com/embed.js';` for your shortname. To get a shortname sign up in the official [Disqus](https://disqus.com/) website.

Example of Disqus code:
```html
<section class="post-full-comments">
<div id="disqus_thread"></div>
<script>
    var disqus_config = function () {
    this.page.url = "{{url absolute="true"}}";
    this.page.identifier = "ghost-{{comment_id}}"
    };
    (function() {
    var d = document, s = d.createElement('script');
    s.src = 'https://EXAMPLE.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
    })();
</script>
</section>
```

# Social Links

For the Social Links you have to edit the file `partials/site-nav.hbs`.

```html
<div class="social-links">
{{#if @site.facebook}}
    <a class="social-link social-link-fb" href="{{facebook_url @site.facebook}}" title="Facebook" target="_blank" rel="noopener">{{> "icons/facebook"}}</a>
{{/if}}
{{#if @site.twitter}}
    <a class="social-link social-link-tw" href="{{twitter_url @site.twitter}}" title="Twitter" target="_blank" rel="noopener">{{> "icons/twitter"}}</a>
{{/if}}
    <a class="social-link social-link-it" href="https://www.instagram.com/bertav.png/" title="Instagram" target="_blank" rel="noopener"><i class="fab fa-instagram"></i></a>
    <a class="social-link social-link-yt" href="https://www.youtube.com/channel/UCbKpGQNwmm1kz2pWdjU8AJQ" title="Youtube" target="_blank" rel="noopener"><i class="fab fa-youtube"></i></a>
    <a class="social-link social-link-vm" href="https://vimeo.com/bertav" title="Vimeo" target="_blank" rel="noopener"><i class="fab fa-vimeo-v"></i></a>
    <a class="social-link social-link-lk" href="https://www.linkedin.com/in/bernardo-taveira/" title="linkedin" target="_blank" rel="noopener"><i class="fab fa-linkedin-in"></i></a>
    <a class="social-link social-link-gh" href="https://github.com/bertaveira" title="Vimeo" target="_blank" rel="noopener"><i class="fab fa-github"></i></a>
</div>
```
This is the section you need to edit! Each line is a social link. Replace the URL in `href="https://github.com/bertaveira"` for example.

If you wish to add another social link that is not here it is simple. Since there is support for Font Awesome just select an icon from their site [HERE](https://fontawesome.com/icons) and copy the html code for it (should look something like this `<i class="fab fa-github"></i>`). Then add this line under the others like it:
```html
<a class="social-link social-link-gh" href="INSER-URL-HERE" title="INSERT-NAME-OF-LINK-(anything you want)" target="_blank" rel="noopener">INSERT-FontAwesome-ICON-CODE-HERE</a>
```
