# legacy-styling-buildpack

This build pack is used to bridge the gap with Heroku-22 and above, where ruby 2.5.9  is no longer supported.

Unfortunately, our internal styling relies on several gems that are no longer supported in the latest version of Ruby and haven't had updates for many years.

This buildpack downloads the css files from a public S3 bucket and copies them into the static folder, to allow it to compile on Heroku.

This is made up of two scripts:
- bin/detect
- bin/compile

If any additional scss files are added to domo or email bases, they will need to be added to the S3 bucket AND to the `compile` script to copy them into the application on deployment

_NB: Buildpacks normally have a `release` script, but this is not needed for this buildpack as we are simply putting files into a folder, there's no metadata required to be output._