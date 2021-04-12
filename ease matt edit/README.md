# change log
- 4/11/21: 
    - changed the look of quotes: added left border, removed all font formatting
        - searched for blockquote and removed all properties while adding a border and padding for 3 selectors
    - reduced size of post image 
        - searched for .post-image and modified the following properties for 3 selectors: display, margin-left, margin-right, width (to reduce img then center)
    - had to also remove background-color, as once image was reduced, random background color was showing
        - searched for .u-placeholder and replaced 3 css selectors for background-color 
    - removed box shadow from header 
        - searched for .navbar and var(--navbar-height);box-shadow and replaced 3 css selectors for box-shadow
- 4/10/21: 
    - created default2.hbs, which is the same as default.hbs but does not have the intro text and photo
        - using default2.hbs in: tag.hbs, post.hbs, page.hbs
    - important: if changes are made to default.hbs, check to see if it also needs to be changed in default2.hbs
- 4/10/21: 
    - removed the 'you might also like' from post.hbs
- 4/9/21: 
    - switched the order of "cover" and "body" in default.hbs
        - got started using this guide: https://ghost.org/docs/tutorials/custom-home-page/
        - overall goal is to retain functionality of tagged articles displayed under tags, but remove cover features (cover, description, and search). but couldn't figure out how without potentially impacting other things
    - currently removed cover, description, and search by deleting cover photo here: https://matt-miyano.ghost.io/ghost/#/settings?showBrandingModal=true
- 4/9/21: 
    - adding intro text above "body" in default.hbs    
    - formatted intro text by creating matt.css


# Ease

A versatile theme suitable for documentation. Publish your posts or business information with ease. Completely free and fully responsive, released under the MIT license.

**Demo: https://ease.ghost.io**

&nbsp;

# Instructions

1. [Download this theme](https://github.com/TryGhost/Ease/archive/master.zip)
2. Log into Ghost, and go to the `Design` settings area to upload the zip file

# Search

1. Generate a content API key in `Integrations` section which will be used to fetch posts from your site.
2. Insert the generated key in `Code injection > Site Header` field.

```html
<script>
    var gh_search_key = 'API_KEY';
    var gh_search_migration = 'v1';
</script>
```

The theme generates an index of posts for highly performant search. The index is updated automatically when posts are added or updated. However, it isn't updated when posts are unpublished or deleted.

To force update the index, increment the search index migration version like `'v2'`.

# Development

Styles are compiled using Gulp/PostCSS to polyfill future CSS spec. You'll need [Node](https://nodejs.org/), [Yarn](https://yarnpkg.com/) and [Gulp](https://gulpjs.com) installed globally. After that, from the theme's root directory:

```bash
# Install
yarn

# Run build & watch for changes
$ yarn dev
```

Now you can edit `/assets/css/` files, which will be compiled to `/assets/built/` automatically.

The `zip` Gulp task packages the theme files into `dist/<theme-name>.zip`, which you can then upload to your site.

```bash
yarn zip
```

# PostCSS Features Used

- Autoprefixer - Don't worry about writing browser prefixes of any kind, it's all done automatically with support for the latest 2 major versions of every browser.

# Copyright & License

Copyright (c) 2013-2021 Ghost Foundation - Released under the [MIT license](LICENSE).
