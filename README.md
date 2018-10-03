# Asio C++ Library

Asio is a C++ library for network and low-level I/O programming used by the
[Platform](https://github.com/PaladinAI/ddat-platform).

# Syncing with the upstream master branch

First, make sure the `upstream` remote is configured:

    git remote -v

    # If the upstream remote doesn't exist, add it:
    git remote add upstream https://github.com/chriskohlhoff/asio.git

Then merge the upstream changes from the `master` branch:

    git fetch upstream
    git checkout develop
    git merge upstream/master

# Publishing to the Conan server

Until the [Platform](https://github.com/PaladinAI/ddat-platform) library is
updated, we're using Asio version 1.11. Make sure to checkout that branch before
making any changes. To update the package, update the version number in
`conanfile.py` then run:

    git checkout asio-1-11-0
    conan create . paladin/develop
    conan upload asio/1.11.0@paladin/develop -r paladin
