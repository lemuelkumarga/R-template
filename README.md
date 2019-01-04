### Find this work and others at my website [[lemuelkumarga.com]](https://lemuelkumarga.com/)!
---



## Package Requirements

### Mac/Ubuntu Operating System
- Other OS-es have not been tested, and may cause unexpected errors.

### Pandoc 2.1 
- Need to reference googlefonts

### Git LFS
- If there exists a cache folder, you may need to install Git LFS
to pull files > 100 MB. Please follow instructions [here](https://github.com/git-lfs/git-lfs/wiki/Installation).
- After Git LFS is installed, type `git lfs pull` to download the large files in the project.


## Creating A New Repository from the Template

To create a new project by using this template as skeleton, we need to manually "fork" this template. Extra precaution is also required as the R-template contains links to other repos (submodules).

Please replicate the steps below in Terminal to ensure success.

``` sh
# First: Create an empty repository in github via https://github.com/new

# Clone the newly created empty repo
git clone https://github.com/<username>/<new_repo_project_name>

# Define this clone as a fork of R-template
cd <new_repo_project_name> 
git remote add upstream https://github.com/lemuelkumarga/R-template.git

# Pull all the files from the template
git pull upstream master

# Remove the "Create New Repo from Template section"
sed -i 's/, prepend_mds=c("shared\/md\/requirements.md","shared\/md\/creating.md","shared\/md\/cloning.md")//g' main.Rmd

# Initialize submodules
git submodule init
git submodule update

# When cloned, submodules are detached from the HEAD. We attempt to rectify this issue to prevent problems in git
cd shared
git checkout -b tmp
git checkout master
git merge tmp
git branch -d tmp
cd ..

# Push your changes to the cloud
git push -u origin master

# Return to original folder if desired
cd ..
```

## Cloning the Repository

Cloning the repository is not as straightforward due to the presence of git submodules.

Please replicate the steps below in Terminal to ensure success.

``` sh
# Clone the repo as usual
git clone https://github.com/lemuelkumarga/R-template

# Initialize submodule
cd R-template
git submodule init
git submodule update

# When cloned, submodules are detached from the HEAD. We attempt to rectify this issue to prevent problems in git
cd shared
git checkout -b tmp
git checkout master
git merge tmp
git branch -d tmp

# Return to original folder if desired
cd ../../
```

---
Insert Title Here
================
<span class="meta">Lemuel Kumarga</span>
<span class="meta">Mon YYYY</span>

## Problem Description

Insert Problem Description Here.

## Preliminaries

First load the necessary packages for this exercise.

``` r
# Load default settings for R Markdown -- see file for more details
source("shared/defaults.R")
# Load some helper functions
source("shared/helper.R")

options(stringsAsFactors = FALSE)

data_dir <- "data/"
output_dir <- "output/"

si <- sessionInfo()
base_pkg_str <- paste0("Base Packages: ",paste(si[["basePkgs"]], collapse=", "))
attached_pkg_str <- paste0("Attached Packages: ",paste(names(si[["otherPkgs"]]), collapse=", "))
cat(paste0(base_pkg_str,"\n",attached_pkg_str))
```

    ## Base Packages: stats, graphics, grDevices, utils, datasets, methods, base
    ## Attached Packages: tidyr, pander, ggplot2, rlang, dplyr, knitr

## Lorem Ipsum

<a data-toggle="popover" title="Lorem Ipsum" data-content="Lorem Ipsum is simply dummy text of the printing and typesetting industry. Data obtained from https://www.lipsum.com/.">Lorem
ipsum</a> dolor sit amet, consectetur adipiscing elit. Vivamus sit amet
urna nunc. Ut bibendum sem nibh, lobortis tempor dolor scelerisque ut.
Nunc elit lorem, accumsan in pharetra ac, sodales sit amet arcu. In hac
habitasse platea dictumst. Sed accumsan fringilla purus. Aliquam
tincidunt ultricies sapien, eu pellentesque quam porttitor dignissim.
Cras convallis, ipsum feugiat porttitor tempus, tortor orci fringilla
augue, vel ultrices magna massa varius nibh. Ut gravida posuere dolor,
non tincidunt eros sollicitudin in. Curabitur quis odio condimentum
lectus congue fermentum id eget odio. Proin sagittis, nisl ac imperdiet
ornare, metus risus tempor velit, gravida laoreet lacus purus in metus.
Sed sed cursus dolor. Aliquam lobortis purus eget iaculis interdum.
Maecenas nec eros magna.

Curabitur at urna in urna scelerisque maximus non ut urna. Nulla
pharetra ipsum neque, quis dapibus ex egestas a. Nunc condimentum lectus
et sapien convallis molestie. Suspendisse vel massa fringilla, imperdiet
diam ut, fringilla lacus. Aliquam molestie orci purus, a tristique lacus
malesuada quis. Ut rutrum lacus non vulputate iaculis. Cras tincidunt
risus nisl, lobortis pellentesque purus laoreet in. Ut malesuada erat eu
massa efficitur, condimentum euismod ligula imperdiet. Nunc lorem
tortor, placerat iaculis facilisis vitae, euismod id nisl. Duis
venenatis pharetra arcu sed sagittis. Vivamus eu ex vitae odio eleifend
congue. Proin iaculis imperdiet sapien, et lobortis libero efficitur in.
In ac ex elementum, ornare elit id, lacinia erat.
