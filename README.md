# llnode

Node.js v4.0.0-v5.0.0 C++ plugin for LLDB (work in progress).

## Demo

https://asciinema.org/a/29589

## Build instructions

### OS X

```bash
# Check out source code of the LLDB that is compatible with OS X's default
# lldb
svn co http://llvm.org/svn/llvm-project/lldb/tags/RELEASE_34/final/ lldb

# Initialize GYP
git clone https://chromium.googlesource.com/external/gyp.git tools/gyp

# Configure
./gyp_lldb

# Build
make -C out/ -j9

# Install
make install-osx
```

### Linux

```bash
# Install lldb and headers
sudo apt-get install lldb-3.6 lldb-3.6-dev

# Initialize GYP
git clone https://chromium.googlesource.com/external/gyp.git tools/gyp

# Configure
./gyp_llnode -Dlldb_dir=/usr/lib/llvm-3.6/ -Dlldb_lib=lldb-3.6

# Build
make -C out/ -j9

# Install
sudo make install-linux
```

### Usage

```
lldb
(lldb) help v8
The following subcommands are supported:

      bt       -- Show a backtrace with node.js JavaScript functions and their
                  args. An optional argument is accepted; if that argument is a
                  number, it specifies the number of frames to display. Otherwise
                  all frames will be dumped.

                  Syntax: v8 bt [number]
      code-map -- Print code map of all compiled functions.

                  Syntax: v8 code-map
      inspect  -- Print detailed description and contents of the JavaScript
                  value.

                  Syntax: v8 inspect expr
      print    -- Print short description of the JavaScript value.

                  Syntax: v8 print expr

For more help on any particular subcommand, type 'help <command> <subcommand>'.
```


## LICENSE

This software is licensed under the MIT License.

Copyright Fedor Indutny, 2015.

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to permit
persons to whom the Software is furnished to do so, subject to the
following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN
NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM,
DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR
OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE
USE OR OTHER DEALINGS IN THE SOFTWARE.
