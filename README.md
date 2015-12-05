
## Prerequisites

* RVM / A Stable Ruby Version
* Yeoman, Gulp, Bower `npm install -g yo gulp bower`

## Get the code and bootstrap the App

```
$ git clone https://github.com/sasasekaric/angular-rails-heroku-example.git
$ cd angular-rails-heroku-example
$ bundle install
$ rake db:create && rake db:migrate
$ npm install

```

## Run it localy

```
$ cd client && gulp serve:full-stack

```

## Deploy to heroku
Firts create repo on github or bitbucket then push code to your new repo then

```
$ heroku create
$ heroku buildpacks:set https://github.com/heroku/heroku-buildpack-ruby
$ heroku buildpacks:add --index 1 https://github.com/heroku/heroku-buildpack-nodejs
$ heroku config:set NODE_ENV=production
$ git push heroku master

```
## Test rails backend
To test rails backend go to
```
http://localhost:9000/api/v1/articles
```
And you should see empty []

```
http://localhost:9000/#/articles
```
And if you inspect your app calls (chrome users can go to Developer Tools inside network tab)
you should see call to article (http://localhost:9000/api/v1/articles)

## Debuging
To see logs from heroku

```

$ heroku logs --tail
$ heroku addons:create papertrail
$ heroku addons:open papertrail

```
