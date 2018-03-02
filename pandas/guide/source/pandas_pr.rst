.. _pandas_pr:

=======================
Submitting your changes
=======================

Once you finished the changes to your assigned docstring, you can follow the
instructions in this document in order to get your changes merged into pandas,
and released in the next version.

1. Validate that your docstring does not have technical errors
--------------------------------------------------------------

There is a script in pandas that validates whether a docstring follows the
technical parts of the pandas docstring convention. To run the script,
execute in your terminal:

    | ``cd <pandas-dir>``
    | ``scripts/validate_docstrings.py <your-function-or-method>``

where `<your-function-or-method>` is for example `pandas.DataFrame.head`,
`pandas.Series.tail` or `pandas.to_datetime`.

2. Visual validation of the docstring
-------------------------------------

The previous sprint validates things like the names of the sections, or
that there are dots, spaces, or blank lines in the right side. But does
not validate for typos, unclear sentences, or other mistakes. To validate
them, as well as the visualization of your docstring in the pandas website
you need to generate the html version of the page you worked on.

To build the documentation run:

    | ``cd <pandas-dir>/doc``
    | ``python make.py html --single <your-function-or-method>``

where `<your-function-or-method>` follows the format described in the previous
section.

This will generate a file `<pandas-dir>/doc/build/html/generated/<your-function-or-method>.html`
that can be opened with your web browser.

3. Validate that the docstring is clear to others
-------------------------------------------------

As the last validation, please show the html version of your docstring to a
person in the sprint not involved in the changes to the docstring, and make
sure they are able to fully understand it.

4. Commit your changes
----------------------

Once all the validations are successful, you can proceed to commit the changes
into git.

Before committing your changes, make sure you are in the branch of the feature
you are going to commit with:

    | ``git branch``

Then, follow the next steps:

    | ``git fetch upstream``
    | ``git merge upstream/master``
    | ``git add <modified-file(s)>``
    | ``git commit -m "<commit-message>"``

where `<modified-file(s)>` is the file where you made your changes (in rare
cases it could be more than one file). And `<commit-message>` is a short
description of your changes, starting by "DOC:" (e.g. "DOC: Improved the
docsting of DataFrame.head()").

5. Push your changes to the sprint repository
---------------------------------------------

Before sending the pull request to the pandas core developers, you will send
it to the sprint repository. Where more experienced contributors will review
it, and suggest changes if needed.

First, push your changes to your GitHub fork:

    | ``git push -u origin <your-branch-name>``

Then, visit https://github.com/python-sprints/pandas in your browser, and click
on the "Compare & pull request" button in the yellow box above the repository
files.

Once your changes are reviewed and approved, you will receive an email on how
to send the final pull request to pandas.
