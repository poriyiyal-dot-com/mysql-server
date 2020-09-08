# 1. Install CMake

### 1. Download the DMG from CMake
### 2. Install the cmake application

You can open then cmake GUI.

Still CMAKE is not availablein shell.

### 3. Create Symlinks for CMAKE

1. Open CMake
2. Tools > How to install for Command Line Use
3. Follow the steps in the dialog box

```bash
sudo "/Applications/CMake.app/Contents/bin/cmake-gui" --install
```

# 2. Run CMake

```
# From mysql source folder

mkdir bld
cd bld

cmake ..

```

#### Resulted in error - Unable to find boost

```
mkdir boost 

cmake .. -DDOWNLOAD_BOOST=1 -DWITH_BOOST=boost
```

##### Error

```
CMake Error at cmake/ssl.cmake:63 (MESSAGE):
  Please install the appropriate openssl developer package.

Call Stack (most recent call first):
  cmake/ssl.cmake:280 (FATAL_SSL_NOT_FOUND_ERROR)
  CMakeLists.txt:580 (MYSQL_CHECK_SSL)
```

#### 

```
brew install openssl
cmake .. -DDOWNLOAD_BOOST=1 -DWITH_BOOST=boost 
```