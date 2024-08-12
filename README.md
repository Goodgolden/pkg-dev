Package Development: The Rest of the Owl
================

### posit::conf(2024)

by Jenny Bryan

-----

:spiral_calendar: August 12, 2024  
:alarm_clock:     09:00 - 17:00  
:hotel:           Willapa meeting room  
:writing_hand:    [pos.it/pkg_dev_24](https://pos.it/pkg_dev_24)

-----

## Schedule

| Time          | Topics         | Prompts |
| :------------ | :------------- | :------ |
| 09:00 - 10:30 | Kick the tires of your setup<br>Core workflows<br>Let me GitHub search that for you | placeholder |
| 10:30 - 11:00 | *Coffee break* | |
| 11:00 - 12:30 | Testing        | placeholder |
| 12:30 - 13:30 | *Lunch break*  | |
| 13:30 - 15:00 | Documentation  | placeholder |
| 15:00 - 15:30 | *Coffee break* | |
| 15:30 - 17:00 | GitHub Actions<br>Beautiful UI with cli<br>Topic by popular request? | placeholder |

## Description

In R, the fundamental unit of reusable and shareable code is a package, containing helpful functions, documentation, and sometimes sample data.
Putting R code in a package is the best way to share our code with others or to share code across different projects.

This workshop assumes you've already dipped your toe in package development, i.e. that you've managed to create a basic package and pass `R CMD check`.
In terms of "How to draw an owl", you've definitely drawn some circles.
But now it's time to draw the rest of the owl!

![](https://datasciencebox.org/images/design-owl.jpg)

You will learn workflows and skills that are (a) very important for package development and (b) very different from writing R scripts.
We will lean heavily on the tools and principles used by the tidyverse team, embodied in the devtools family of packages, including usethis, testthat, and roxygen2.

This list of topics is indicative of what we will cover:

-   Fundamental daily workflows: `devtools::load_all()` and `check()`
-   Testing: the testthat package and the philosophy of writing tests as you go (vs. "later")
-   Documentation: function documentation, vignettes, and website
-   Data: internal data vs. data available to your user
-   GitHub Actions for automatically checking your package and building/deploying a pkgdown website
-   User interface: how to provide beautiful, informative messages with the cli package

There will be chunks of time for you to do exercises throughout the day.
We will make sure there are good options that allow all participants to engage with the material.
But if you have your own package(s), you are welcome to use these times to apply what we're learning, e.g. about testing or documentation, in your personal packages.

This will be an interactive 1-day workshop, and we will be using the RStudio IDE to work through the materials.

## Audience

This course is for you if you:

-   Are very comfortable writing R scripts and functions.
-   Have already created a basic package, e.g., you've successfully worked through [The Whole Game chapter from R Packages](https://r-pkgs.org/whole-game.html) or have equivalent experience. You should also be able to follow the story in [The package within](https://r-pkgs.org/package-within.html) chapter.
-   Have concrete plans for one or more specific packages you want to create. You might have even started implementing these plans.
-   Are interested in using devtools/RStudio for package development.
-   Are at least curious about Git/GitHub. We won't have time to teach this explicitly, but you will certainly see Git/GitHub through out the day.

We expect many participants will have more package development experience than the minimum described above.
We typically see a real mix of backgrounds in workshops such as this.
Participants at either extreme (very new or very experienced) should anticipate that they'll hear questions and discussion aimed at the other end of the experience spectrum and that's OK.

## Prework

Each participant needs to bring their own laptop, with functioning wifi.
You should be able to install software (R packages, really) and download files onto it.
History shows that Windows laptops that are very locked-down by corporate IT can be extremely challenging in workshops.
If you encounter permission problems while doing the setup below, that is a big red flag.
Try to solve those problems in advance or bring a different computer.
As a last resort, it is possible to work on [Posit Cloud](https://posit.cloud/).
If you fear this might happen to you, go ahead and set up your Posit Cloud account in advance (it's free!).

System setup: work through the [System setup](https://r-pkgs.org/setup.html) chapter.
Main TODOs:

* Install several R packages related to package development (devtools and friends).
* Optional but recommended: do what is described for your operating system to be able to build and install R packages that contain compiled code. We will not use any C/C++ in the workshop! But anyone who is taking this workshop is likely to want this general capability in the near future.

Personal devtools/usethis setup: work through the [usethis setup](https://usethis.r-lib.org/articles/usethis-setup.html) article
Main TODOs:

* Consider adding a snippet to your `.Rprofile` that attaches devtools in all interactive R sessions.
* Consider setting some options in `.Rprofile` to customize usethis's behaviour:
  - `usethis.description` to pre-fill DESCRIPTION fields
  - `usethis.destdir` to designate a preferred home for local projects
* Run `git_sitrep()` to get a situation report on your Git/GitHub setup.
  Use of Git/GitHub is not mandatory, but it is likely to enhance your workshop experience.

  In particular, configuring a GitHub personal access token will have a huge payoff, in the workshop and beyond.

Here are a few small challenges that should test whether your system is ready to go:

```r
library(devtools)

# Git/GitHub "situation report"
git_sitrep()

# clones the Git repo holding the source of the usethis package
# if your GitHub PAT is set up correctly, it will FORK and clone
create_from_github("r-lib/usethis")

# if you want to test whether you can install packages, from source, that have
# compiled code, try this:
install.packages("cli", type = "source")
```

## Instructor and TAs

* Jenny Bryan (instructor) is a software engineer at Posit, usually working on the tidyverse packages or its supporting ecosystem, and is a member of the R Foundation. She recently co-authored the second edition of [the R Packages book](https://r-pkgs.org/) and is the maintainer of the [devtools](https://devtools.r-lib.org/) and [usethis](https://usethis.r-lib.org/) packages (among others).
* Tomasz Kalinowski (TA) is a software engineer at Posit and a member of the [mlverse](https://github.com/mlverse) team, contributing to the development of open-source machine learning software. He co-authored ["Deep Learning with R"](https://www.manning.com/books/deep-learning-with-r-second-edition) and maintains several R packages, including [reticulate](https://rstudio.github.io/reticulate/), [tensorflow](https://tensorflow.rstudio.com), and [keras3](https://keras3.posit.co).
* Kevin Ushey (TA) is a software engineer at Posit and member of the RStudio IDE development team. He is the maintainer of the [renv](https://rstudio.github.io/renv/) package, and has contributed to a large number of packages in the R ecosystem.

-----

![](https://i.creativecommons.org/l/by/4.0/88x31.png) This work is
licensed under a [Creative Commons Attribution 4.0 International
License](https://creativecommons.org/licenses/by/4.0/).
