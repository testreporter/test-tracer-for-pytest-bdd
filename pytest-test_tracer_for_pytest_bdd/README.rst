=================================
Test Tracer for Pytest BDD
=================================

.. image:: https://img.shields.io/pypi/v/pytest-test-tracer-for-pytest.svg
    :target: https://pypi.org/project/pytest-test-tracer-for-pytest
    :alt: PyPI version

.. image:: https://img.shields.io/pypi/pyversions/pytest-test-tracer-for-pytest.svg
    :target: https://pypi.org/project/pytest-test-tracer-for-pytest
    :alt: Python versions

.. image:: https://github.com/testreporter/test-tracer-for-pytest/actions/workflows/main.yml/badge.svg
    :target: https://github.com/testreporter/test-tracer-for-pytest/actions/workflows/main.yml
    :alt: See Build Status on GitHub Actions

A plugin that allows collecting test data for use on Test Tracer. It is designed to be used with 
the `Pytest BDD`_ tool


Requirements
------------

* `Pytest BDD`_
* A free `Test Tracer`_ account
* An API token that allows uploading the test result



Installation
------------

You can install "pytest-test-tracer-for-pytest" via `pip`_ from `PyPI`_::

    $ pip install pytest-test-tracer-for-pytest


Usage
-----

Install the Plugin then activate it using the following Pytest parameters

.. list-table:: parameters
   :widths: 25 8 57 10
   :header-rows: 1

   * - Parameter Name
     - Required
     - Description
     - Default Value
   * - test-tracer-run-reference
     - No
     - By default, Test Tracer Runs are grouped one per Pytest run. If you want multiple Pytest runs to be visible in the same Test Tracer Run, you can specify your own unique run reference. Useful if you split up your test runs into several parallel runs
     - A GUID
   * - use-test-tracer
     - No
     - Provide this argument to enable the Test Tracer plugin
     - False
   * - build-version
     - No
     - If your application under test has a build version. You can enter it here.
     - None
   * - build-revision
     - Yes
     - A unique revision for your application under test. Typically this is a git commit hash, an SVN revision, or any other string that identifies the current code base
     - None
   * - test-tracer-project-name
     - Yes
     - The name of the Project that this test is for. You can give it the name of your application, a single microservice, or any other way that you choose to describe the thing being tested.
     - None
   * - branch-name
     - Yes
     - The name of the branch that is being tested
     - None
   * - test-tracer-no-upload
     - No
     - If you provide this argument, Test Tracer will still generate test result data, but it won't attempt to upload it to Test Tracer
     - False
   * - test-tracer-upload-token
     - No
     - If you want to upload results to Test Tracer, you need to specify the API token used to secure the upload
     - None

Here is an example of using the Test Tracer for Pytest plugin with Git as the source control::

$ pytest --branch-name=$(git rev-parse --abbrev-ref HEAD) --build-revision=$(git rev-parse --short HEAD) --test-tracer-project-name="Your Project Name" --test-tracer-upload-token="Your Test Tracer Upload Token"

License
-------

Distributed under the terms of the `MIT`_ license, "pytest-test-tracer-for-pytest" is free and open source software


Issues
------

If you encounter any problems, please `file an issue`_ along with a detailed description.

.. _`MIT`: https://opensource.org/licenses/MIT
.. _`BSD-3`: https://opensource.org/licenses/BSD-3-Clause
.. _`GNU GPL v3.0`: https://www.gnu.org/licenses/gpl-3.0.txt
.. _`Apache Software License 2.0`: https://www.apache.org/licenses/LICENSE-2.0
.. _`cookiecutter-pytest-plugin`: https://github.com/pytest-dev/cookiecutter-pytest-plugin
.. _`file an issue`: https://github.com/testreporter/test-tracer-for-pytest/issues
.. _`pytest`: https://github.com/pytest-dev/pytest
.. _`tox`: https://tox.readthedocs.io/en/latest/
.. _`pip`: https://pypi.org/project/pip/
.. _`PyPI`: https://pypi.org/project
.. _`Test Tracer`: https://testtracer.io
.. _`Pytest BDD`: https://pypi.org/project/pytest-bdd/
