![https://ci.appveyor.com/api/projects/status/github/wheeler-microfluidics/git_helpers?branch=master&svg=true](https://ci.appveyor.com/api/projects/status/github/wheeler-microfluidics/git_helpers?branch=master&svg=true)
# `git_helpers` #

Wrapper API around `git` command-line utilities.

__NB__ `git` must be installed and available on the executable search path.


## Example usage ##

Create an instance of the `Git` class, and use methods to run `git` commands.

    >>> from git_helpers import Git
    >>> g = Git()
    >>> g.root_path
    path('.')
    >>> g = Git('.')
    >>> g.root_path
    path('.')
    >>> g.rev_parse()
    'e3efb58eac464355f4ffbc5dc2774c0b95ddcd1c'
    >>> g.describe()
    'v0.1'
    >>> g.summary()
    '* e3efb58 - Initial commit of git_helpers (6 minutes ago)'
    >>> g.branch()
    'master'

Run arbitrary commands by passing a list of string arguments to the `command`
method.

    >>> g.command(['rev-parse', 'HEAD'])
    'e3efb58eac464355f4ffbc5dc2774c0b95ddcd1c'
