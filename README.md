ansible-role-drupal
==========

Description
------------
A role for deploying Drupal with a set of modules and themes from their git
repositories.
Inspired by [Wim Leers' mr-drupal method](http://wimleers.com/article/mr-drupal).

Requirements
------------
Requires drush and mysql on the target. There is no dependency to a specific role
because that really limits the usefulness for anyone not wanting to use those
exact roles.

Role Variables
--------------

drupal_config_directory: Absolute path for D8 config.
drupal_multisite_directory: Absolute path for site files, commonly webroot/sites/default.
drupal_sites_dir: Directory used for all the drupal (or other) sites on the host.
dev_group: If you want a group (for dev access) to be set for the site, use this.
server_admin_email: admin@example.com
site_admin_email: admin@example.com

install_profile: Which install profile to use
locale: What to set as the locale.
drupal_git_base: Prefix for drupal.org git repositories.

site_name: Name of the site.

Notes
-----
* Only works with Drupal 8
* No versions are added so Drupal can't track updates
* .git directories will be inside the webroot
* Still a bit rough around the edges

Example Playbook
-------------------------

    - role: drupal
      site_name: drupal
      core: HEAD
      db:
        user: drupal_user
        name: drupal_db
        password: mypassword

You probably want to put this in a site-specific role as a dependency and
specify the variables there.

License
-------

MIT
