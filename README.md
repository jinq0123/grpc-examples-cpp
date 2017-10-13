# grpc-examples-cpp
Fork of grpc cpp examples and build with conan.

## Build

1. Install [conan](http://docs.conan.io/en/latest/installation.html).
1. `conan remote add remote_bintray_jinq0123 https://api.bintray.com/conan/jinq0123/test`
1. `conan install . --build missing` to install required dependencies.
	* generates conanpremake.lua which is required by premake5.lua
	* generates conaninfo.txt
1. Premake
	* `premake5.exe --os=windows vs2015` to generate VS2015 sln.
	* `premake5.exe --os=linux gmake` to generate Makefile.

### Change settings
The default setting may be release_x64 which can see in the generated conaninfo.txt.
You can add settings in `conan install` like:
```
conan install . --build missing -s build_type=Debug -s arch=x86_64 -s compiler.runtime=MDd
```

