# dev_R-RENV
R with RENV Notes and Workspace 

#### The renv package helps you create reproducible environments for your R projects. 
Install renv within R or from a shell <br/>
Shell: <br/>
`$R -e "install.packages('renv',repos='https://cran.rstudio.org')"` <br/>

Within R: <br/>
`>install.packages('renv',repos='https://cran.rstudio.org')` <br/>

To convert a project to use renv, call renv::init() within R `>renv::init()`. It adds three new files and directories to your project: <br/>
- The renv/library which is a library that contains all packages currently used by your project
- The lockfile, renv.lock
- The project R profile, .Rprofile. This file is run automatically every time you start R (in that project), and renv uses it to configure your R session to use the project library. 
