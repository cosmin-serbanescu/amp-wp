# AMP Contributing Guide

Thanks for taking the time to contribute!

To clone this repository
``` bash
$ git clone --recursive git@github.com:Automattic/amp-wp.git
```

### Updating Allowed Tags And Attributes

The file `class-amp-allowed-tags-generated.php` has the AMP specification's allowed tags and attributes. It's used in sanitization.
To update that file:
1. `cd` to the root of this plugin
2. run `bash bin/amphtml-update.sh`
That script is intended for a Linux environment like [VVV](https://github.com/Varying-Vagrant-Vagrants/VVV).

### Testing Media And Embed Support

The following script creates a post in order to test support for WordPress media and embeds.
To run it:
1. `ssh` into an environment like [VVV](https://github.com/Varying-Vagrant-Vagrants/VVV)
2. `cd` to the root of this plugin
3. run `wp eval-file bin/create-embed-test-post.php`
4. go to the URL that is output in the command line

### PHPUnit Testing

Please run these tests in an environment with WordPress unit tests installed, like [VVV](https://github.com/Varying-Vagrant-Vagrants/VVV).

Run tests:

``` bash
$ phpunit
```

Run tests with an HTML coverage report:

``` bash
$ phpunit --coverage-html /tmp/report
```

When you push a commit to your PR, Travis CI will run the PHPUnit tests and sniffs against the WordPress Coding Standards.