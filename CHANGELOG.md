# Change Log
All notable changes to this project will be documented in this file.
This project adheres to [Semantic Versioning](http://semver.org/) and
and [human-readable changelog](http://keepachangelog.com/).

## [1.0.0b1] - 2016-09-08
First pypi.org release.

### Added
 - Basic test suite
 - Docstrings
 - Sphinx based documentation
 - `.paramDict` provides natural-language translation of three-letter parameter
   codes. Not inclusive of all possible codes.

### Changed
 - `.getOpusData` now takes a tuple(DataBlockType, Dimensions, Derivative) as
   the second argument.
 - `.listContents` returns a list of datablock tuples
 - 3D TRC data is now return as a 3D numpy array under `.traces` with the structure
   `.traces[row][column][trace]` where trace corresponds to the `.labels` index
   of the trace. Individual trace maps can be accessed as `.traces[:,:,trace]`

### Fixed
 - Properly terminate parameter strings

## [1.0.0a3] - 2016-08-15
The "I heard you like parameters" release
### Added
 - This change log (CHANGELOG.md)
 - `.parameters` now returns Acquisition, Instrument, Sample and FT parameters
   in addition to the existing Data parameters

### Changed
 - Parameters are now returned in `.parameters` instead of `.paramList`
 - Support editable enumerated string parameter type

### Fixed
 - `.parameters`/`.paramList` strings are now unicode literals

## [1.0.0a1] - 2016-05-10
Released to limited audience as win32-py3.4 and linux64-py3.4 binary wheels.
### Added
 - Python 3 support:
  - all binary literals are `bytes`
  - cython reads source .pyx file in language_level=3
 - test.py tests 3D example file
 - profile.py profiles using onion map2.0 file

### Changed
 - Python 2 has been futurized to maintain a single 2/3 codebase
 - `_readFloats` replaced with numpy.fromfile
 - Add metadata to `setup.py`

### Deprecated
 - Python 2 support will likely be ignored in the future (No Python 2 consumers)
