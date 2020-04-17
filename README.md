# cassidynelemans.com

https://www.cassidynelemans.com is a static site generated by [Hugo](https://gohugo.io/) that is hosted in an S3 bucket and served by a Cloudfront distribution.

## Local environment setup

- Install hugo via brew

`brew install hugo`

- Clone the repo onto your local machine

`git clone git@github.com:nelemansc/cassidynelemans.com.git`

- cd to the folder and make modifications. The theme used lives in the `themes/` directory.

- run `hugo server -D` to generate the site via hugo emulation. The site can be accessed at http://localhost:1313. If all looks good, commit your changes and push.

The Github Action associated with the repo does the following:
- checks out the repo
- Runs `hugo -D` to generate the static assets
- Uploads the static assets generated from the previous steup to S3
- Invalidates the Cloudformation cache so the newest version is served up by the CDN
