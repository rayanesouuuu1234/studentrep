---
layout: post
title: Linux Shell and Bash
description: A Tech Talk on Linux and the Bash shell.
toc: True
comments: True
categories: ['5.A', 'C4.1']
courses: {'csp': {'week': 0}}
type: devops
---

## Bash Tutorial
> A brief overview of Bash, on your way to becoming a Linux expert.  When a computer boots up, a kernel (MacOS, Windows, Linux) is started.  This kernel provides a shell that allows user to interact with a most basic set of commands.  Typically, the casual user will not interact with the shell as a Desktop User Interface is started by the computer boot up process.  To activate a shell directly, users will run a "terminal" through the Desktop. VS Code provides ability to activate "terminal" while in the IDE.

## Prerequisites
> Setup bash shell dependency variables for this page.

- Hack: Change variables to match your project.


```python
%%script bash

# Dependency Variables, set to match your project directories

cat <<EOF > /tmp/variables.sh
export project_dir=$HOME/vscode  # change vscode to different name to test git clone
export project=\$project_dir/teacher  # change teacher to name of project from git clone
export project_repo="https://github.com/nighthawkcoders/teacher.git"  # change to project of choice
EOF
```


```python
%%script bash

# Extract saved variables
source /tmp/variables.sh

# Access the variables
echo "Project dir: $project_dir"
echo "Project: $project"
echo "Repo: $project_repo"
```

    Project dir: /Users/rayanesouissi/vscode
    Project: /Users/rayanesouissi/vscode/teacher
    Repo: https://github.com/nighthawkcoders/teacher.git


## Setup Project
> Pull code from GitHub to your machine. This script will create a project directory and add "project" from GitHub to the vscode directory.  There is conditional logic to make sure that clone only happen if it does not (!) exist.


```python
%%script bash

# Extract saved variables
source /tmp/variables.sh

echo "Using conditional statement to create a project directory and project"

cd ~    # start in home directory

# Conditional block to make a project directory
if [ ! -d $project_dir ]
then 
    echo "Directory $project_dir does not exists... makinng directory $project_dir"
    mkdir -p $project_dir
fi
echo "Directory $project_dir exists." 

# Conditional block to git clone a project from project_repo
if [ ! -d $project ]
then
    echo "Directory $project does not exists... cloning $project_repo"
    cd $project_dir
    git clone $project_repo
    cd ~
fi
echo "Directory $project exists." 
```

    Using conditional statement to create a project directory and project
    Directory /Users/rayanesouissi/vscode exists.
    Directory /Users/rayanesouissi/vscode/teacher exists.


### Look at files Github project
> All computers contain files and directories.  The clone brought more files from cloud to your machine.  Review the bash shell script observe the commands that show and interact with files and directories.

- "ls" lists computer files in Unix and Unix-like operating systems
- "cd" offers way to navigate and change working directory
- "pwd" print working directory
- "echo" used to display line of text/string that are passed as an argument


