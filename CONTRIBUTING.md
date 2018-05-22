# Contributing to the Mount Sion CBS Website

This is a continuous project between student of Mount Sion CBS, it is a learning opportunity where students get industry standard advice and direction while gaining exposure to the best practises in web design and development. Any contributions that will aid the students in their learning experience is welcome

## Prerequisites

The website is built using the Semantic UI framework, if you wish to customise the framework you will need to have the following installed:

- Node (Latest LTS)

Once you have node installed you will need to download and install gulp globally.

```
npm install -g gulp
```

With gulp installed globally, run the following from the root directory of the project:
```
npm install
```
This will install any dependencies needed.

With that done, you can clone down the website, a guide on how to do this can be viewed [here](docs/Tutorial.md)

If you wish to edit/customise the semantic frame work, you will need to navigate to `semantic/src/site/site.variables` here you can edit the color of blue or set other variables, see the semantic [docs](https://semantic-ui.com/usage/theming.html) for more info on this.
Any changes you make to these variables will require you to rebuild the semantic CSS and this can be done in the following directory `semantic/` by running:

```
$ gulp build
```

This will kick off the build and then you will see the changes in your browser, just use semantic as normal in the regular html files.


## Getting Started

Please take some time to read [tutorial](docs/Tutorial.md) to familiarise yourself on how to approach getting set up and cloning the website. We also offer a guide on some common use cases you may encounter while using git, you can use our [guide](docs/git-commands.md) as a point of reference.

The site is built using the Semantic UI Framework. Feel free to flick through their [doc's](https://semantic-ui.com/) if you are not familar with Semantic.

## Issue tracker

All Issues can be tracked in our GitHub Issues, if you find an issue or a bug please feel free to leave an issue and make use of our Issue Template

## Best practices

As this is a learning project for the students of Mount Sion CBS, the best practices in web design and development will be enforced and encouraged at the PR level, it should also be noted this project is aimed for beginners and should be taken into account when reviewing work. 