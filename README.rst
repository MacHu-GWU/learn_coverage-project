.. image:: https://travis-ci.org/MacHu-GWU/learn_coverage-project.svg?branch=master
    :target: https://travis-ci.org/MacHu-GWU/learn_coverage-project?branch=master

.. image:: https://coveralls.io/repos/github/MacHu-GWU/learn_coverage-project/badge.svg?branch=master
    :target: https://coveralls.io/github/MacHu-GWU/learn_coverage-project?branch=master

.. image:: https://img.shields.io/pypi/v/learn_coverage.svg
    :target: https://pypi.python.org/pypi/learn_coverage

.. image:: https://img.shields.io/pypi/l/learn_coverage.svg
    :target: https://pypi.python.org/pypi/learn_coverage

.. image:: https://img.shields.io/pypi/pyversions/learn_coverage.svg
    :target: https://pypi.python.org/pypi/learn_coverage

.. image:: https://img.shields.io/badge/Star_Me_on_GitHub!--None.svg?style=social
    :target: https://github.com/MacHu-GWU/learn_coverage-project


Welcome to ``learn_coverage`` Documentation
===========================================
This project is to learn doing code coverage test and continues integration using https://coveralls.io/.


What is Code coverage test?
------------------------------------------------------------------------------
Code coverage is a type of test to make sure all source code are executed during a test.

For example:

This is your source code:

.. code-block:: python

    def square_root(value):
        return square_root ** 0.5

    def power(base, times):
        return base ** times

This is your test code:

.. code-block:: python

    def test_square_root():
        assert square_root(4) == 2.0

Then your code coverage is 50%.


Code coverage in Python
------------------------------------------------------------------------------
There is a library called `coverage <Target>`_.

You just follow the `instruction <Target>`_, and create a ``.coveragerc`` file, put your configuration about:

- code / file you want to exclude / include
- how to report the coverage test result

Then you can use the rich-features command line tool to run your test script.


Code coverage integration with ``pytest``
------------------------------------------------------------------------------
`pytest <Target>`_ is a unittest framework, and its becoming semi-standard over Python community.

There is a library called `pytest-cov <Target>`_, can add more options to pytest command. And you don't need to change anything since you have a ``.coveragerc`` file, you just add ``--cov=<package_name>`` to ``pytest`` command.


Integration with `coveralls.io <https://coveralls.io/>`_
------------------------------------------------------------------------------
Like `travis-ci <https://travis-ci.org/>`_, `coveralls.io <https://coveralls.io/>`_ provides auto-coverage test everytime when you check-in to GitHub.

There's a library called `coveralls <https://pypi.python.org/pypi/coveralls>`_, can integrate your coverage test with `coveralls.io <https://coveralls.io/>`_.

How to:

1. Sign in `coveralls.io <https://coveralls.io/>`_ with your GitHub account, toggle your repo **ON**.
2. Edit your ``.travis.yml`` file.

.. code-block:: yaml

    install:
      - pip install --upgrade pytest-cov # Upgrade pytest-cov to latest
      - pip install coveralls # Install coverall

    script:
      - pytest tests --cov=<package_name> # Run Unittest

    after_success:
      coveralls # travis-ci will transfer data to coveralls after success






