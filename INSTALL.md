# Installation Instructions

These instructions are intended to aid in the process of adding CI testing to an existing project.  The assumption is made that no other testing is in place already. It is recommended that these steps be completed as the first steps in establishing a new repository.

Note: The tools used in this process only run on *nix based operating systems, there is currently no support for automating testing on windows.


##Installation Steps

####Prepare to install

* Ensure you have an up to date clone of the repository you will be adding testing to, open a command shell or other git utility to the project's root folder
* Create and switch to a new branch called ci
* Download the latest copy of the CI_template to your computer

####Add the CI Compnents to your project

* Copy the .travis.yml file from CI_Template to the root of your project
* Copy the entire tests folder to the root of your project

####Travis-CI Configurations

* Open the .travis.yml file 
* Modify/add the emails which should receive notifications for build pass/fail.
* Modify the branch list for branches that testing will run.  What is present is recommended by default.
* Modify any other settings if required, however this should be fine for most setups.

####Bootstrap your Plugin/Theme

* Open tests/bootstrap.php
* Beginning on line 10, modify the initial file to be included for testing.  This is typically the main plugin php file, or a themes functions.php.  Be sure to use parent pathing ( ../ ) as the Bootstrap.php runs from the tests folder.
* Additional files, or dependencies may be added after line 10.

####Create your own Unit Tests

* Modify or rename/create new test files in the tests/custom_tests path.  Files must be prefixed with test- and the sample template provides a basic structure for setup, teardown and custom test cases.

##Additional Reading

Please review the following for information on creating unit tests for WordPress.

* https://make.wordpress.org/core/handbook/automated-testing/
* http://wordpress.tv/2011/08/20/nikolay-bachiyski-unit-testing-will-change-your-life/
* https://make.wordpress.org/core/handbook/coding-standards/php/

##Executing tests on Travis-CI

In order to execute the tests you will need to have the repository setup on github with travis-ci, please speak to the Integration team to enable this setting.

Once the setting is enabled, any push of code to the branches configured will initiate testing, access to the build results will be available from the travis-ci website and a link should be provided when Integration enables CI on your project.

## Running tests locally

Local execution can be done on *nix based systems only.  In order to do this you need to execute the install-wp-tests.sh script like:

	$> tests/install-wp-tests.sh wordpress_test root '' localhost

You will need to provide the proper username/password and server information for the database, executing the script without any parameters provides the usage information.

*WARNING* Execution of the test will delete the database specified, it will not prompt you, do not specify an existing database.

Once the Installation is complete you can execute the tests

	$> phpunit -c tests/phpunit.xml

For code standards you would execute

	$> /tmp/php-codesniffer/scripts/phpcs -p -s -v -n ../ --standard=./tests/codesniffer.ruleset.xml --extensions=php

##Questions

If you have any questions or issues please contact the Integration Team <pdtechintegration@postmedia.com> for support.
