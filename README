Conan Workspace setup for local development

# Installation
git clone https://github.com/traact/traact_workspace.git
cd traact_workspace
git submodule init
git submodule update
git submodule foreach git checkout master
# create build directory (e.g. for debug: cmake-build-debug, release: cmake-build-release )
mkdir cmake-build-debug
cd cmake-build-debug
# build workspace (using a matching profile e.g. debug/release)

# use --profile=my_profile to specify the conan profile to use
# Linux
conan workspace install ../conanws_gcc.yml -o cuda_dev_config:cuda_version=10.0 -o traact_kinect_azure:with_bodytracking=True -o opencv:with_gtk=True --build "*"
# Windows
conan workspace install ../conanws_vs.yml -o cuda_dev_config:cuda_version=10.2 -o traact_kinect_azure:with_bodytracking=True -o opencv:with_gtk=True --build "*"

# Generate project files, use your compiler
# Linux, should work, need to specify build type
cmake .. -DCMAKE_BUILD_TYPE=Debug
# Windows
cmake .. -G "Visual Studio 15 2017 Win64"

# Requirements Windows
Visual Studio 2015/2017 (2019 does not work because boost does not support 2019 yet)
Windows SDK-Version 10.0.17134.0


%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"

