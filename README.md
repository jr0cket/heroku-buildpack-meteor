# Heroku buildpack for meteor

This buildpack for Heroku will allow you to deploy a meteor appliction.  

The buildpack uses a Mongodb plugin to hold the data that would otherwise be in minimongo.  The original author of this pack used MongoHQ addon, this has been swapped over to MongoLabs as they are the only Mongodb addon available in the EU region.


## Usage

```
$ heroku create --buildpack https://github.com/jr0cket/heroku-buildpack-meteor.git
```

## Example

Create a sample app with 'meteor'

```
$ meteor create --example wordplay
wordplay: created.

To run your new app:
   cd wordplay
   meteor
```

Commit the files to your local git repository.

```
$ cd wordplay
$ git init
Initialized empty Git repository in /tmp/a/wordplay/.git/
$ git add .
$ git commit -m "Sample wordplay app!"
```

Create your heroku app using the [Heroku toolbelt](https://toolbelt.heroku.com) 

```
$ heroku create --buildpack https://github.com/jr0cket/heroku-buildpack-meteor.git
```

Configure your ROOT_URL setting (not sure if this is actually neccessary)

```
$ heroku config:add ROOT_URL=<insert_url_created_above_here>
```

Deploy your application to Heroku by doing a git push

```
$ git push heroku master
```

Enjoy!
