# RSE 102: git-workflows-exercises

This repository contains the exercises for the topic _git workflows_ of the [RSE102](https://github.com/RSE-102/Lecture-Material) course.
The corresponding lecture slides can be found at [sustainable-simulation-software.gitlab.io](https://sustainable-simulation-software.gitlab.io/course-material/slides/git_intro/workflows/index.html#/title-slide).

Note that the code of the exercises builds upon each other. Thus, you need exercise 1,
for instance, to be completed before you can continue with exercise 2. Each exercise
contains some tasks that are described in the comments of the respective `.py` file.

Typically, each one of you will have to make one of the already existing tests pass.
The tests in a file can be run with `pytest`, for instance, with `python3 -m pytest FILENAME.py`.
To run only the test you are working on, use `python3 -m pytest FILENAME.py -k TESTNAME`.


## Preparation

The exercises should be worked on in groups of two people.
Start as follows: One of you creates a new remote repository,
e.g. on `github.com`. Then, copy the `*.py` files and `README.md`
into a new folder on your machine and follow the instructions given
in your remote repository on how to upload these files into the newly
created repository.

You should now have a fresh, remotely available repository containing the
exercises. The other person can now fork this repository, such that both
of you can work independent of each other on different tasks in different
repositories. The first, newly created repository will serve as the "mainline repo"
throughout the exercise. This means that the person owning the fork will open pull
requests into the main branch of the "mainline repo", while the owner of
the "mainline repo" creates branches and pull requests directly in there.

Each individual task should be worked on on a dedicated branch. Avoid making commits
to the main branch except via the acceptance of pull requests. Also, do not merge
branches locally, but do all merges via pull requests on your remote repository (on `github.com`).

`GitHub` allows you to decide whether the acceptance of a pull request should yield
a _merge commit_ or not. To this end, open the dropdown-menu on the right side of the
_merge pull request_ button. If you select "rebase and merge", no merge commit will be
created, and, a rebase will be performed prior to merging. In the exercises, you will
have to do manual rebases locally in order to arrive at the desired git histories.


## Exercise 1

- Distribute the two tasks and work on them in parallel:
  - create a branch for your task, giving it an appropriate name (note: task A is not an appropriate name. Use names that describe what is changed/implemented.)
  - commit the solution to your task onto that branch in a single commit with appropriate name
  - push your commit to the remote repository
  - open a pull request into the main branch of the "mainline repo"
  - Together, integrate both tasks via the pull requests, but take care that the final git history looks like this:
  ```sh
    * task B
    |
    * task A
    |
    * your initial commit
  ```
  - In order to achieve this, you can rebase the branch for task B after having merged task A locally, or,
    use the "rebase and merge" option in the pull request.



## Exercise 2

- repeat the same procedure as from exercise 1, but with the file `exercise2.py`
- this time we want a semi-linear history, which should now continue like this:
  ```sh
    * merge ex2 task B
    | \
    |  * ex2 task B
    | /
    * merge ex2 task A
    | \
    |  * ex2 task A
    | /
    * last commit of exercise 1
    ...
    ```
- again, proper commit messages and branch names should be used
- this time, rebasing the branch for task B will lead to conflicts after task A has been merged. Do this rebase together,
  on the machine of the person that owns the "mainline repo"


## Exercise 3

- repeat the procedure from the previous exercises, but this time using the file `exercise3.py`
- we again want a semi-linear history, but this time the entire exercise should be done in one merge request:
  ```sh
    * merge ex3
    | \
    |  * ex3 task B
    |  * ex3 task A
    | /
    * merge ex2 task B (from last exercise)
    | \
    ...
    ```
- again, proper commit messages and branch names should be used


## Exercise 4

- in this exercise, we want to achieve yet a different layout of the git history:
  ```sh
    * merge ex4
    | \
    |  * merge ex4 task B
    |  | \
    |  |  * ex4 task B
    |  | /
    |  * merge ex4 task A
    |  | \
    |  |  * ex 4 task A
    |  | /
    |  * ex 4 task 0
    | /
    * merge ex3 (from last exercise)
    | \
    ...
    ```
- again, proper commit messages and branch names should be used


## License

   See `License` file.
