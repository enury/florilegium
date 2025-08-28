Title: Mystical Pelican
Summary: Integrating a IIIF viewer in a pelican blog article
Slug: 2025-10-01-mystical-pelican
Author: Elisa Nury
Date: 2025-10-01
Categories: DH
manifest: images/manifests/mystical-pelican.json
status: draft


I'm interested in using a viewer to display IIIF images for two reasons: first of all because I would not need to worry too much about images rights and also because it would limit the amount of data I have to store myself. The downside is that links to images may cease working in the long term.

### Pelican theme settings
I've downloaded the TwentyFifteen theme and copied the content of `themes/twenteenFifteen` in my github main branch. Then I defined the THEME variable in the configuration file:
`THEME = 'themes/twenteenFifteen'`

### Modifying the theme
In the `base.html` template I added the link to tify's css along with the other stylesheets. 

In `article.html` I included the following code:
```
{% if article.manifest %}
<script src="https://cdn.jsdelivr.net/npm/tify@0.33.0/dist/tify.js"></script>
<script>
new Tify({
  container: '#tify',
  manifestUrl: '{{ article.manifest }}',
})
</script>
{% endif %}
```

It is a very basic solution to start with, allowing one manifest per page. 

For another Pelican plugin with IIIF functionality, see Frederik Elwert's [Pelican Collection Demo](https://github.com/frederik-elwert/pelican-collection-demo)

### Generating manifests

For the manifest generation, I've a set of XQuery functions adapted from e-editiones [TEI Publisher](https://teipublisher.com/exist/apps/tei-publisher/documentation/presentation-manifests), that I run in eXist-db.

I store the generated manifests in the folder `images/manifests`.

I have included as much metadata as possible from the original manifest of the images, but they are not showing up in tify only the full manifest metadata appears in the menu. When I have the time, I'll try to find a solution so that the credits for each image can be found.

And my next goal will be to add annotations to the manifest, so that I can comment on each image individually!

---

Apparently there are not so many (at least easily findable) examples of using a IIIF viewer in a pelican website. My web browser was either focusing on pages about the [Curly-headed Pelican](https://en.wikipedia.org/wiki/Dalmatian_pelican), or IIIF tutorials... Then in a strike of genius, it started to direct me to [Biblissima](https://portail.biblissima.fr/fr/bbma.view?q=p%C3%A9lican+mystique&vid=search-results) pages with these representations of the "mystical pelican", a pelican who is piercing its chest in a Christ-like manner to feed its nestlings.

I definitely need to know more about this! In the meantime, please enjoy this collection of lovely mystical pelicans.

<div id="tify" style="height: 650px"></div>





