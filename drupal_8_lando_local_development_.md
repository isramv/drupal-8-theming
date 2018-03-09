# Using lando to spin up a local development site.

Lando uses docker containers to create local development environments within minutes, with this tool we are going to be able to use a local development environment with all the tools required for Drupal 8 development.

### Before continue:

please check if your system meets the requirement: [Lando Hardware Requirements](https://docs.devwithlando.io/installation/system-requirements.html) if your system doesn't support Lando, you might want use Acquia Dev Desktop instead, follow this [Instructions](https://docs.google.com/document/d/1KflNYF_HaTsbwQc0SEaeTBwNvvNm26Qxay2pAR17vwE/edit)

## Installing lando:

If you have already installed Docker CE, Quit Docker before proceed.

  1. Get your lando installer from the [lando releases page](https://github.com/lando/lando/releases) and install [Install Instructions](https://docs.devwithlando.io/installation/installing.html).
  
## Getting familiar with the terminal:

Once you install lando and Docker we should get familiar with the terminal, this is a critical step because Drupal 8 uses composer to manage the dependencies and install your Drupal instance.

Open the terminal, iTerm or similar:

for the purpuse of this training create a empty directory:

```bash
$ mkdir ~/training
```
or
```bash
$ mkdir $HOME/training
```

Access the directory:

```bash
$ cd ~/training/
```

## Composer way:

If you have composer available from your system, execute:

```bash
$ composer create-project drupal-composer/drupal-project:8.x-dev drupal --stability dev --no-interaction
```

## Git way:

```bash
$ git clone git@github.com:drupal-composer/drupal-project.git drupal
```
## Lando init

In order to use Lando we need a `.lando.yml` file, this lando file should contain All the things you require to run and develop our first theme.

then we are going to init a Drupal 8 project:

```bash
$ lando init --recipe drupal8
```
You are going to answer the following questions:

in the following example I decided to call my lando project: drupal-8-theme-development, you can name it whatever you want:

```bash
$ ? Where is your webroot relative to the init destination? drupal/web
$ ? What do you want to call this app? D8 theming
```

All the files that are begin with dot like: `.lando.yml` aren't visible with the command `ls`
you need to use `ls -la` which shows hidden files

```bash
$ ls -la
```

Using `$ lando info` you'll be able to see the basic configuration of your web application.

# Using Lando Composer to install D8

```bash
$ lando composer install
```






  
  
  
