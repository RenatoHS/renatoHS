+++
title = "Paralel Computing 1"

date = 2018-09-09T00:00:00
# lastmod = 2018-09-09T00:00:00

draft = false  # Is this a draft? true/false
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.

# Add menu entry to sidebar.
linktitle = ""
[menu.tutorial]
parent = "Tutorial 2"
weight = 1
+++

If something takes less time if done through parallel processing, why
not do it and save time? Computers nowadays have multi core processors
with sufficient amount of memory available to run parallel processing.
Instead of waiting a long time for a task to complete, one can divide
the taks to run in multiple cores and thus obtain outputs much faster.

Packages
--------

There are many packages to run parallel processing in R. Here are a few
examples:

-   parallel
-   snow
-   doSNOW
-   doParallel
-   foreach

The first thing to do is to set up a parallel cluster

    library(doParallel)

    ## Loading required package: foreach

    ## Loading required package: iterators

    ## Loading required package: parallel

    #use the "parallel" library to detect the number of cores in your computer
    nc <- detectCores()

    #set the cluster with nc - 1 (always leave one core free for the machine to run its other processes)
    cl <- makeCluster(nc - 1)
    # this will create a SOCK cluster, which can be done in all operating systems

    #if you want to create a FORK cluster (which has better capabilities to manage memory)
    #cl <- makeCluster(nc-1, type = "FORK")
    #note that Windows doest not support FORK clusters

Including Plots
---------------

You can also embed plots, for example:

![](tut_2_files/figure-markdown_strict/pressure-1.png)

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
