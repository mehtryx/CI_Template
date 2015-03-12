CI for WordPress Plugins and Themes
==
Continuous Integration Template - Designed for use with Travis-ci or executed on a *nix based OS.
Based off of the combined work from many wordpress developers and VIP coding

Contributors: Keith Benedict <kbenedict@postmedia.com>, Michael Joseph <mjoseph@postmedia.com>

Tested up to : 4.2-alpha

Stable Tag: 1.0.2

Change Log
===========

V 1.0.3 - March 12, 2015
===========================
* Bug fix, used alias for git checkout, removed to use full command
* wp_version check, path had incorrect case
* changed parameter for the mysql password to --password from -p

V 1.0.2 - March 11, 2015
===========================
* Codesniffer ruleset is now in CI_Config, removed from this repo
* WP_Version is now in CI_Config, defining the value for latest
* Added subroutine to remove files and reset to default the paramters before executing install
* Drop database prior to creation (if exists) and added warning to readme that this command drops specified db

V 1.0.1 - March 9, 2015
===========================
* Updated repo with final changes for configuration module.

V 1.0.0 - January 15, 2015
===========================
* move to major release version 1.0.0
* finalize documentation for installation

V 0.0.9 - January 13, 2015
===========================
* installation script cleanup
* documentation initialized in INSTALL.md file
* template code updated
* paired down core tests to essentials

V 0.0.5 - November 8, 2014
===========================
* remove WCAG 2.0 tests for short term, revisit as a feature later
* clean up template files


V 0.0.4 - October 2, 2014
===========================
* inclusion of php syntax checker
* inclusion of php code sniffer
* initial testing of WCAG 2.0 testing

V 0.0.3 - September 8, 2014
===========================
* removed php 5.2 testing
* added templated test configuration
* added --quite to code repository check outs (reduce log length and noise)

V 0.0.2 - September 5, 2014
===========================
* updated install script for darwin and *nix support
* removed log folder contents from tracking
* added gitkeep to log folder to preserve for travis-ci

V 0.0.1 - July 15, 2014
===========================
* Added base 2014 theme for starting point on CI testing
* Updated Readme to include a Changelog, stable tag, contributors, description and version number