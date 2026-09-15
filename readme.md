# Notes

Run locally with 

    hugo server -D -F

-D for Drafts

-F for future content

# create post

    hugo new posts/my-first-post.md

# Image & Figure with centering

    ![](/uploads/aw.png#center)

    {{< figure align=center src="/uploads/aw.png" title="Hello World" >}}


Link: [Text](URL)
Image: ![Alt Text](URL)

Linked image: [![Alt Text](Image URL)](Link URL)


## Build version

Use **Hugo 0.164.0 Extended** locally and in GitHub Actions. Check with
`hugo version` before publishing; Homebrew upgrades can change the local version.
The workflow pins this version explicitly instead of following `latest`.

Production build (same command as CI):

    hugo --minify --logLevel info --printPathWarnings

XML and JSON minification remain disabled in `config.yml` following the previous
build hang. Keep the `params.author` setting: the bundled PaperMod RSS template
uses it to avoid the removed `site.Author` API.

Pull requests targeting `master` build without deploying. Pushes to `master`
and manual runs on `master` build and upload via FTP. CI caps Hugo at 30 seconds
using Ubuntu's `timeout` command and logs its version and progress. The upload
has a one-minute limit, and the full job (including setup) has a two-minute limit.
If a run stalls, inspect whether it stopped in Setup Hugo, Build, or Sync files.

PaperMod is checked into this repository directly. Its language template fields
have been updated for Hugo 0.164.0; no theme submodule download is required.
