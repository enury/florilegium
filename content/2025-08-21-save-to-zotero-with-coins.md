Title: Save to Zotero: make it easy with COinS
Summary: A quick guide to make your HTML page easily saved to Zotero using COinS metadata
Featured_image: images/logo-zotero.png
Date: 2025-08-21
Category: DH

If you are preparing a digital resource and want it to be properly cited, you may want to make it easy for readers to save your page directly to their reference management of choice, e.g. Zotero. One way to do that is to integrate [COinS metadata](https://en.wikipedia.org/wiki/COinS) in the HTML code ([Bleier 2021](https://www.digitalhumanities.org/dhq/vol/15/3/000561/000561.html)).

For the [grammateus](https://grammateus.unige.ch) project, we wanted to make our pages easily saved, to encourage people to cite the content properly. But easier said than done! The COinS website is not accessible anymore, and it is not obvious which field to use for which piece of metadata, in particular the type and the DOI which I needed to include.

After digging around, here is the solution I have found.

## Step by Step

1. Open Zotero and create the ideal citation
2. Export it to COinS
![img](images/zotero-coins-export.png) 
3. If necessary, adapt it with more options: 
    * `rft.type` to specify the [type](https://www.zotero.org/support/kb/item_types_and_fields) of resource (book, webpage, dataset, blog post, document...)
    * `rft.id` to specify the DOI
4. Copy the `span` created to your HTML page
5. Voilà!



## Example

Example from a grammateus [page](https://grammateus.unige.ch/descriptions/warrant):

```
<span class="Z3988" title="url_ver=Z39.88-2004&amp;ctx_ver=Z39.88-2004&amp;rfr_id=info%3Asid%2Fzotero.org%3A2&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Adc&amp;rft.type=webpage&amp;rft_id=info%3Adoi%2Fhttp%3A%2F%2Fdoi.org%2F10.26037/yareta:4bcjmpoy6zavbozlhn46ckrrci&amp;rft.title=Description%20of%20Greek%20Documentary%20Papyri:%20Warrant&amp;rft.source=grammateus%20project&amp;rft.identifier=https://grammateus.unige.ch/descriptions/warrant&amp;rft.aufirst=Gianluca&amp;rft.aulast=Bonagura&amp;rft.au=Gianluca%20Bonagura&amp;rft.au=Ruey-Lin%20Chang&amp;rft.au=Lavinia%20Ferretti&amp;rft.au=Susan%20Fogarty&amp;rft.au=Elisa%20Nury&amp;rft.au=Paul%20Schubert&amp;rft.date=2024&amp;rft.language=en"></span>
```

If you use the Zotero connector to save the page, it should appear properly among your references. Although Zotero is inventing a short title out of thin air, but that is not a big deal.

## Why not meta tags?

When I was looking for options, I started first with the meta tags described on the page for [exposing metadata](https://www.zotero.org/support/dev/exposing_metadata). It might be sufficient in some cases, but I did not find how to specify the type of resource, for instance if I wanted to save a page as a dataset.
