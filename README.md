# Code editor component for PyQt5

Component has been created for [Enki editor](http://enki-editor.org) as replacement for [QScintilla](http://www.riverbankcomputing.com/software/qscintilla/intro)

[API documentation](https://qutepart.readthedocs.org/en/latest/)

## Features
* Syntax highlighting for 196 languages
* Smart indentation for many languages
* Line numbers
* Bookmarks
* Advanced edit operations
* Matching braces highlighting
* Autocompletion based on document content
* Marking too long lines with red line
* Rectangular selection and copy-paste
* Vim mode

## Building and installation on Linux

Qutepart depends on:

* Python 3
* PyQt5
* pcre

_Versions up to `2.2.3` used to work on Python 2 and PyQt4._

#### 1. Install [pcre](http://www.pcre.org/) and development files
On Debian, Ubuntu and other Linuxes install package `libpcreX-dev`, where `X` is available in your distribution pcre version.
For other OSes - see instructions on pcre website

#### 2. Install Python development files
On Debian, Ubuntu and other Linuxes install package `python3-dev`, on other systems - see Python website

#### 3. Install C compiler
It will probably be gcc

#### 4. Build and install the package
`python setup.py install`

## Building and installation on Windows

* Download and install the [CMake binary](http://www.cmake.org/). Tested with 2.8.12.
* Download and install Microsoft Visual Studio Express Edition 2010 (or the full version).
* Create a root directory and place the following as subdirectories in it:
    - Download the [pcre source](http://www.pcre.org/). Tested with v. 8.37.
    - Download the latest Qutepart [release](https://github.com/hlamer/qutepart/releases).

#### Make pcre
    cd <pcre-8.37 source>
    mkdir build
    cd build
    cmake .. -DBUILD_SHARED_LIBS:BOOL=OFF -DPCRE_SUPPORT_UTF:BOOL=ON -DPCRE_SUPPORT_JIT:BOOL=ON -G "Visual Studio 10 2010"
    cmake --build . --config Release

#### Build/install Python modules
    cd qutepart
    python setup.py install --include-dir=../pcre-8.37/build --lib-dir=../pcre-8.37/build/Release

## Qutepart and Katepart
[Kate](http://kate-editor.org/) and Katepart (an editor component) is really cool software. The Kate authors and community have created, probably, the biggest set of highlighters and indenters for programming languages.

* Qutepart uses Kate syntax highlighters (XML files)
* Qutepart contains a port from Javascript to Python of Kate indenters (12% of the code base in version 1.0.0)
* Qutepart doesn't contain Katepart code.

Nothing is wrong with Katepart. Qutepart has been created to enable reusing highlighters and indenters in projects where a KDE dependency is not acceptable.


## Author
Andrei Kopats
[hlamer@tut.by](mailto:hlamer@tut.by)


## Bug reports, patches
[Github page](https://github.com/hlamer/qutepart)

## License
LGPL v2
