# legacy-styling-buildpack

This build pack is bridge the gap with Heroku-22 and above, where ruby 2.5.9  is no longer supported.

Unfortunately, our styling relies on several gems that are no longer supported in the latest version of Ruby.

This buildpack downloads the css files from a public S3 bucket and copies them into the static folder, to allow it to compile on Heroku.

This is made up of three scripts:
- bin/detect
- bin/compile
- bin/release