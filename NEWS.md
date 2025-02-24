## Release 0.23 (12-Aug-2022)

This release adds support for Setuptools' PEP-660 editable installations,
drops support for Python 3.6, and supports startlingly old git versions.

With thanks to Biastian Zim, Michał Górny, Igor S. Gerasimov, Christian Clauss,
Anderson Bravalheri and Simão Afonso for contributions.

* FIX: Adequate custom `build_py` command to changes in setuptools v64 by @abravalheri in (313)
* FIX: skip version update on `build_ext` if .py does not exist by @mgorny in (297)
* FIX: old GIT (<1.7.2) does not know about `--count` flag by @foxtran in (306)
* FIX: Use only numeric versions in Git, ignore other tags with the same prefix by @effigies in (256)
* FIX: Handle missing `tag_prefix` gracefully by @effigies in (308)
* FIX: Restore `py_modules` field to setup.py by @effigies in (293)
* ENH: Patch versioneer files into manifest at runtime by @effigies in (309)
* STY: Undefined name: VersioneerBadRootError on line 51 by @cclauss in (305)
* STY: Appease flake8 by @simaoafonso-pwt in (312)
* MNT: Drop 3.6 support, remove old hacks by @effigies in (288)
* MNT: Clarify license as CC0-1.0 by @BastianZim in (292)
* MNT: Drop distutils by @effigies in (289)
* MNT: Disable editable installs of versioneer (they will not work) by @effigies in (307)
* CI: Update gh-actions PLATFORM variable to avoid double-testing by @effigies in (311)

## Release 0.22 (07-Mar-2022)

This release fixes failures in Windows related to different handling of
asterisk characters depending on the shell and the presence of a prefix.

This release explicitly has been tested on Python 3.10 and is the final
release that will support Python 3.6 or distutils.

With thanks to John Wodder, Mathijs van der Vlies and Christian Schulze for
their contributions.

* FIX: Unset `GIT_DIR` environment variable while retrieving version information from git (#280)
* FIX: Hide console window if pythonw.exe is used (#285)
* FIX: Broken tag prefix on Windows and add CI (#283)
* FIX: Default to setuptools, only falling back to distutils (#276)
* TEST: Verify and note Python 3.10 support (#272)
* MNT: Run CI weekly to catch upstream deprecations quickly (#281)

## Release 0.21 (13-Oct-2021)

With thanks to Dimitri Papadopoulos Orfanos, Andrew Tolmie, Michael Niklas,
Mike Taves, Ryan Mast, and Yaroslav Halchenko for contributions.

* FIX: Escape asterisk in `git describe` call on Windows (#262)
* ENH: Add some type annotations to play nicely with mypy (#269)
* ENH: Respect tags with `.postN` in pep440-pre style (#261)
* TEST: Subproject installations fixed in Pip 21.3, remove expected failure marks (#271)
* STY: Fix typos (#260 and #266)
* STY: Centralize pylint hints in header (#270)
* MNT: Use `os.path` and `pathlib` consistently (#267)

## Release 0.20 (13-Jul-2021)

With thanks to Tanvi Moharir, Ashutosh Varma, Benjamin Rüth, Lucas Jansen,
Timothy Lusk and Barret O'Brock for contributions.

* Respect `versionfile_source` in `__init__.py` snippet (#241)
* Add `pep440-branch` and `pep440-post-branch` styles (#164)
* Stop testing deprecated `easy_install`, support left in for now (#237)
* Use `versionfile_build` instead of `versionfile_source` where needed (#242)
* Improve handling of refname edge cases (#229)
* Clarify installation in docs (#235)
* Play nicely with custom `build_ext`s (#232)

## Release 0.19 (10-Nov-2020)

Versioneer's 0.19 release is the first under new maintainership, and most of the work
done has been maintenance along with a few features and bug fixes. No significant
changes to the mode of operation have been included here.

The current maintainers are Nathan Buckner, Yaroslav Halchenko, Chris Markiewicz,
Kevin Sheppard and Brian Warner.

* Drop support for Python < 3.6, test up to Python 3.9
* Strip GPG signature information from date (#222)
* Add `bdist_ext` cmdclass, to support native code extensions (#171)
* Canonicalize pep440-pre style (#163)
* Take arguments to `get_cmdclass`

## Release 0.18 (01-Jan-2017)

* switch to entrypoints to get the right executable suffix on windows (#131)
* update whitespace to appease latest flake8

Thanks to xoviat for the windows patch.
