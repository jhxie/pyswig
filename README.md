# Cmake SWIG Python Extension
## Overview
Just a simple example I have written for demonstrating how to use swig in
cmake.

## Build Instructions
After installing needed dependencies, issuing:
```bash
mkdir build
cmake -Bbuild -H.
make -C build
sudo make -C build install
python3 << EOF
import example
example.beep()
EOF
```
The generated *example* python module only works for python3.

## License
Copyright &copy; 2016 Jiahui Xie  
Licensed under the [GNU General Public License v3][GPL3].  
Distributed under the [GNU General Public License v3][GPL3].

[GPL3]: https://opensource.org/licenses/GPL-3.0
