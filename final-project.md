# Final Project

The final project for this class will be due at the end of the 
semester.  The task is to reproduce the architecture from class
in order to develop, test, build, package, deploy, and monitor
a website of your own.  This will focus on two aspects.  1) 
how well you can replicate the infrastructure we've 
worked on in class and 2) how well you can
explain the whats, whys, and hows of your setup.

## Documentation

Documentation will account for a large portion of the grade for 
the final project. The goal of the documentation is to demonstrate 
your familiarity with the various pieces. Make sure to you 
work on the documentation as you build your project to ensure
the highest quality and accuracy of your information. The target audience of
your documentation should be your former selves (at the start
of class) or students starting this class next year.

The documentation should include sections on each
portion of the architecture with details on:

* What role that portion plays in the overall architecture
* Advantages and disadvantages to the program or service used compared to alternatives in the same space
* Picture(s) to help convey your understanding of the program or service
* Samples of any commands or workflows regularly used

### Changelog

A changelog.md file should be included in your github repo.  This serves as
a record of what improvements/bug fixes were included between
each version.  A sample changelog can be found [here](https://github.com/olivierlacan/keep-a-changelog/blob/master/CHANGELOG.md).
Remember, the last number is incremented for patches and bug fixes.
The middle number for new features.  The first number for changes
that would break backwards compatibility. (http://semver.org/)
This log should allow users to determine what features
are available for what docker images.

## Execution

* Your website should have a minimum of 3 pages (main and 2 sub pages not including the metrics page)
* Each page should be added separately so that separate docker images and git tag are available for each new page

## Git

* The name of the new repo is up to you
* Pull requests shall show passing docker cloud tests (once that integration is setup)
* All changes to the master branch (beyond the inital commit) shall be done
through pull requests.
* All commit messages should be informative

## Docker Cloud

* Create a new docker cloud repository and connect it to the new github account
* Integrated with your github repo to perform PR validation builds
* Setup automated builds against the new github repository
	* Configure AUTOTEST off Internal PRs (with a small node)
* builds images
	* "latest" off of the master branch
	* "release-#.#.#" off semantic versioned git tags

## Unit Tests

Your new website should have a similar flask `*_test.py` testing file
configured to test if your webpages load and whether they contain
the desired content.

* The unit tests should check the output of each page
* A new unit test should be added with each new page

## Ansible

Each new page addition to the website should be followed
by a change to your ansible configuration with
the staging version promoted to production and
the newly built image run in staging. The staging 
and production containers should be run off of
the release-#.#.# docker images (not latest).

The final state of your server should have the completed
website running in the staging environment and the
production environment running a previous release.

## Monitoring

Application and system metrics should be accessible
via the `/metrics` page.  Page hit counts and 
page render times should be included in the metrics
as with the docker-cloud-test project.

## Virtualization

Emails will be sent to your address in Canvas with 
server information.


Good Luck,

Dan Couture