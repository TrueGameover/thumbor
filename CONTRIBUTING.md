So you want to contribute with thumbor? Awesome! Welcome aboard!

## Steps

There are a few things you'll need in order to properly start hacking on
it.

1. Fork and clone
2. Install dependencies and initialize environment
3. Hack, in no particular order:
   - Write enough code
   - Write tests for that code
   - Check that other tests pass
   - Repeat until you're satisfied
4. Submit a pull request

## Fork and Clone

First step is to [fork it](http://help.github.com/fork-a-repo/) and
create your own clone of thumbor.

## Install Dependencies

We seriously advise you to use
[virtualenv](http://pypi.python.org/pypi/virtualenv) since it will keep
your environment clean of thumbor's dependencies and you can choose when
to "turn them on".

You'll also need python \>= 3.7 and [python
poetry](https://python-poetry.org/).

Installing poetry should be as easy as `pip install poetry`, but you can
find more about it in their website.

Other than that, you'll also need `<span class="title-ref">redis-server
\<https://redis.io\></span>\` installed (for queued detector unit
tests).

## Initializing the Environment

Once you've created your virtualenv, and installed poetry, make sure you
can use poetry:

    $ poetry --version
    Poetry version 1.0.3

You should see something similar. After that we just need to download
all python packages with:

    $ make setup

## Running the Tests

Running the tests is as easy as:

    $ make test

You should see the results of running your tests after an instant.

If you are experiencing "Too many open files" errors while running the
tests, try increasing the number of open files per process, by running
this command:

    $ ulimit -S -n 2048

Read
<http://superuser.com/questions/433746/is-there-a-fix-for-the-too-many-open-files-in-system-error-on-os-x-10-7-1>
for more info on this.

## Linting your code

Please ensure that your editor is configured to use
[black](https://github.com/psf/black),
[flake8](https://flake8.pycqa.org/en/latest/) and
[pylint](https://www.pylint.org/).

Even if that's the case, don't forget to run `make flake pylint` before
commiting and fixing any issues you find. That way you won't get a
request for doing so in your PR.

## Pull Requests

After hacking and testing your contribution, it is time to make a pull
request. Make sure that your code is already integrated with the master
branch of thumbor before asking for a pull request.

To add thumbor as a valid remote for your repository:

    $ git remote add thumbor git://github.com/thumbor/thumbor.git

To merge thumbor's master with your fork:

    $ git pull thumbor master

If there was anything to merge, just run your tests again. If they pass,
[send a pull request](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).

The latest version of this document can be found at [Hacking on thumbor](https://thumbor.readthedocs.io/en/latest/hacking_on_thumbor.html).
