# SELMA Use Case 0 (UC0) Source Code: 
## Build from macOS for macOS and cross-compile for Linux from macOS

<B>Online demo</B> version of SELMA UC0 is available at: https://selma.ailab.lv

<B>How to use</B> video is available at: https://youtu.be/r4nsumsnR5M

<B>The project</B> page is available at: https://selma-project.eu/

<B>Precompiled version</B> ready for installation is available from separate repository: https://github.com/SELMA-project/UC0-OpenSource

## Downloading the UC0 Source Code 

<B>Download All Parts</B> of the split archive to the same directory from the Release https://github.com/SELMA-project/UC0-Build/releases/tag/v1.0.0

<B>Reassemble the Archive</B> using the cat command:

```
cat UC0source.tgz.part* > UC0source.tgz
```

<B>Decompress the Reassembled Archive</B> with tar:
```
tar -xzvf UC0source.tgz
```

## Dependency

Install [homebrew](https://brew.sh/)

```
brew install FiloSottile/musl-cross/musl-cross
```

## OpenBLAS

```
cd openblas && ./build.sh
```

## CTranslate2

```
cd translate/engine && target_os=Linux ./build.sh
cd translate/engine && target_os=Darwin ./build.sh
cd translate && target_os=Linux ./build.sh
cd translate && target_os=Darwin ./build.sh
```

## libtorch

Patched pytorch is already precompiled.

## whisper.cpp

```
target_os=Linux ./build-whisper-lib.sh
target_os=Darwin ./build-whisper-lib.sh
```

## Final App

```
./build-linux-x86_64.sh
./build-darwin.sh
```

## Run

Copy models to `models` directory.

```
./uc0-darwin
```
or
```
./uc0-linux-x86_64
```

Open in browser `http://localhost:9090`


