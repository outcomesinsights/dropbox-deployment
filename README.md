# dropbox-deployment
Deploy your CI artifacts to Dropbox

[![Build Status](https://travis-ci.org/Jawnnypoo/upload-to-dropbox.svg?branch=master)](https://travis-ci.org/Jawnnypoo/upload-to-dropbox)

## Setup
Install the gem:
```
gem install dropbox-deployment
```

## Usage
Similar to the [dropbox_api](https://github.com/Jesus/dropbox_api), you need to have an environment variable called `DROPBOX_OAUTH_BEARER`

You can create a OAUTH token here:
https://www.dropbox.com/developers/apps/create

Deployment looks for a `dropbox-deployment.yml` file in order to configure where the artifacts are and where they should go.
For example:
```yml
deploy:
  dropbox_path: /Builds # The path to the folder on Dropbox where the files will go
  artifacts_path: artifacts # can be a single file, or a path
  debug: true # if you want to see more logs
```
After creating this configuration, all you need to do is run:
```shell
dropbox-deployment  
```

## Limitations
Since we rely on a certain function of the ruby Dropbox API client, we are limited to 150 MB files. See more [here](http://jesus.github.io/dropbox_api/DropboxApi/Client.html#upload-instance_method)

## Test Locally
Just run `ruby test/test.rb`
## Thanks
Thanks to the following for being a great reference on how to create a command line Ruby Gem:
  - http://robdodson.me/how-to-write-a-command-line-ruby-gem/
