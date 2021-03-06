# Chi Hack Night website

Website for [Chi Hack Night](http://chihacknight.org/).

**Chi Hack Night** is Chicago's weekly event to build, share & learn about civic tech.

Hosted by [Netlify](https://www.netlify.com/).

## Dependencies

* [Jekyll](http://jekyllrb.com/) - Static site generator built in Ruby
* [Bootstrap 3](http://getbootstrap.com) - HTML and CSS layouts
* [DataTables](http://datatables.net) - for searching and sorting tables
* [Mustache](http://github.com/janl/mustache.js) - templating library for javascript (used on projects page)
* [jQuery Address](http://github.com/asual/jquery-address) - for deep linking URLs on the projects page

## Running locally

Requirements:

* ruby-2.6.2
* jekyll 3.6.3

We recommend using [rvm](https://rvm.io/) to manage your Ruby versions.

Initial setup
```console
git clone https://github.com/chihacknight/chihacknight.org.git
cd chihacknight.org
rvm install ruby-2.6.2
bundle install
```

Running locally
```console
jekyll serve -w
```

Then open your web browser and navigate to http://localhost:4000

## Run in a Docker container

If you have Docker installed, can avoid some of the hassle of installing Jekyll and/or Ruby by pulling from the offical Jekyll image, installing dependancies, and serving locally. 

This is especially handy if you're on Windows machine:

```
docker run --rm --label=jekyll --volume=%CD%:/srv/jekyll  -it -p 4000:4000 jekyll/jekyll set JEKYLL_VERSION=3.6.3 | bundle install | jekyll serve
```

## Deploying

Deployments are handled by Netlify by pushing to the `production` branch.

Whenver a branch is merged into `production`, or a commit is pushed to `production` it will trigger a Netlify deploy.

## Workflow
The Chi Hack Night web team manages bugs, new features and site development through the [GitHub project board](https://github.com/chihacknight/chihacknight.org/projects/2).

To ensure high code quality, we practice using pull requests and having at least one member of the web team review them before merging in to `production`. 

## Protocols

**Cancelled presenters** If a presenter cancel after we have sent out our email blast, we add `CANCELLED PRESENTATION` to the event title and update the description of the event noting that it will be an open hack event. Example: https://chihacknight.org/events/2018/10/09/censusbureau.html

## Projects and People

The [projects](http://chihacknight.org/open-source-projects.html) and [people](http://chihacknight.org/open-source-people.html) pages are powered by [Github](https://github.com/) and [civic-json-worker](https://github.com/open-city/civic-json-worker), 
a script we run every 5 minutes that fetches data from the [Github API](http://developer.github.com/). 

The JSON files are backed up every hour in the [civic-json-files](https://github.com/open-city/civic-json-files) repository.
