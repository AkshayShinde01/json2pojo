[中文 README](README.cn.md)

## Introduction
An IntelliJ Idea plugin which generate POJOs from JSON with Lombok and gson/jackson annotations.

## Installation
From IntelliJ Idea plugin marketplace search `Json2Pojo with Lombok`.

## Usage
1. From context of a package，select "New-> Generate POJOs from JSON".
![Context menu](image/menu.jpg "菜单")

2. Input root class name and source JSON.
![Input UI](image/input.jpg "输入")

## Example
Json

	{
	  "javaHome": "c:\\java18",
	  "java.version": "12",
	  "scala.Version": "2.12.8"
	}

POJO class

    package test;

    import com.google.gson.annotations.SerializedName;
    import lombok.Data;
    import lombok.experimental.Accessors;

    @Data
    @Accessors(fluent = true)
    @SuppressWarnings("unused")
    public class Version {
        private String javaHome;
        @SerializedName("java.version")
        private String javaVersion;
        @SerializedName("scala.version")
        private String scalaVersion;
    }

## Settings
![Settings UI](image/config.jpg)

Settings file ~/.json2pojo

    {
      "primitive": true,
      "field.name.annotation": 1,
      "lombok.accessors": false,
      "lombok.accessors.fluent": true,
      "lombok.accessors.chain": true,
      "lombok.accessors.prefix": "",
      "lombok.builder": false,
      "lombok.data": true,
      "lombok.no.args.constructor": false,
      "lombok.required.args.constructor": true,
      "lombok.all.args.constructor": false
    }

