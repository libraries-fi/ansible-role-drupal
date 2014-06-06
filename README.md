ansible-role-drupal
==========

Description
------------
A role for deploying Drupal with a set of modules and themes from their git
repositories.
Inspired by [Wim Leers' mr-drupal method](http://wimleers.com/article/mr-drupal).

Requirements
------------
Requires at least drush, mysql. There is no dependency to a specific role
because that really limits the usefulness for anyone not wanting to use those
exact roles.

Notes
-----
* Only works with Drupal 8
* No versions are added so Drupal can't track updates
* .git directories will be inside the webroot
* Still a bit rough around the edges

Simple example usage
--------------------
    - role: drupal
      site_name: drupal
      core: HEAD
      db:
        user: drupal_user
        name: drupal_db
        password: mypassword

You probably want to put this in a site-specific role as a dependency and
specify the variables there.
