# 工程搭建


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

