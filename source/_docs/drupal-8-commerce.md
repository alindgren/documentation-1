---
title: Drupal Commerce on Drupal 8
description: FILL ME IN WITH INFORMATION!
contributors: [alexfornuto, rachelwhitton]
tags: [drupal]
---

This self-referencing document can be used as a starting point to write your own new doc for Pantheon. Start with an overview of the topic, which may include a summary of what will be accomplished after following the instructions.

<div class="alert alert-info">
<h4 class="info">Note</h4><p markdown="1">For optimal use of this document, consider viewing the markdown file and rendered page in Sculpin side-by-side. Any important points the customer needs to be made aware of can be put in a note like this.
</p>
</div>

## Before You Begin

Here's a list of prerequisites or technical requirements a user must have or understand before starting the task. This is a good place to use:

 - Make sure your PHP version is compatible with Pantheon
 - Install git, if necessary
 - Install composer, if necessary


Make sure your PHP version is compatible with Pantheon


## Create A New Drupal 8 Site

1.  Create a new site on Pantheon, note site name, deploy Drupal 8:

        terminus ...

    DO NOT INSTALL

2.  Put site in git mode:

        terminus ...

### Replace The Upstream

3.  Copy your Git Connection Info into a text file to get the `ssh:// ... repository.git` URL.


4.  In terminal, navigate to location for local site root:

        cd ~/projects/my-awesome-site

5.  Execute commands, replacing my-site with your site name and `ssh://ID@ID.drush.in:2222/~/repository.git` with your repository URL:

        composer create-project pantheon-systems/example-drops-8-composer my-site
        cd my-site
        composer prepare-for-pantheon
        git init
        git add -A .
        git commit -m "web and vendor directory from composer install"
        git remote add origin ssh://ID@ID.drush.in:2222/~/repository.git
        git push --force origin master

    See: https://github.com/pantheon-systems/example-drops-8-composer

6.  Return to Pantheon site, switch to SFTP mode:

        terminus

7.  Visit Development Site, install, select Standard profile.

    SCREENSHOT

### Install The Drupal Commerce Module

8.  Switch site back to git mode:

        terminus ...

9.  Execute these composer commands to install Drupal Commerce:

        composer config repositories.drupal composer https://packages.drupal.org/8
        composer require "drupal/commerce 2.x-dev"

    See: http://docs.drupalcommerce.org/v2/getting-started/install.html

10. Use the composer prepare-for-pantheon command again to get rid of submodule repositories:


        composer prepare-for-pantheon

11. Commit and push changes to Pantheon:

        git status
        git add -A .
        git commit -m "Install Drupal Commerce"
        git push origin master

12. Return to Pantheon and install Commerce modules: Product, Checkout, Cart



## Second Major Step





##See Also

If you can, end your doc with links to external resources that can be used to improve the reader's comprehension, or to guides on logical next steps in a common development workflow.

 - [An internal guide with a relative link](/docs/get-started)
 - [An external guide with a full URL](http://writing.rocks/)
