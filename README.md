This repository contains the source code and media for the [OFO website](https://openforestobservatory.org). Building these source files into an actual HTML website relies on [Hugo](https://gohugo.io/), using the [Hugo Blox](https://hugoblox.com/) theme (specifically the [Boostrap version](https://bootstrap.hugoblox.com/)) and is based on the [Research Group](https://github.com/HugoBlox/theme-research-group) starter template. The build is performed at [Netlify](https://www.netlify.com/) upon push or mege to main. Netlify also serves the site. A preview version of the site is also built and served upon submission of a PR.

<br/>

### Editing Tips

Edit the home landing page at `/content/_index.md`. All other pages can be edited in folders within `/content/`. e.g., the tools page is at `/content/tools/_index.md`
  



## Previewing edits before publishing

There are two ways to preview edits before they become public. **1.** The Netlify option does not require any local software or compute, but it requires pushing changes to Github, submitting a pull request, and waiting about a minute for the website to build. **2.** The local option does not require pushing changes, builds almost immediately, but requires having hugo installed locally.

### Using Netlify's deploy-preview feature

If you commit your changes to a branch, push the branch to GitHub, and then submit a pull request, it will trigger Netlify to build a "deploy preview". Within a few seconds of creating the PR, Netlify will add a comment to the PR that a preview is building, and within a minute or two, it will update with a link to the preview. It is accessible to anyone on the internet but they would need to have the URL (which they could get by visiting our GitHub repo and viewing the PR).

After creating the PR, any additional commits pushed to the branch will trigger an update to the deploy preview. During the build, the Netlify comment will say "building" and when done it will return with the link to the site preview.

Note: Links in embedded iframes (i.e., leaflet maps and data tables) need to use absolute URLs that must be specified in the site source files prior to build. Therefore, these links will not point to the deploy preview, but to the live public website. You can view the "preview" version of these pages by changing `openforestobservatory.org` to `<deploy preview domain>`. If you know a way to use relative links within iframes, or eliminate the iframes entirely, let us know!

### Locally

To edit the website locally, clone this repo to your machine `git clone https://github.com/open-forest-observatory/ofo-website-3.git'

Install the Hugo command-line tools: 

&nbsp;&nbsp;&nbsp;&nbsp;on Ubuntu, `sudo apt install hugo` 



on MacOS `brew install hugo`. 


Then, in a terminal with the root of the website repo as your working directory, run `hugo server`. The website will build in a few seconds, and then the terminal will tell you it is being served at localhost:1313. Go to this URL to see the site.

Note: Links in embedded iframes (i.e., leaflet maps and data tables) need to use absolute URLs that must be specified in the site source files prior to build. By default, the R scripts that build these resources are set to use `openforestobservatory.org` (not `localhost:1313`) as the domain. This can be changed (via a constant at the top of the relevant scripts) to `localhost:1313` so that these URLs point to the local server's site. You would then have to re-run the R script to re-generate the site source files with this new URL. Just make sure to set it back to `openforestobservatory.org` before pushing your changes (or at least before submitting a PR).
