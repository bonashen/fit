# Fit

[![Release](https://jitpack.io/v/2tu/fit.svg)](https://jitpack.io/#2tu/fit) [![Build Status](https://travis-ci.org/2tu/fit.svg?branch=master)](https://travis-ci.org/2tu/fit) [![Apache License](http://img.shields.io/hexpm/l/plug.svg?style=flat)](https://github.com/kentarosasaki/raspberrypi/blob/master/LICENSE)

Fit 使用SharedPreferences存储对象中的基本数据类型。利用APT编译时生成代码，与转成String及反射相比更快。

## support
* 基本类型
* 基本包装类型
* Set<String>
* minSDK 11



## Installation
Add it in your root build.gradle at the end of repositories:

```
dependencies {
   classpath 'com.neenbedankt.gradle.plugins:android-apt:1.8'
}

allprojects {
	repositories {
		...
		maven { url "https://jitpack.io" }
	}
}
```
Add the following dependency to your `build.gradle` file:

```
apply plugin: 'com.neenbedankt.android-apt'

dependencies {
    compile 'com.github.2tu.fit:fit:0.1.3'
    apt 'com.github.2tu.fit:fit-compiler:0.1.3'
}
```

## Usage
annotation model class.
```java
@SharedPreferenceAble
```

save
```java
User user = new User("Three.Tu");
Fit.save(this, user);
```
get
```java
User user = Fit.get(this, User.class);
```
clear
```java
Fit.clear(this, User.class);
```

## What's new (0.1.3) - [Changelog](https://github.com/2tu/fit/blob/master/CHANGELOG.md)
* 检查inner class
* 检查private构造
