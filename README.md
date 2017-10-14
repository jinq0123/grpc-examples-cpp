# grpc-examples-cpp
Build grpc cpp examples with conan and premake.

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
The default setting may be Release_x64 which can be seen in the generated conaninfo.txt.
You can add settings in `conan install` like:
```
conan install . --build missing -s build_type=Debug -s arch=x86_64 -s compiler.runtime=MDd
```

Visual Studio has multiple configurations like Release_x64 and Debug_x32,
 but the generated sln must be used only for the configuration
 which is set in `conan install`.

## Run
```
vs2015\bin\x64\Release\greeter_async_client.exe  
vs2015\bin\x64\Release\greeter_async_client2.exe 
vs2015\bin\x64\Release\greeter_async_server.exe  
vs2015\bin\x64\Release\greeter_client.exe        
vs2015\bin\x64\Release\greeter_server.exe        
```
```
vs2015\bin\x64\Release\route_guide_client.exe --db_path=route_guide/route_guide_db.json
vs2015\bin\x64\Release\route_guide_server.exe --db_path=route_guide/route_guide_db.json   
``` 
