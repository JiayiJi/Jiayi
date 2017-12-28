This is Jiayi Ji's personal website. It is built with blogdown and hugo, now hosted on netlify.

How to Build this site manually

1. If you are starting from scratch, clone the github repo into RStudio or first creating a project on your computer and then add the directory to your git client (and, optionally, create remote repository).  

    - My preferred method of making new repos as RStuio Projects
    
        1. Start at Github.com > New Repo
        1. Clone [new & empty] Repo as new project into Rstudio IDE running on localhost
        1. git push -- README.md, license.md, and .gitignore

Check out [Jeff Goldsmith's lecture material](http://jeffgoldsmith.com/DSI/git.html) if you want to adopt the latter approach.
    
2. `library(blogdown)` [Resources:  [github](https://github.com/rstudio/blogdown), [Yihui's Book](https://bookdown.org/yihui/blogdown/)]

    - Dependencies:
    
        - `devtools::install_github('rstudio/blogdown')`
        - `blogdown::install_hugo()`
            - only need to do this once, but
            - might need to, occasionally but not initially, run `blogdown::update_hugo()`
        - `blogdown::new_site(theme = "gcushen/hugo-academic")` 
            - must be a completely empty directory except for .Rproj file
            - view [other theme](https://themes.gohugo.io/) options
                - See [Yihui's recommendation](https://github.com/rstudio/blogdown#blogdown) of selecting one of only a few workable themes for newbies
    
3. `blogdown::serve_site()`
4. Edit via *Rmarkdown* or *markdown* in the `content` directory and subdirs

    - Initially, you will have edited the `config.toml`, plus `layouts`, and `static` directories (e.g. CSS, templates, etc. and such)
    
5. Make customizations and stylistic (i.e. non-content) changes (CSS, see ["*static*"](https://bookdown.org/yihui/blogdown/templates.html)) in the `static` directory, where the sub-hierarchy of `static` mirrors the sub-hierarchy into `public` 

    - Do not need to mirror the entire sub-hieary.  Customize/mirror only as necessary and appropriate.
    
5. Override `layouts` by ghosting the `themes/../layouts/...` sub-hiearchy into the `layouts` directory.  See [custom-layours documentation](https://bookdown.org/yihui/blogdown/custom-layouts.html)

5. Deployment on [Netlify](http://netlify.com)  

    - For Manual Deployment, Optionally stop blogdown server.  Drag `public` directory to netlify.com deploy
    - For Continuous Depolyment, set up according to the [Netlify Docs](https://www.netlify.com/docs/continuous-deployment/) pointing to the `/public` of an appropriate github repository.

        - You need to set Command = `hugo_0.31`. Otherwise, Netlify won't let you set up your website. I found this through trial and error.

