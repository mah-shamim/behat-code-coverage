Installation
============

The recommended way to install Behat Code Coverage is to use `Composer`_. From the command line simply execute the following to add
``dvdoug/behat-code-coverage`` to the ``require-dev`` section of your project's ``composer.json`` file. Composer will
automatically take care of downloading the source and configuring an autoloader:

.. code::

    composer require --dev dvdoug/behat-code-coverage

The code is also available to download from `GitHub`_

After installation, in your project's ``behat.yml`` or ``behat.yml.dist``, add ``DVDoug\Behat\CodeCoverage\Extension``
into the ``extensions`` key under ``default`` to enable it.

The below example represents a typical configuration you may wish to use as a starting point. Each option is more fully
explained in the next section.

.. code:: yaml

    default:
        extensions:
            DVDoug\Behat\CodeCoverage\Extension:
                filter:
                    include:
                        directories:
                            'src': ~
                reports:
                    html:
                        target: build/coverage-behat
                    text:
                        showColors: true

Compatibility
-------------
Since both PHPUnit and Behat Code Coverage both depend upon php-code-coverage, it is not always possible to run an
older version of PHPUnit alongside the newest version of this library or vice versa since they both need to be compatible
with the same underlying version of the code coverage component. Where reasonably possible Behat Code Coverage maintains
support for multiple versions of the coverage library to ease the upgrade path, however where a new version is
significantly incompatible with older ones or where a compelling new feature exists the minimum supported version may be
raised. Fixes for any subsequently discovered bugs will be backported as appropriate.


.. _Composer: https://getcomposer.org
.. _GitHub: https://github.com/dvdoug/behat-code-coverage
