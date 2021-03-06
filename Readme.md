# JNI(Java Native Interface) Template

### Environmental dependencies

- This project **Just support JDK 8.**
- [Cmake](https://cmake.org/download/)
- [Make](https://www.gnu.org/software/make/)

# Hello JNI !

Build **demo** and run it with:

```shell script
./build.sh
./build/bin/run.sh
```

# Customize JNI

## Unix-like

#### 1. Create ``JNI`` file in ``$PEOJECT_HOME/src/java`` of this project. ( [Demo](https://github.com/JoverZhang/JNI-example/blob/master/src/java/com/ttmo/HelloJNI.java) ）

#### 2. Generate ``header-file`` of ``JNI``.

```shell script
cd src

# PS: Must in 'src' directory run with:
./generate.sh ./java/com/ttmo/DemoLib.java
```

#### 3. Add to ``$PROJECT_HOME/src/CMakeLists.txt`` ( [Demo](https://github.com/JoverZhang/JNI-example/blob/master/src/CMakeLists.txt) )

```cmake
add_library(
  {LIBRARY_NAME} SHARED
  {xxx.h} {xxx.cc}
  ...{.h/.c}
)
```

#### 4. Implement interface. ( [Demo](https://github.com/JoverZhang/JNI-example/blob/master/src/com_ttmo_HelloJNI.cc)) )

> Omitted here.

#### 5. Build ``.so`` file with ``cmake`` and ``make``.

```shell script
cd $PROJECT_HOME
./build.sh
```

#### 6. Run ``JNITest.java`` to test your ``JNI``.

```shell script
cd $PROJECT_HOME
./build/bin/run.sh
```

## Windows

emmm... I don't know.

# Example
```shell script
cd src
javah -classpath ./java com.ttmo.DemoLib
```


# Extend

#### Compiler your ".java" file.

```shell script
javac *.java
```

#### Generate header-file for ".java" file. 
**cd** to **CLASSPATH** of your **java project**.
```shell script
javah -classpath {CLASSPATH} {classes}
```
