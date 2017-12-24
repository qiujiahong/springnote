# 工程搭建


## 创建项目

* 创建项目，打开网页https://start.spring.io/
* 填写group,artfact选择web依赖，点击生成项目
* 下载项目，使用idea打开
* 删除src文件夹
* 删除原有``dependencies``,``build``,
* 修改包信息

```xml
	<groupId>com.loc.study</groupId>
	<artifactId>spring-cloud-study</artifactId>
	<version>1.0-SNAPSHOT</version>
	<packaging>pom</packaging>
	<name>spring-cloud-study</name>
	<description>Demo project for Spring Boot</description>
```

* 添加子模块
```xml
	<modules>
		<module>spring-cloud-app</module>
	</modules>
```
* 添加依赖

```xml
    <properties>
		<spring.boot.version>1.5.8.RELEASE</spring.boot.version>
		<spring.cloud.version>Dalston.SR4</spring.cloud.version>
	</properties>

	<dependencyManagement>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-dependencies</artifactId>
			<version>${spring.boot.version}</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-dependences</artifactId>
			<version>${spring.cloud.version}</version>
		</dependency>
	</dependencies>
	</dependencyManagement>
```
* 添加build
```xml
<build>
		<pluginManagement>
			<plugins>
				<plugin>
					<groupId>org.apache.maven.plugins</groupId>
					<artifactId>maven-compiler-plugin</artifactId>
					<configuration>
						<compilerVersion>1.8</compilerVersion>
						<source>1.8</source>
						<target>1.8</target>
					</configuration>
				</plugin>
				<plugin>
					<groupId>org.springframework.boot</groupId>
					<artifactId>spring-boot-maven-plugin</artifactId>
					<version>${spring.boot.version}</version>
					<executions>
						<execution>
							<goals>
								<goal>repackage</goal>
							</goals>
						</execution>
					</executions>
				</plugin>
			</plugins>
		</pluginManagement>
	</build>
```

* 根目录下新建文件夹``spring-cloud-app``
* 新建``spring-cloud-app/pom.xml``文件夹
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>com.loc.study</groupId>
		<artifactId>spring-cloud-study</artifactId>
		<version>1.0-SNAPSHOT</version>
	</parent>
	<artifactId>spring-cloud-app</artifactId>
	<version>1.0-SNAPSHOT</version>

	<properties>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
		<project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
		<java.version>1.8</java.version>
	</properties>

	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>


</project>
```
* 新建文件夹``spring-cloud-app/src/main/java``

* 右键java文件夹，选择``mark directory as source code``
* 新建包``com.loc.study.springboot.app``
* 包下面新建类``Application``  

```java
package com.loc.study.springboot.app;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class Application {
    public static void main(String[] args){
        SpringApplication.run(Application.class,args);
    }
}
```


## 项目地址

* spring cloud： https://github.com/spring-cloud/spring-cloud-release/releases
* spring boot ： https://github.com/spring-projects/spring-boot

* mavnen 使用dependencyManagement管理依赖

```xml
	<dependencyManagement>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-dependencies</artifactId>
			<version>${spring.boot.version}</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-dependences</artifactId>
			<version>${spring.cloud.version}</version>
		</dependency>
	</dependencies>
	</dependencyManagement>
```

* mark diectory as source root

## spring-cloud-config
分布式配置中心