```python
%%script bash

# Extract saved variables
source /tmp/variables.sh

echo "Navigate to project, then navigate to area wwhere files were cloned"
cd $project
pwd

echo ""
echo "list top level or root of files with project pulled from github"
ls

```

    Navigate to project, then navigate to area wwhere files were cloned
    /Users/rayanesouissi/vscode/teacher
    
    list top level or root of files with project pulled from github
    Gemfile
    Gemfile.lock
    LICENSE
    Makefile
    README.md
    _config.yml
    [34m_data[m[m
    [34m_includes[m[m
    [34m_layouts[m[m
    [34m_notebooks[m[m
    [34m_posts[m[m
    [34m_site[m[m
    [34massets[m[m
    csa.md
    csp.md
    csse.md
    [34mimages[m[m
    index.md
    indexBlogs.md
    [34mscripts[m[m


### Look at file list with hidden and long attributes
> Most linux commands have options to enhance behavior

[ls reference](https://www.rapidtables.com/code/linux/ls.html)


```python
%%script bash

# Extract saved variables
source /tmp/variables.sh

echo "Navigate to project, then navigate to area wwhere files were cloned"
cd $project
pwd

echo ""
echo "list all files in long format"
ls -al   # all files -a (hidden) in -l long listing
```

    Navigate to project, then navigate to area wwhere files were cloned
    /Users/rayanesouissi/vscode/teacher
    
    list all files in long format
    total 120
    drwxr-xr-x  25 rayanesouissi  staff   800 Sep 15 10:39 [34m.[m[m
    drwxr-xr-x   5 rayanesouissi  staff   160 Aug 16 22:00 [34m..[m[m
    drwxr-xr-x  14 rayanesouissi  staff   448 Sep 20 11:30 [34m.git[m[m
    drwxr-xr-x   3 rayanesouissi  staff    96 Aug 16 21:48 [34m.github[m[m
    -rw-r--r--   1 rayanesouissi  staff   176 Sep  5 09:58 .gitignore
    -rw-r--r--   1 rayanesouissi  staff   122 Aug 16 21:48 Gemfile
    -rw-r--r--   1 rayanesouissi  staff  7348 Sep  5 10:00 Gemfile.lock
    -rw-r--r--   1 rayanesouissi  staff  1081 Aug 16 21:48 LICENSE
    -rw-r--r--   1 rayanesouissi  staff  3136 Sep  5 09:58 Makefile
    -rw-r--r--   1 rayanesouissi  staff  6853 Sep  5 09:58 README.md
    -rw-r--r--   1 rayanesouissi  staff   607 Aug 16 21:48 _config.yml
    drwxr-xr-x   6 rayanesouissi  staff   192 Aug 16 21:48 [34m_data[m[m
    drwxr-xr-x  13 rayanesouissi  staff   416 Sep 15 10:39 [34m_includes[m[m
    drwxr-xr-x   6 rayanesouissi  staff   192 Sep  5 09:58 [34m_layouts[m[m
    drwxr-xr-x  65 rayanesouissi  staff  2080 Sep 20 11:30 [34m_notebooks[m[m
    drwxr-xr-x  69 rayanesouissi  staff  2208 Sep 15 10:39 [34m_posts[m[m
    drwxr-xr-x  32 rayanesouissi  staff  1024 Sep  5 10:00 [34m_site[m[m
    drwxr-xr-x   4 rayanesouissi  staff   128 Aug 16 21:48 [34massets[m[m
    -rw-r--r--   1 rayanesouissi  staff    92 Aug 16 21:48 csa.md
    -rw-r--r--   1 rayanesouissi  staff    98 Aug 16 21:48 csp.md
    -rw-r--r--   1 rayanesouissi  staff   108 Aug 16 21:48 csse.md
    drwxr-xr-x  40 rayanesouissi  staff  1280 Sep 15 10:39 [34mimages[m[m
    -rw-r--r--   1 rayanesouissi  staff  5162 Sep 15 10:39 index.md
    -rw-r--r--   1 rayanesouissi  staff    53 Aug 16 21:48 indexBlogs.md
    drwxr-xr-x   9 rayanesouissi  staff   288 Sep  5 09:59 [34mscripts[m[m



```python
%%script bash

# Extract saved variables
source /tmp/variables.sh

echo "Look for posts"
export posts=$project/_posts  # _posts inside project
cd $posts  # this should exist per fastpages
pwd  # present working directory
ls -l  # list posts
```

    Look for posts
    /Users/rayanesouissi/vscode/teacher/_posts
    total 1720
    -rw-r--r--  1 rayanesouissi  staff  61997 Sep  5 09:59 2023-07-15-machine_learning_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  35434 Sep  5 09:59 2023-07-29-cloud-workspace-automation_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   9659 Sep  5 09:59 2023-07-29-cloud_database_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   2811 Sep  5 09:59 2023-07-30-mario_overview_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   7060 Sep  5 09:59 2023-08-01-mario_player_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  10258 Sep  5 09:59 2023-08-02-mario_platform_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  16451 Sep  5 09:59 2023-08-03-mario_tube_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  18874 Sep  5 09:59 2023-08-04-mario_block_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  19318 Sep  5 09:59 2023-08-05-mario_goomba_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  22629 Sep  5 09:59 2023-08-06-mario_background_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   7827 Sep  5 09:59 2023-08-15-java-hello_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   7685 Aug 16 21:48 2023-08-16-Tools_Equipment.md
    -rw-r--r--  1 rayanesouissi  staff  20405 Sep  5 09:59 2023-08-16-github_pages_setup_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  10337 Sep  5 09:59 2023-08-16-linux_shell_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   4650 Sep  5 09:58 2023-08-16-pair_programming.md
    -rw-r--r--  1 rayanesouissi  staff   8691 Sep  5 09:59 2023-08-16-python_hello_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   7139 Sep  5 09:58 2023-08-17-markdown-html_fragments.md
    -rw-r--r--  1 rayanesouissi  staff   4687 Sep  5 09:58 2023-08-21-python_flask.md
    -rw-r--r--  1 rayanesouissi  staff   8841 Sep  5 09:59 2023-08-23-github_pages_anatomy_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  18680 Sep  5 09:59 2023-08-23-java-console_games_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   6670 Sep  5 09:58 2023-08-23-javascript-calculator.md
    -rw-r--r--  1 rayanesouissi  staff   6505 Sep  5 09:59 2023-08-23-python_tricks_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   6316 Sep  5 09:59 2023-08-29-basics-of-js_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  11341 Sep 15 10:39 2023-08-30-agile_methodolgy.md
    -rw-r--r--  1 rayanesouissi  staff   4397 Sep 15 10:39 2023-08-30-javascript-music-api.md
    -rw-r--r--  1 rayanesouissi  staff   2336 Sep  5 09:59 2023-08-30-javascript_grab_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   5592 Sep  5 09:59 2023-08-30-js-with-html_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   8735 Sep  5 09:59 2023-08-30-showcase-S1-pair_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  10874 Sep  5 09:59 2023-09-06-java-primitives_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   8046 Sep  5 09:59 2023-09-06-javascript-input_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   5312 Sep  5 09:58 2023-09-06-javascript-motion-mario-oop.md
    -rw-r--r--  1 rayanesouissi  staff  10350 Sep  5 10:00 2023-09-06-javascript-output-jquery_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   5500 Sep  5 10:00 2023-09-06-python-flask_in_jupyter_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff    263 Sep 15 10:39 2023-09-10-users-db.md
    -rw-r--r--  1 rayanesouissi  staff  11627 Sep  5 10:00 2023-09-12-AP-python_lists_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  10489 Sep  5 10:00 2023-09-12-java_menu_class_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   1878 Sep 15 10:39 2023-09-12-javascript-calculator-reviews.md
    -rw-r--r--  1 rayanesouissi  staff   5212 Sep  5 10:00 2023-09-12-python-flask-anatomy_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   3688 Sep  5 09:58 2023-09-12-python-flask-repo.md
    -rw-r--r--  1 rayanesouissi  staff   2845 Sep 15 10:39 2023-09-12-unit-1-summary.md
    -rw-r--r--  1 rayanesouissi  staff   6708 Sep  5 10:00 2023-09-13-java_fibonaccii_class_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  24360 Sep  5 10:00 2023-09-13-javascript_output_api_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   4737 Sep  5 10:00 2023-09-13-python-errors_fries_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  21670 Sep  5 10:00 2023-09-13-python-pandas_intro_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   5256 Sep 15 10:39 2023-09-14-java-free_response.md
    -rw-r--r--  1 rayanesouissi  staff   6173 Sep 15 10:39 2023-09-14-javascript-binary-U2-1.md
    -rw-r--r--  1 rayanesouissi  staff    804 Sep 15 10:39 2023-09-15-java-free_response_showcase.md
    -rw-r--r--  1 rayanesouissi  staff  17201 Sep  5 10:00 2023-09-17-python-images-U2-2_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  24421 Sep  5 10:00 2023-09-18-python-pandas-U2-3_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  27805 Sep  5 10:00 2023-09-19-python-sql-U2-4a_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   7491 Sep  5 10:00 2023-09-19-python-sql-U2-4b_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   8410 Sep  5 10:00 2023-09-20-java-image_2D_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  19197 Sep  5 10:00 2023-09-20-javascript_motion_dog_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  16463 Sep  5 10:00 2023-09-27-aws-deployment_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff    371 Sep 15 10:39 2023-09-28-java-spring-passion-idea.md
    -rw-r--r--  1 rayanesouissi  staff    385 Sep 15 10:39 2023-09-28-java-spring_passion.md
    -rw-r--r--  1 rayanesouissi  staff   2404 Sep 15 10:39 2023-09-28-java-student-teach-tri1.md
    -rw-r--r--  1 rayanesouissi  staff   9963 Sep  5 10:00 2023-10-02-java-spring-anatomy_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   9823 Sep  5 10:00 2023-10-09-java-chatgpt_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  11058 Sep  5 10:00 2023-10-09-javascript_api_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  21533 Sep  5 10:00 2023-10-09-python_machine_learing_fitness_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  13219 Sep  5 09:58 2023-10-16-java-api-pojo-jpa.md
    -rw-r--r--  1 rayanesouissi  staff  13998 Sep  5 10:00 2023-10-16-java_jpa_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   6819 Aug 16 21:48 2023-11-13-jwt-java-spring.md
    -rw-r--r--  1 rayanesouissi  staff  12219 Sep  5 10:00 2023-11-13-jwt-python-flask_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff  12279 Sep  5 10:00 2023-11-13-vulnerabilities_IPYNB_2_.md
    -rw-r--r--  1 rayanesouissi  staff   6686 Sep  5 10:00 2024-01-04-cockpit-setup_IPYNB_2_.md



```python
%%script bash

# Extract saved variables
source /tmp/variables.sh

echo "Look for notebooks"
export notebooks=$project/_notebooks  # _notebooks is inside project
cd $notebooks   # this should exist per fastpages
pwd  # present working directory
ls -l  # list notebooks
```

    Look for notebooks
    /Users/rayanesouissi/vscode/teacher/_notebooks
    total 4040
    -rw-r--r--  1 rayanesouissi  staff  992100 Sep  5 09:58 2023-07-15-machine_learning.ipynb
    -rw-r--r--  1 rayanesouissi  staff   43705 Sep  5 09:58 2023-07-29-cloud-workspace-automation.ipynb
    -rw-r--r--  1 rayanesouissi  staff    3584 Sep  5 09:58 2023-07-30-mario_overview.ipynb
    -rw-r--r--  1 rayanesouissi  staff   10600 Sep  5 09:58 2023-08-01-mario_player.ipynb
    -rw-r--r--  1 rayanesouissi  staff   14783 Sep  5 09:58 2023-08-02-mario_platform.ipynb
    -rw-r--r--  1 rayanesouissi  staff   22612 Sep  5 09:58 2023-08-03-mario_tube.ipynb
    -rw-r--r--  1 rayanesouissi  staff   25779 Sep  5 09:58 2023-08-04-mario_block.ipynb
    -rw-r--r--  1 rayanesouissi  staff   26462 Sep  5 09:58 2023-08-05-mario_goomba.ipynb
    -rw-r--r--  1 rayanesouissi  staff   30617 Sep  5 09:58 2023-08-06-mario_background.ipynb
    -rw-r--r--  1 rayanesouissi  staff   10283 Sep  5 09:58 2023-08-15-java-hello.ipynb
    -rw-r--r--  1 rayanesouissi  staff   26361 Sep  5 09:58 2023-08-16-github_pages_setup.ipynb
    -rw-r--r--  1 rayanesouissi  staff   16156 Sep  5 09:58 2023-08-16-linux_shell.ipynb
    -rw-r--r--  1 rayanesouissi  staff   11466 Sep 15 10:39 2023-08-16-python_hello.ipynb
    -rw-r--r--  1 rayanesouissi  staff   11158 Sep  5 09:58 2023-08-23-github_pages_anatomy.ipynb
    -rw-r--r--  1 rayanesouissi  staff   23636 Sep  5 09:58 2023-08-23-java-console_games.ipynb
    -rw-r--r--  1 rayanesouissi  staff    9663 Sep  5 09:58 2023-08-23-python_tricks.ipynb
    -rw-r--r--  1 rayanesouissi  staff    1091 Sep 15 10:39 2023-08-28-basics-home.ipynb
    -rw-r--r--  1 rayanesouissi  staff    4012 Sep 15 10:39 2023-08-28-basics-html.ipynb
    -rw-r--r--  1 rayanesouissi  staff   11924 Sep 15 10:39 2023-08-29-basics-of-js.ipynb
    -rw-r--r--  1 rayanesouissi  staff   18177 Sep 15 10:39 2023-08-30-basics-js-data-types.ipynb
    -rw-r--r--  1 rayanesouissi  staff   16262 Sep 15 10:39 2023-08-30-basics-js-with-html.ipynb
    -rw-r--r--  1 rayanesouissi  staff    3214 Sep  5 09:58 2023-08-30-javascript_grab.ipynb
    -rw-r--r--  1 rayanesouissi  staff    9689 Aug 16 21:48 2023-08-30-showcase-S1-pair.ipynb
    -rw-r--r--  1 rayanesouissi  staff   15223 Sep 15 10:39 2023-09-06-java-primitives.ipynb
    -rw-r--r--  1 rayanesouissi  staff   12695 Sep 15 10:39 2023-09-06-javascript-input.ipynb
    -rw-r--r--  1 rayanesouissi  staff   14906 Sep  7 09:55 2023-09-06-javascript-output-jquery.ipynb
    -rw-r--r--  1 rayanesouissi  staff   10023 Sep 20 11:30 2023-09-06-python-flask_in_jupyter.ipynb
    -rw-r--r--  1 rayanesouissi  staff   13709 Sep 15 10:39 2023-09-12-java_menu_class.ipynb
    -rw-r--r--  1 rayanesouissi  staff    7174 Sep  5 09:58 2023-09-12-python-flask-anatomy.ipynb
    -rw-r--r--  1 rayanesouissi  staff   13183 Sep 15 10:39 2023-09-12-python_lists.ipynb
    -rw-r--r--  1 rayanesouissi  staff    9841 Sep 15 10:39 2023-09-13-java_fibonaccii_class.ipynb
    -rw-r--r--  1 rayanesouissi  staff   25234 Sep 15 10:39 2023-09-13-javascript_output_objects.ipynb
    -rw-r--r--  1 rayanesouissi  staff   43423 Aug 16 21:48 2023-09-13-python-pandas_intro.ipynb
    -rw-r--r--  1 rayanesouissi  staff    8478 Sep 21 10:03 2023-09-15-1_4-python-errors.ipynb
    -rw-r--r--  1 rayanesouissi  staff   22317 Sep 15 10:39 2023-09-17-python-images-U2-2.ipynb
    -rw-r--r--  1 rayanesouissi  staff   34768 Sep 15 10:39 2023-09-18-python-pandas-U2-3.ipynb
    -rw-r--r--  1 rayanesouissi  staff   49090 Sep 15 10:39 2023-09-19-python-sql-U2-4a.ipynb
    -rw-r--r--  1 rayanesouissi  staff   11550 Sep 15 10:39 2023-09-19-python-sql-U2-4b.ipynb
    -rw-r--r--  1 rayanesouissi  staff   11584 Sep 15 10:39 2023-09-20-java-image_2D.ipynb
    -rw-r--r--  1 rayanesouissi  staff    4616 Sep 15 10:39 2023-09-20-spritesheet_animation.ipynb
    -rw-r--r--  1 rayanesouissi  staff   24663 Sep 15 10:39 2023-09-21-javascript_motion_dog.ipynb
    -rw-r--r--  1 rayanesouissi  staff   22157 Sep 15 10:39 2023-09-27-aws-deployment.ipynb
    -rw-r--r--  1 rayanesouissi  staff   13599 Sep  5 09:58 2023-10-02-java-spring-anatomy.ipynb
    -rw-r--r--  1 rayanesouissi  staff   12429 Sep 15 10:39 2023-10-09-java-chatgpt.ipynb
    -rw-r--r--  1 rayanesouissi  staff   15632 Aug 16 21:48 2023-10-09-javascript_api.ipynb
    -rw-r--r--  1 rayanesouissi  staff  113091 Aug 16 21:48 2023-10-09-python_machine_learing_fitness.ipynb
    -rw-r--r--  1 rayanesouissi  staff     562 Sep 15 10:39 2023-10-16-java-u1-student.ipynb
    -rw-r--r--  1 rayanesouissi  staff     542 Sep 15 10:39 2023-10-16-java-u2-student.ipynb
    -rw-r--r--  1 rayanesouissi  staff     729 Sep 15 10:39 2023-10-16-java-u3-student.ipynb
    -rw-r--r--  1 rayanesouissi  staff     543 Sep 15 10:39 2023-10-16-java-u4-student.ipynb
    -rw-r--r--  1 rayanesouissi  staff     543 Sep 15 10:39 2023-10-16-java-u5-student.ipynb
    -rw-r--r--  1 rayanesouissi  staff     544 Sep 15 10:39 2023-10-16-java-u6-student.ipynb
    -rw-r--r--  1 rayanesouissi  staff     542 Sep 15 10:39 2023-10-16-java-u7-student.ipynb
    -rw-r--r--  1 rayanesouissi  staff     567 Sep 15 10:39 2023-10-16-java-u8-student.ipynb
    -rw-r--r--  1 rayanesouissi  staff     541 Sep 15 10:39 2023-10-16-java-u9-student.ipynb
    -rw-r--r--  1 rayanesouissi  staff   20077 Sep  5 09:58 2023-10-16-java_jpa.ipynb
    -rw-r--r--  1 rayanesouissi  staff     564 Sep 15 10:39 2023-10-17-java-u10-student.ipynb
    -rw-r--r--  1 rayanesouissi  staff   16271 Aug 16 21:48 2023-11-13-jwt-python-flask.ipynb
    -rw-r--r--  1 rayanesouissi  staff   15951 Aug 16 21:48 2023-11-13-vulnerabilities.ipynb
    -rw-r--r--  1 rayanesouissi  staff   18328 Aug 16 21:48 2023-11-20-jwt-java-spring-challenge.md
    -rw-r--r--  1 rayanesouissi  staff   10745 Aug 16 21:48 2024-01-04-cockpit-setup.ipynb
    drwxr-xr-x  3 rayanesouissi  staff      96 Aug 16 21:48 [34mfiles[m[m



```python
%%script bash

# Extract saved variables
source /tmp/variables.sh

echo "Look for images in notebooks, print working directory, list files"
cd $notebooks/images  # this should exist per fastpages
pwd
ls -l
```

    Look for images in notebooks, print working directory, list files
    /Users/rayanesouissi/vscode/studentrep/_notebooks


    bash: line 6: cd: /images: No such file or directory


    total 152
    -rw-r--r--  1 rayanesouissi  staff   5838 Sep 27 23:47 2023-08-16-JS-Basics-Test.ipynb
    -rw-r--r--  1 rayanesouissi  staff  32137 Sep  7 09:54 2023-08-16-linux_shell.ipynb
    -rw-r--r--  1 rayanesouissi  staff   5415 Aug 16 22:00 2023-08-17-AP-pseudo-vs-python.ipynb
    -rw-r--r--  1 rayanesouissi  staff   8615 Aug 16 22:00 2023-08-21-VSCode-GitHub_Pages.ipynb
    -rw-r--r--  1 rayanesouissi  staff   1394 Sep 12 08:46 2023-08-31-emoji.ipynb
    -rw-r--r--  1 rayanesouissi  staff   2103 Sep 11 09:52 2023-08-31-soccer-player-salaries-csv.ipynb
    -rw-r--r--  1 rayanesouissi  staff   2819 Sep 11 21:51 2023-09-06-Sports-Quiz.ipynb
    -rw-r--r--  1 rayanesouissi  staff   2682 Sep 21 09:58 2023-09-14-team-test-identifying-errors.ipynb


### Look inside a Markdown File
> "cat" reads data from the file and gives its content as output


```python
%%script bash

# Extract saved variables
source /tmp/variables.sh

echo "Navigate to project, then navigate to area wwhere files were cloned"

cd $project
echo "show the contents of README.md"
echo ""

cat README.md  # show contents of file, in this case markdown
echo ""
echo "end of README.md"

```

    Navigate to project, then navigate to area wwhere files were cloned
    show the contents of README.md
    
    ## Teacher Blog site
    This site is intended for the development of Teacher content.  This blogging site is built using GitHub Pages [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).
    - The purpose is to build lessons and distribute across different Computer Science sections (CSSE, CSP, CSA), a pathway that covers 3 years of High School instruction.
    - The primary languages and frameworks that are taught are `JavaScript/HTML/CSS`, `Python/Flask`, `Java/Spring`.  Read below for more details.
    - In this course, Teacher content is not exclusively developed by Teachers.  In fact, many Students have been invited to develop and publish content into this repository.  Their names will appear as authors on the content which they aided in producing.
    - This site has incorporated ideas and has radically modified scripts from the now deprecated [fastpages](https://github.com/fastai/fastpages) repository.
    - This site includes assistance and guideance from ChatGPT, [chat.openai.com](https://chat.openai.com/) 
    
    ### Courses and Pathway
    The focus of the Del Norte Computer Science three-year pathway is `Full Stack Web Development`.  This focus provides a variety of technologies and exposures.  The intention of the pathway is breadth and exposure.
    - `JavaScript` documents are focused on frontend development and for entry class into the Del Norte Computer Science pathway.  JavaScript documents and materials are a prerequisites to Python and Java classes.
    - `Python` documents are focused on backend development and requirements for the AP Computer Science Principles exam.
    - `Java` documents are focused on backend development and requirements for the AP Computer Sciene A exam.
    - `Data Structures` materials embedded into JavaScript, Python, or Java documents are focused on college course articulation.
    
    ### Resources and Instruction
    The materials, such as this README, as well as `Tools`, `DevOps`, and `Collaboration` resources are integral part of this course and Computer Science in general.  Everything in our environment is part of our learning of Computer Science. 
    - `Visual Studio Code` is key the code-build-debug cycle editor used in this course, [VSCode download](https://code.visualstudio.com/).  This is an example of a resource, but inside of it it has features for collaboration.
    - `Tech Talks`, aka lectures, are intended to be interactive and utilize `Jupyter Notebooks` and Websites.  This is an example of blending instruction and tools together, which in turn provide additional resources for learning.  For instance, deep knowledge on  GitHub Pages and Notebooks are valuable in understanding principles behind Full Stack Development and Data Science. 
    
    ## GitHub Pages
    All `GitHub Pages` websites are managed on GitHub infrastructure. GitHub uses `Jekyll` to tranform your content into static websites and blogs. Each time we change files in GitHub it initiates a GitHub Action that rebuilds and publishes the site with Jekyll.  
    - GitHub Pages is powered by: [Jekyll](https://jekyllrb.com/).
    - Publised teacher website: [nighthawkcoders.github.io/teacher](https://nighthawkcoders.github.io/teacher/)
    
    ## Preparing a Preview Site 
    In all development, it is recommended to test your code before deployment.  The GitHub Pages development process is optimized by testing your development on your local machine, prior to files on GitHub
    
    Development Cycle. For GitHub pages, the tooling described below will create a development cycle  `make-code-save-preview`.  In the development cycle, it is a requirement to preview work locally, prior to doing a VSCode `commit` to git.
    
    Deployment Cycle.  In the deplopyment cycle, `sync-github-action-review`, it is a requirement to complete the development cycle prior to doing a VSCode `sync`.  The sync triggers github repository update.  The action starts the jekyll build to publish the website.  Any step can have errors and will require you to do a review.
    
    ### WSL and/or Ubuntu installation requirements
    - The result of these step is Ubuntu tools to run preview server.  These procedures were created using [jekyllrb.com](https://jekyllrb.com/docs/installation/ubuntu/)
    ```bash
    # 
    # WSL/Ubuntu setup
    #
    mkdir mkdir vscode
    git clone https://github.com/nighthawkcoders/teacher.git
    # run script, path vscode/teacher are baked in script
    ~/vscode/teacher/scripts/activate_ubuntu.sh
    #=== !!!Start a new Terminal!!! ===
    #=== Continue to next section ===
    ```
    
    ### MacOs installation requirements 
    - Ihe result of these step are MacOS tools to run preview server.  These procedures were created using [jekyllrb.com](https://jekyllrb.com/docs/installation/macos/). 
    
    ```bash
    # 
    # MacOS setup
    #
    mkdir mkdir vscode
    git clone https://github.com/nighthawkcoders/teacher.git
    # run script, path vscode/teacher are baked in script
    ~/vscode/teacher/scripts/activate_macos.sh
    #=== !!!Start a new Terminal!!! ===
    #=== Continue to next section ===
    ```
    
    
    ### Run Preview Server
    - The result of these step is server running on: http://0.0.0.0:4100/teacher/.  Regeneration messages will run in terminal on any save and update site upon refresh.  Terminal is active, press the Enter or Return key in the terminal at any time to see prompt to enter commands.
    
    - Complete installation
    ```bash
    cd ~/vscode/teacher
    bundle install
    make
    ```
    - Run Server.  This requires running terminal commands `make`, `make stop`, `make clean`, or `make convert` to manage the running server.  Logging of details will appear in terminal.   A `Makefile` has been created in project to support commands and start processes.
    
        - Start preview server in terminal
        ```bash
        cd ~/vscode/teacher  # my project location, adapt as necessary
        make
        ```
    
        - Terminal output of shows server address. Cmd or Ctl click http location to open preview server in browser. Example Server address message... 
        ```
        Server address: http://0.0.0.0:4100/teacher/
        ```
    
        - Save on ipynb or md activiates "regeneration". Refresh browser to see updates. Example terminal message...
        ```
        Regenerating: 1 file(s) changed at 2023-07-31 06:54:32
            _notebooks/2024-01-04-cockpit-setup.ipynb
        ```
    
        - Terminal message are generated from background processes.  Click return or enter to obtain prompt and use terminal as needed for other tasks.  Alway return to root of project `cd ~/vscode/teacher` for all "make" actions. 
            
    
        - Stop preview server, but leave constructed files in project for your review.
        ```bash
        make stop
        ```
    
        - Stop server and "clean" constructed files, best choice when renaming files to eliminate potential duplicates in constructed files.
        ```bash
        make clean
        ```
    
        - Test notebook conversions, best choice to see if IPYNB conversion is acting up.
        ```bash
        make convert
        ```
        
    end of README.md


### Env, Git and GitHub
> Env(ironment) is used to capture things like path to Code or Home directory.  Git and GitHub is NOT Only used to exchange code between individuals, it is often used to exchange code through servers, in our case deployment for Website.   All tools we use have a behind the scenes hav relationship with the system they run on (MacOS, Windows, Linus) or a relationship with servers which they are connected to (ie GitHub).  There is an "env" command in bash.  There are environment files and setting files (.git/config) for Git.  They both use a key/value concept.

- "env" show setting for your shell
- "git clone" sets up a director of files
- "cd $project" allows user to move inside that directory of files
- ".git" is a hidden directory that is used by git to establish relationship between machine and the git server on GitHub.  


```python
%%script bash

# This command has no dependencies

echo "Show the shell environment variables, key on left of equal value on right"
echo ""

env
```

    Show the shell environment variables, key on left of equal value on right
    
    MANPATH=/usr/local/share/man::
    VSCODE_CRASH_REPORTER_PROCESS_TYPE=extensionHost
    TERM=xterm-color
    SHELL=/bin/zsh
    CLICOLOR=1
    TMPDIR=/var/folders/3r/_pbvf6d522957yhk2jxc75440000gn/T/
    HOMEBREW_REPOSITORY=/usr/local/Homebrew
    PYTHONUNBUFFERED=1
    ORIGINAL_XDG_CURRENT_DESKTOP=undefined
    MallocNanoZone=0
    PYDEVD_USE_FRAME_EVAL=NO
    PYTHONIOENCODING=utf-8
    USER=rayanesouissi
    COMMAND_MODE=unix2003
    SSH_AUTH_SOCK=/private/tmp/com.apple.launchd.5wFZ6MNmH3/Listeners
    __CF_USER_TEXT_ENCODING=0x1F5:0x0:0x0
    PAGER=cat
    ELECTRON_RUN_AS_NODE=1
    VSCODE_AMD_ENTRYPOINT=vs/workbench/api/node/extensionHostProcess
    PATH=/usr/local/bin:/Users/rayanesouissi/Library/Python/3.11/bin:/usr/local/bin:/usr/local/sbin:/opt/local/bin:/opt/local/sbin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin:/usr/local/sbin:/opt/local/bin:/opt/local/sbin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
    __CFBundleIdentifier=com.microsoft.VSCode
    PWD=/Users/rayanesouissi/vscode/studentrep/_notebooks
    VSCODE_HANDLES_UNCAUGHT_ERRORS=true
    MPLBACKEND=module://matplotlib_inline.backend_inline
    XPC_FLAGS=0x0
    FORCE_COLOR=1
    XPC_SERVICE_NAME=0
    SHLVL=1
    HOME=/Users/rayanesouissi
    VSCODE_NLS_CONFIG={"locale":"en-us","osLocale":"en-us","availableLanguages":{},"_languagePackSupport":true}
    PYDEVD_IPYTHON_COMPATIBLE_DEBUGGING=1
    HOMEBREW_PREFIX=/usr/local
    LOGNAME=rayanesouissi
    LC_CTYPE=UTF-8
    VSCODE_IPC_HOOK=/Users/rayanesouissi/Library/Application Support/Code/1.81-main.sock
    VSCODE_CODE_CACHE_PATH=/Users/rayanesouissi/Library/Application Support/Code/CachedData/6c3e3dba23e8fadc360aed75ce363ba185c49794
    CLICOLOR_FORCE=1
    VSCODE_PID=35861
    INFOPATH=/usr/local/share/info:
    HOMEBREW_CELLAR=/usr/local/Cellar
    GIT_PAGER=cat
    VSCODE_L10N_BUNDLE_LOCATION=
    VSCODE_CWD=/
    _=/usr/bin/env



```python
%%script bash

# Extract saved variables
source /tmp/variables.sh

cd $project

echo ""
echo "show the secrets of .git"
cd .git
ls -l

echo ""
echo "look at config file"
cat config
```

    
    show the secrets of .git
    total 88
    -rw-r--r--   1 rayanesouissi  staff    222 Sep 20 11:10 FETCH_HEAD
    -rw-r--r--   1 rayanesouissi  staff     21 Aug 16 21:48 HEAD
    -rw-r--r--   1 rayanesouissi  staff     41 Sep 20 11:10 ORIG_HEAD
    -rw-r--r--   1 rayanesouissi  staff    312 Aug 16 21:48 config
    -rw-r--r--   1 rayanesouissi  staff     73 Aug 16 21:48 description
    drwxr-xr-x  15 rayanesouissi  staff    480 Aug 16 21:48 [34mhooks[m[m
    -rw-r--r--   1 rayanesouissi  staff  17900 Sep 20 11:30 index
    drwxr-xr-x   3 rayanesouissi  staff     96 Aug 16 21:48 [34minfo[m[m
    drwxr-xr-x   4 rayanesouissi  staff    128 Aug 16 21:48 [34mlogs[m[m
    drwxr-xr-x  84 rayanesouissi  staff   2688 Sep 20 11:10 [34mobjects[m[m
    -rw-r--r--   1 rayanesouissi  staff    112 Aug 16 21:48 packed-refs
    drwxr-xr-x   5 rayanesouissi  staff    160 Aug 16 21:48 [34mrefs[m[m
    
    look at config file
    [core]
    	repositoryformatversion = 0
    	filemode = true
    	bare = false
    	logallrefupdates = true
    	ignorecase = true
    	precomposeunicode = true
    [remote "origin"]
    	url = https://github.com/nighthawkcoders/teacher.git
    	fetch = +refs/heads/*:refs/remotes/origin/*
    [branch "main"]
    	remote = origin
    	merge = refs/heads/main


### Student Request - Make a file in Bash
> This example was requested by a student (Jun Lim, CSA). The request was to make jupyer file using bash, I adapted the request to markdown.  This type of thought will have great extrapolation to coding and possibilities of using List, Arrays, or APIs to build user interfaces.  JavaScript is a language where building HTML is very common.

> To get more interesting output from terminal, this will require using something like mdless (https://github.com/ttscoff/mdless).  This enables see markdown in rendered format.
- On Desktop [Install PKG from MacPorts](https://www.macports.org/install.php)
- In Terminal on MacOS
    - [Install ncurses](https://ports.macports.org/port/ncurses/)
    - ```gem install mdless```
    
> Output of the example is much nicer in "jupyter"


```python
%%script bash

# This example has error in VSCode, it run best on Jupyter
cd /tmp

file="sample.md"
if [ -f "$file" ]; then
    rm $file
fi

tee -a $file >/dev/null <<EOF
# Show Generated Markdown
This introductory paragraph and this line and the title above are generated using tee with the standard input (<<) redirection operator.
- This bulleted element is still part of the tee body.
EOF

echo "- This bulleted element and lines below are generated using echo with standard output (>>) redirection operator." >> $file
echo "- The list definition, as is, is using space to seperate lines.  Thus the use of commas and hyphens in output." >> $file
actions=("ls,list-directory" "cd,change-directory" "pwd,present-working-directory" "if-then-fi,test-condition" "env,bash-environment-variables" "cat,view-file-contents" "tee,write-to-output" "echo,display-content-of-string" "echo_text_>\$file,write-content-to-file" "echo_text_>>\$file,append-content-to-file")
for action in ${actions[@]}; do  # for loop is very similar to other language, though [@], semi-colon, do are new
  action=${action//-/ }  # convert dash to space
  action=${action//,/: } # convert comma to colon
  action=${action//_text_/ \"sample text\" } # convert _text_ to sample text, note escape character \ to avoid "" having meaning
  echo "    - ${action//-/ }" >> $file  # echo is redirected to file with >>
done

echo ""
echo "File listing and status"
ls -l $file # list file
wc $file   # show words
mdless $file  # this requires installation, but renders markown from terminal

rm $file  # clean up termporary file
```

    
    File listing and status
    -rw-r--r--  1 rayanesouissi  wheel  809 Sep 27 23:58 sample.md
          15     132     809 sample.md


    bash: line 30: mdless: command not found


## Hack Preparation.
> Review Tool Setup Procedures and think about some thing you could verify through a Shell notebook.
- Come up with your own student view of this procedure to show your tools are installed.
- Name and create notes on some Linux commands you will use frequently.
- Is there anything we use to verify tools we install? Review versions checks.
- Is there anything we could verify with Anaconda?  or WSL?  
- How would you update a repository?  Could you do that in script above?

