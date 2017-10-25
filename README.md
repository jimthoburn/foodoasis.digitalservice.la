
# Food Oasis

* [How to make changes](#license)
* [How to develop locally](#how-to-develop-locally)
* [Speeding up Jekyll](#speeding-up-jekyll)
* [Handy guides](#handy-guides)
* [A summary of the project files](#a-summary-of-the-project-files)
* [How to add a new location](#how-to-add-a-new-location)
* [License](#license)


This is a website with a map of food sources in Los Angeles, and list of resources about food deserts and health. You can view the site here…
https://foodoasis.la

## How to make changes

The website is published with [GitHub Pages](https://pages.github.com), and the files are generated with [Jekyll](http://jekyllrb.com).

As you make changes and commit/push them to GitHub, the [staging website](https://staging.foodoasis.la) will automatically update. You can also manually push your changes to the [live website](https://github.com/foodoasisla/foodoasis.la).

## How to develop locally

If you want to see a preview of your changes while you work, you can [run a Jekyll server](https://jekyllrb.com) on your local machine. [Installing Ruby and Jekyll](https://jekyllrb.com/docs/installation/) is a good place to start.

After you have Jekyll installed, you can clone this project with [Git](https://git-scm.com) or [GitHub Desktop](https://desktop.github.com)…

```
git clone https://github.com/foodoasisla/site.git
```

And then start running the Jekyll application like this...

```
jekyll serve
```

## Speeding up Jekyll

Since it takes a while to generate the whole site, you may want to run Jekyll in “incremental“ mode, and use our development configuration file…

```
jekyll build && jekyll serve --config _config_dev.yml --incremental
```

Wow, that’s a lot to remember! We’re using [Node.js](https://nodejs.org) to manage commands like that one for us. If you’d like to do that as well, here are some steps you can follow…

1. Install [Node.js and NPM](https://nodejs.org/en/download/).

2. Install our project’s dependencies...

```
npm install
```

3. Start the application...

```
npm start
```

That will start Jekyll with a special configuration that skips these files (since they take a long time to create)…

```
api/*
locations/*
community-garden/*
farmers-market/*
food-pantry/*
summer-lunch/*
supermarket/*
sitemap.xml
```

If those folders are already present, your local website should still work great (though the files in those folders may not be the latest).

Here’s one more command skips the initial build of those folders, if you want to start up quickly.

```
npm run serve
```

## Handy guides

* [Markdown](https://guides.github.com/features/mastering-markdown/)
* [Liquid](https://shopify.github.io/liquid/)
* [Liquid for Designers](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers)
* [Jekyll](https://jekyllrb.com/docs/home/)

## A summary of the project files

### Files for Jekyll
```
_config.yml
_config_dev.yml
_data/*
_drafts/*
_includes/*
_layouts/*

```

### Files for Node.js
```
package.json
_node/*
```

### Files [generated by Node.js](#how-to-add-a-new-location), for Jekyll
```
_locations/*
_community-garden/*
_farmers-market/*
_food-pantry/*
_summer-lunch/*
_supermarket/*
```

### Files for GitHub
```
README.md
LICENSE
CNAME
```

### Assets
```
assets/css
assets/images
assets/js
```

### Pages
```
index.html
organizations.md
resources.md
about.md
team.md
faqs.md
news.html
add.md
404.md
```

### Pages translated into Spanish
```
es/*
```

### Lists of locations
```
locations/*
community-garden/*
farmers-market/*
food-pantry/*
summer-lunch/*
supermarket/*
```

## How to add a new location

You can add a new location with the [add form](https://foodoasis.la/add/).

If you want to add a lot of new locations at once, these files may help…

```
_node/create-markdown.js
_node/update-markdown.js
```

After you add one or more new locations, run this command to add them to the map…

```
npm run update-paging
```

The markdown files in these folders were initially generated by [Node.js](https://nodejs.org) from the data files in the `_data` folder.

```
_locations/*
_community-garden/*
_farmers-market/*
_food-pantry/*
_summer-lunch/*
_supermarket/*
```

They were created with `_node/create-markdown.js` and updated with `_node/update-markdown.js`, **but have since been edited by hand**.

## License

The code, data and design for this project are available under an [open source license](https://github.com/foodoasisla/site/blob/master/LICENSE). That means you’re free to use them to make a food oasis for your city.

The *Food Oasis Los Angeles* name and logo are copyright Hack for LA c/o Code for America. Please check with us first, before using these on a project.

The icons used in this project came from these two sources…

### Icons by the Noun Project
https://thenounproject.com

[Licensed under Creative Commons](https://thenounproject.zendesk.com/hc/en-us/articles/200509798-What-licenses-do-you-use-)

To use these icons on your project, you may need to [purchase a license from the Noun Project](https://thenounproject.zendesk.com/hc/en-us/articles/200562857-Do-I-have-to-pay-to-use-icons-).

### Icons by Font Awesome, by Dave Gandy
http://fontawesome.io

[Licensed under the SIL OFL 1.1](http://scripts.sil.org/OFL)
