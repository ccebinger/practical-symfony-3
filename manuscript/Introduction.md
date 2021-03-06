# Introduction

Building an application is like building a Pyramid. You create each piece of functionality bit by bit. You test the functionality and make sure its stable before building the next piece. This cycle continues until you reach the peak - completion.

Choosing the best framework for RAD (Rapid Application Development) has been a topic debated to death. Today, there is no longer such a thing as "The Best Framework" because all modern day frameworks follow the best practice. However, there is such a thing called "The Best Practice". In fact, you can see similar development methodologies being used across all frameworks. So knowing one framework well means you can jump between other frameworks easily. Just as human evolves, different frameworks learn from each other and adapt very fast to new and better technologies.

At the time of writing, NodeJS continues to innovate with PHP closing in fast behind. PHP is the old veteran when comes to web development with the most frameworks in the market. The 2 frameworks that stood out from the pack were Laravel and Symfony. If you are looking to learn a new framework, I highly recommend Symfony because it is one of the more stable modern framework out there. Symfony components have been widely used by many popular projects including Composer, Behat, Codeception, Drupal and Laravel (just to name a few).

Learning Symfony is never an easy task. Many people follow tutorials in google, read up all the documentation in [Symfony website](http://symfony.com) and still find it challenging to create a simple application. Why? Because there is too much theory and not enough real world practical examples. Worst still, you can get entangled in technical jargons and advance customisations easily. The fact that Symfony is an extremely flexible framework makes it even harder to master because there are so many ways to achieve the same goal. If you are new to MVC (Model-View-Controller) and RAD, you will find that Symfony has a steep learning curve.

This book aims to lower the learning curve by providing a step by step hands-on approach to guide developers who are new to Symfony to build a simple CMS using good industry practice. Let us call the CMS "SongBird". Hopefully after following all the chapters, your eyes will be opened to RAD and the unlimited possibilities with Symfony. 

## Audience

This book is targeted at developers who are new to Symfony. If you are already a seasoned PHP Developer, I hope you would pick up some tips here and there.

## Why Re-invent the Wheel?

At the time of writing, there are already many CMS and a few popular Symfony ones out there. Symfony has the [CMF project](http://cmf.symfony.com/). Why built a new one? 

SongBird is really a tutorial project and not trying to compete in the CMS space.

## Is SongBird Reusable?

Definitely. SongBird is not just a tutorial CMS, you can use it as a vanilla framework to kickstart other Symfony projects. It will be a hugh time saver because all common features have been build and configured already. Since you are the one who creates the software, you will have better idea of how the software works and know where to customise things should the need arises. 

You can also think of SongBird as the foundation for the [CMF project](http://cmf.symfony.com/). Once you are comfortable with the basics of building a CMS, you are ready for more complex development.

## Chapters Overview

**Chapter 1: Survival Skills**

A quick introduction to the skills required to learn Symfony.

**Chapter 2: What is SongBird**
 
Introduction to what Songbird is and isn't.

**Chapter 3: Creating the Dev Environment**

Installing Songbird using docker. Docker is fantastic but its a shame that mac users need a work around at the time of writing.

**Chapter 4: The Testing Framework Part 1 (Optional)**

Introduces and Installing Codeception for Behavioural Testing.

**Chapter 5: The Testing Framework Part 2 (Optional)**

Writing a sample BDD acceptance test.

**Chapter 6: The User Management System Part 1**

Introduces and Installing FOSUserBundle for User Management.

**Chapter 7: The User Management System Part 2**

Generating user CRUD using the command line and a bit of doctrine appetizer.

**Chapter 8: Doctrine Fixtures and Migrations**

Installing and running Doctrine Fixtures and Migrations. It is important to have a consistent way of creating test data and migrating schemas.

**Chapter 9: The Admin Panel Part 1**

Installing EasyAdminBundle and integrating it with FOSUserBundle.

**Chapter 10: BDD With Codeception (Optional)**

Writing BDD acceptance tests for user management business rules.

**Chapter 11: Customising the Login Process**

Customising Twig templates for the login and request password pages.

**Chapter 12: The Admin Panel Part 2**

Tweaking EasyAdmin UI.

**Chapter 13: Internalisation**

Getting Songbird to support french as well.

**Chapter 14: Uploading Files**

Installing VichUploaderBundle and integrating it with EasyAdminBundle.
 
**Chapter 15: Logging User Activities**

Creating a simple bundle to log user activities.
 
**Chapter 16: Improving Performance and Troubleshooting**

Installing blackfire and improving Symfony performance. Introduces Gulp to manage all frontend assets.

**Chapter 17: The Page Manager Part 1**

Creating a custom bundle called NestablePageBundle to manage pages. Introduces PHPUnit to write functional tests.
 
**Chapter 18: Making Your Bundle Reusable**

Refactoring NestablePageBundle and making it as a separate installable component.
 
**Chapter 19: The Page Manager Part 2**

Installing CKEditor to the CMS and creating a custom locale selector.
 
**Chapter 20: The Front View**

Creating the frontend controller and view.
 
**Chapter 21: Dependency Injection Revisited**

Using Compiler Pass to add user roles to EasyAdminBundle.

**Chapter Final**

Congratulations. It's time to start build something yourself using Symfony.

## Conventions Used in This Book

**Each git branch is a chapter**. Obviously, chapter_6 branch means it is Chapter 6. Otherwise stated, all path references assumes **~/songbird** as the root folder. Always execute commands from the root folder.

To executing commands, You will see a "->" before the command. For example

```
-> git status

On branch chapter_6
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   symfony/app/AppKernel.php
	modified:   symfony/app/config/routing.yml

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	symfony/src/myfolder/

no changes added to commit (use "git add" and/or "git commit -a")
```

This means that in the command line terminal, go to the ~/songbird folder and type in "git status".

Likewise, a code snippet like this

```
# symfony/app/config/routing.yml
...
Songbird_user:
    resource: "@SongbirdUserBundle/Controller/"
    type:     annotation
    prefix:   /
```

means update or insert this snippet in ~/songbird/symfony/app/config/routing.yml

or it could mean a comment for you to action like

```
# you should commit your changes now.
-> git commit -m"update file changes"
```

**All symfony commands** runs under the symfony dir, ie

```
# in the symfony dir
-> bin/console debug:router
```

## Learning Symfony

If you are new to RAD and like to learn Symfony, I recommend you to go through the chapters in sequential order. Every time you are on a new chapter, create a new branch based on the previous chapter and try to add or update the code as suggested in the chapter. For example, you have just finished chapter 4 and going into chapter 5.

Commit all your changes in chapter 4 first.

```
-> git commit -m"This is chapter 4 commit comments"
```

Then checkout chapter 5.

```
# this command will create a new mychapter_5 branch based off your current branch
-> git checkout -b mychapter_5
``` 

We use mychapter_x to differentiate between your work and my work. To look at all the branches available:

```
-> git branch -a

  mychapter_4
* mychapter_5
  ...
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/chapter_4
  remotes/origin/chapter_5
  ...
```

If you are being lazy and want to use my chapter 4 instead to start chapter 5,

```
-> git checkout -b mychapter_5 origin/chapter_4
```

If you are already getting confused, here are some good [git resource](https://help.github.com/articles/good-resources-for-learning-git-and-github/) to read.

## Jumping between Chapters

I have organised the repository such that every chapter will have its own corresponding branch in the code. Feel free to jump between the different chapters and test out the code. However, remember to [stash](https://git-scm.com/book/en/v1/Git-Tools-Stashing) or commit your changes before switching to a new branch. Also remember to clear your cache if things are broken.

Chapters that talk about [Codeception Testing Framework](http://codeception.com/) are optional. Feel free to skip them if you already know testing.

To clear the cache fully,

```
rm -rf symfony/var/cache/*
```

## Regenerating Bootstrap Cache

If you are getting errors on bootstrap.php.cache, you can regenerate it easily.

```
-> symfony/vendor/sensio/distribution-bundle/Resources/bin/build_bootstrap.php
```

## Composer Memory Errors

Refer to [composer troubleshooting guide](https://getcomposer.org/doc/articles/troubleshooting.md) if you have problems using composer.

A common issue is when you get allowed memory exhausted error. A quick workaround is

```
-> php -d memory_limit=-1 path_to_composer update
```

## Reinstalling Symfony

Some directories are needed by Symfony but they are not version controlled (eg. the bin directory). In case they have been deleted accidentally, you can reinstall the packages. The re-installation process will not mess up with your existing code. That's the beauty of being modular.

```
rm -rf vendor
composer update
```

## Installing the Demo (Optional)

If you are already getting impatient and wants to see a demo of the completed project, you can checkout the final chapter. Make sure you have docker and docker-compose installed.

```
# If you are new to web development, you might be unfamiliar with some of the commands here. Don't worry as they will be explained as you follow through the chapters sequentially.

-> git clone https://github.com/bernardpeh/songbird
-> cd songbird
-> git checkout chapter_final

# update SYMFONY_APP_PATH parameters in the .env file and leave the rest as defaults
-> cp .env.dist .env

# we need to create new dir when mounting docker (if case if using nfs)
-> mkdir -p .data/db
-> mkdir -p logs/{symfony,nginx}
-> cd symfony

# See chapter 3 to improve mac performance before continuing (if you are interested)
-> docker-compose up --build -d

# To confirm all your containers are running
-> docker-compose ps

# add ip to your host file (assuming you are in unix env)
-> sudo echo "127.0.0.1 songbird.app" >> /etc/hosts

# create the uploads dir
mkdir -p web/uploads/{profiles,featured_images}

# install symfony libraries - ignore the db errors when running composer install
-> ./scripts/composer install

# install db and fixtures 
-> ./scripts/resetapp

# install js libraries
-> bower install
-> npm install

# install assets
-> gulp
```

*Docker could be slower for mac users. Chapter 3 provides a workaround.*

Now go to http://songbird.app:8000 and you should see the homepage.

![](images/cms_final.png)

You can log into the backend by going to http://songbird.app:8000/admin using 

```
user: admin
password: admin
```

To run full BDD test on the site

```
# Optional Step to check site is fully functional
-> ./scripts/runtest
```

## References

* [RAD](https://en.wikipedia.org/wiki/Rapid_application_development)

* [Agile Software Development](https://en.wikipedia.org/wiki/Agile_software_development)
