## MoonLibs - Graphics and Audio Lua Libraries

A collection of libraries for graphics, audio, and heterogeneous programming in [Lua](https://www.lua.org) (>= 5.3), mostly bindings to popular C/C++ libraries.

They currently run 
[on GNU/Linux](#installing-on-gnulinux) and (most of them) [on Windows](#installing-on-windows) with MSYS2/MinGW-w64.

The libraries do not depend on each other, so they can be selectively installed.

_Author:_ _[Stefano Trettel](https://www.linkedin.com/in/stetre)_

[![Lua logo](./powered-by-lua.gif)](https://www.lua.org/)

----

#### Reference Manuals

| Rendering | Windowing | Math | Image | Model | Text | Audio |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
[MoonGL](https://stetre.github.io/moongl/doc/index.html) |  [MoonGLFW](https://stetre.github.io/moonglfw/doc/index.html) | [MoonGLMATH](https://stetre.github.io/moonglmath/doc/index.html) | [MoonImage](https://stetre.github.io/moonimage/doc/index.html) | [MoonAssimp](https://stetre.github.io/moonassimp/doc/index.html) | [MoonFreeType](https://stetre.github.io/moonfreetype/doc/index.html) | [MoonSndFile](https://stetre.github.io/moonsndfile/doc/index.html) |
[MoonCL](https://stetre.github.io/mooncl/doc/index.html) | [MoonNuklear](https://stetre.github.io/moonnuklear/doc/index.html) | | [(_MoonSOIL_)](https://stetre.github.io/moonsoil/doc/index.html) | | [MoonFonts](https://stetre.github.io/moonfonts/doc/index.html) | [MoonAL](https://stetre.github.io/moonal/doc/index.html) |
[MoonVulkan](https://stetre.github.io/moonvulkan/doc/index.html) | [MoonFLTK](https://stetre.github.io/moonfltk/doc/index.html) | | | | | [LuaJACK](https://stetre.github.io/luajack/doc/index.html) |
| | [(_MoonGLUT_)](https://stetre.github.io/moonglut/doc/index.html) | | | | | |

----

### Contents

* [The collection](#the-collection)
* [Installation instructions](#installation-instructions)
  * [Installing on GNU/Linux](#installing-on-gnulinux)
  * [Installing on Windows](#installing-on-windows)
* [Dependencies](#dependencies)
* [Examples](#examples)

---

### The collection

Below is the list of libraries currently contained in the MoonLibs collection,
with links to their repositories where the code and more details can be found.

* **Rendering and computing:**
  * [**MoonGL**](https://github.com/stetre/moongl) - bindings to **OpenGL 3.x - 4.x**.
  * [**MoonCL**](https://github.com/stetre/mooncl) - bindings to **OpenCL**.
  * [**MoonVulkan**](https://github.com/stetre/moonvulkan) - bindings to **Vulkan**.
* **Windowing, input handling, GUI:**
  * [**MoonGLFW**](https://github.com/stetre/moonglfw) - bindings to **GLFW**.
  * [**MoonFLTK**](https://github.com/stetre/moonfltk) - bindings to the **Fast Light Toolkit (FLTK)**.
  * [**MoonNuklear**](https://github.com/stetre/moonnuklear) - bindings to **Nuklear**.
  * _[MoonGLUT](https://github.com/stetre/moonglut) (deprecated) - bindings to **FreeGLUT**_.
* **Math:**
  * [**MoonGLMATH**](https://github.com/stetre/moonglmath) - **graphics math library** for MoonGL and MoonVulkan.
* **Image loading:**
  * [**MoonImage**](https://github.com/stetre/moonimage) - **STB image** based image loading library.
  * _[MoonSOIL](https://github.com/stetre/moonsoil) (deprecated) - bindings to the **Simple OpenGL Image Library**_.
* **Model loading:**
  * [**MoonAssimp**](https://github.com/stetre/moonassimp) - bindings to the **Open Asset Import Library (Assimp)**.
* **Text rendering:**
  * [**MoonFreeType**](https://github.com/stetre/moonfreetype) - bindings to the **FreeType** font rendering library.
  * [**MoonFonts**](https://github.com/stetre/moonfonts) - bitmap fonts, bindings to **STB fonts**.
* **Audio:**
  * [**MoonSndFile**](https://github.com/stetre/moonsndfile) - bindings to **libsndfile**.
  * [**MoonAL**](https://github.com/stetre/moonal) - bindings to **OpenAL**.
  * [**LuaJACK**](https://github.com/stetre/luajack) - bindings to the **JACK Audio Connection Kit**.

---

### Installation instructions

**TLDR** - Provided you have already installed the toolchain ([GNU/Linux](#installing-on-gnulinux), [Windows](#installing-on-windows)) and the needed [dependencies](#dependencies), to install a library of the collection
all you have to do is clone it, enter its base directory, compile and install. E.g. for MoonFLTK:

```bash
$ git clone https://github.com/stetre/moonfltk
$ cd moonfltk
moonfltk$ make
moonfltk$ make install # or: $ sudo make install
```

To uninstall it:

```bash
moonfltk$ make uninstall # or: $ sudo make uninstall
```

---

#### Installing on GNU/Linux

The following instructions show how to install the libraries on Ubuntu.
To install on a GNU/Linux distribution other than Ubuntu, replace `apt` with the package manager used by
the distribution (the names of the packages may also differ).

##### Install the toolchain and Lua

Install the following packages (if you don't have them already):

```bash
$ sudo apt install make
$ sudo apt install binutils
$ sudo apt install gcc
$ sudo apt install git
```

Install the [latest version](https://www.lua.org/download.html) of Lua:

```bash
$ sudo apt install libreadline-dev
$ wget https://www.lua.org/ftp/lua-5.3.4.tar.gz
$ tar -zxpvf lua-5.3.4.tar.gz
$ cd lua-5.3.4
lua-5.3.4$ make linux
lua-5.3.4$ sudo make install
```

##### Install a library

The following instructions show how to install MoonFLTK, but the same procedure applies to any other any other library of the collection.

First, install any [dependencies](#dependencies) needed by the library. MoonFLTK needs FLTK, which you can install by typing:

```bash
$ sudo apt install libfltk1.3-dev
```

Then clone the library (or, if you prefer, download the latest release tarball and decompress, it),
enter its base directory, compile, and install:

```bash
$ git clone https://github.com/stetre/moonfltk
$ cd moonfltk
moonfltk$ make
moonfltk$ sudo make install
```

To uninstall the library:

```bash
moonfltk$ sudo make uninstall
```


---

#### Installing on Windows

The following instructions show how to install the libraries on Windows with MSYS2/MinGW-w64.

##### Install MSYS2/MinGW-w64

Download the [MSYS2 installer](https://msys2.github.io/) and
follow the instructions from the download page.

##### Install the toolchain and Lua

In the following, we'll assume that you installed MSYS2 in the default location `C:\msys32`. If not, change the paths below accordingly to your chosen location.

Open a MinGW shell (using the shell launcher `C:\msys32\mingw32.exe` or `mingw64.exe`, depending on your architecture), and install the following packages:

```bash
$ pacman -S make
$ pacman -S tar
$ pacman -S git
$ pacman -S ${MINGW_PACKAGE_PREFIX}-gcc
$ pacman -S ${MINGW_PACKAGE_PREFIX}-lua
```

Append one of the following two paths, depending on your architecture, to the PATH environment variable:
- `C:\msys32\mingw32\bin`   (corresponding to `/mingw32/bin` under MSYS2, for 32-bit), or
- `C:\msys32\mingw64\bin`   (corresponding to `/mingw64/bin` under MSYS2, for 64-bit).

(To do so, right click `Computer->Properties->Advanced System Settings->Environment variables`,
then search for the `PATH` or `Path` system variable, edit it, and append a semicolon (`;`) followed by the path).

Now your environment is ready and you should be able to execute the Lua interpreter from the Windows command prompt, by just typing `lua` in it (to exit from the interpreter, type `os.exit()` or `Ctrl-C` in it).

##### Install a library

The following instructions show how to install MoonFLTK, but the same procedure applies to any other any other library of the collection, provided it is supported on Windows.

First, open a MinGW shell and from there install any [dependencies](#dependencies) needed by the library. MoonFLTK needs FLTK, which you can install by typing:

```bash
$ pacman -S ${MINGW_PACKAGE_PREFIX}-fltk
```

Then clone the library (or, if you prefer, download the latest release tarball and decompress, it),
enter its base directory, compile, and install:

```bash
$ git clone https://github.com/stetre/moonfltk
$ cd moonfltk
moonfltk$ make
moonfltk$ make install
```

To uninstall the library:

```bash
moonfltk$ make uninstall
```
---

### Dependencies

The same procedures shown above for MoonFLTK apply to any other library of the collection,
and differ only in the dependencies (if any, other than Lua and the C standard libraries) that need
to be installed.

The dependencies needed by the different libraries are listed below.

GNU/Linux (Ubuntu):

```bash
$ sudo apt install libfltk1.3-dev     # needed only by MoonFLTK
$ sudo apt install libglfw3-dev       # needed only by MoonGLFW
$ sudo apt install freeglut3-dev      # needed only by MoonGLUT
$ sudo apt install libglew-dev        # needed only by MoonGL
$ sudo apt install libassimp-dev      # needed only by MoonAssimp
$ sudo apt install libfreetype6-dev   # needed only by MoonFreeType
$ sudo apt install libsndfile1-dev    # needed only by MoonSndFile
$ sudo apt install libopenal-dev      # needed only by MoonAL
$ sudo apt install libjack-jackd2-dev # needed only by LuaJack
```

Windows (MSYS2/MinGW-w64):

```bash
$ pacman -S ${MINGW_PACKAGE_PREFIX}-fltk        # needed only by MoonFLTK
$ pacman -S ${MINGW_PACKAGE_PREFIX}-glfw        # needed only by MoonGLFW
$ pacman -S ${MINGW_PACKAGE_PREFIX}-freeglut    # needed only by MoonGLUT
$ pacman -S ${MINGW_PACKAGE_PREFIX}-glew        # needed only by MoonGL
$ pacman -S ${MINGW_PACKAGE_PREFIX}-assimp      # needed only by MoonAssimp
$ pacman -S ${MINGW_PACKAGE_PREFIX}-freetype    # needed only by MoonFreeType
$ pacman -S ${MINGW_PACKAGE_PREFIX}-libsndfile  # needed only by MoonSndFile
$ pacman -S ${MINGW_PACKAGE_PREFIX}-openal      # needed only by MoonAL
```

---

### Examples

Each library comes with a few examples, which are located in the `example/` directory of the
source package (or in its subdirectories).

Other examples, typically using more than one library, can be found in the `example/` directory
of this repository.

The examples are Lua scripts that can be executed with the standard Lua interpreter.

#### Running the examples

On **GNU/Linux**, the examples can be executed from the command line. To run, say, the `fltk/valuators.lua` example, assuming the MoonFLTK source package is located in `/home/ste/moonfltk`:

```bash
$ cd /home/ste/moonfltk/examples/fltk
fltk$ lua valuators.lua
```

On **Windows**, the examples can be executed either in a MinGW shell or from a Windows command prompt.

Let's assume the MoonFLTK source package is located in `/home/ste/moonfltk` under MSYS2, which corresponds to the `C:\msys32\home\ste\moonfltk` folder under Windows.

To run, say, the `fltk/valuators.lua` example in a MinGW shell:

```bash
$ cd /home/ste/moonfltk/examples/fltk
fltk$ lua valuators.lua
```

To run the same example from a Windows command prompt:

```dos
C:\> cd \msys32\home\ste\moonfltk\examples\fltk
C:\msys32\home\ste\moonfltk\examples\fltk> lua valuators.lua
```

