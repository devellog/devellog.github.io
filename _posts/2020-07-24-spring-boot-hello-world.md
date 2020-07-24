---
layout: post
title:  "Spring Boot Web 시작하기"
date:   "2020-07-24 00:00:00"
author: Sean
categories: spring-boot
tags:	spring-boot
#cover:  "/assets/instacode.png"
---

### 참고

* [Spring Boot](https://spring.io/projects/spring-boot)
* [Spring Guide](https://spring.io/guides)


<br/>

### IDE

* [Eclipse](https://www.eclipse.org/downloads/)

#### Plugin

* Eclipse 메뉴 'Help > Eclipse Marketplace' 선택  
  -- Find: 'Spring' 입력  
  -- Spring Tools 4 (aka Spring Tool Suite 4) 4.7.0.RELEASE - 'Install' 클릭  
  -- 'Confirm' 클릭  
  -- 'I accept the terms of the license agreements' 체크, 'Finish' 클릭  
  -- 'Restart Now' 클릭  


<br/>

### demo 프로젝트

* 메뉴 'File > New > Project' 선택  
  -- Wizards: 'spring' 입력  
  -- 'Spring Starter Project' 선택, 'Next' 클릭  
* 프로젝트 구성  
  -- Maven 확인, 'Next' 클릭  
  -- Dependency 선택 : 'Web > Spring Web' 체크, 'Finish' 클릭  
* 프로젝트 생성 결과
<img src="/assets/images/posts/2020/2020-07-24-spring-boot-hello-world-03.png" style="width:300px">
* 프로젝트 실행  
  -- 'DemoApplication.java' 마우스 우클릭, 'Run As > Spring Boot App' 선택  
  -- Console message  
  &nbsp;&nbsp;&nbsp; > Tomcat initialized with port(s): 8080 (http)  
  &nbsp;&nbsp;&nbsp; > Tomcat started on port(s): 8080 (http) with context path ''  
<img src="/assets/images/posts/2020/2020-07-24-spring-boot-hello-world-05.png">


<br/>

### Hello World

* 'pom.xml' dependency 추가  

{% highlight xml %}
		<dependency>
			<groupId>javax.servlet</groupId>
			<artifactId>jstl</artifactId>
		</dependency>
		<dependency>
			<groupId>org.apache.tomcat.embed</groupId>
			<artifactId>tomcat-embed-jasper</artifactId>
			<scope>provided</scope>
		</dependency>
{% endhighlight %}

* 'application.yml' 생성  
  -- 'application.properties' 파일은 삭제  

{% highlight yml %}
server:
  port: 80
spring:
  mvc:
    view:
      prefix: /WEB-INF/jsp/
      suffix: .jsp
{% endhighlight %}

* 'HelloController.java' 생성

{% highlight java %}
package com.example.demo;

import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;

import java.util.HashMap;
import java.util.Map;

@Controller
public class HelloController {

    @RequestMapping("/hello")
    public String helloJSP() {
        return "hello";
    }

    @RequestMapping("/api/hello")
    public ResponseEntity<?> helloAPI() {
        Map data = new HashMap<String, Object>();
        data.put("data", "hello World");
        return new ResponseEntity<>(data, HttpStatus.OK);
    }
}
{% endhighlight %}

* 'hell.jsp' 생성  
  -- 경로 : 'demo/src/main/webapp/WEB-INF/jsp'  

{% highlight jsp %}
{% raw %}<%@ page contentType="text/html;charset=UTF-8" language="java" %>{% endraw %}
<html>
<head>
    <title>Hello</title>
</head>
<body>
Hello JSP
</body>
</html>
{% endhighlight %}

* 브라우저 실행 결과  
  -- by JSP  
<img src="/assets/images/posts/2020/2020-07-24-spring-boot-hello-world-07.png" style="width:400px">
  -- by Rest API  
<img src="/assets/images/posts/2020/2020-07-24-spring-boot-hello-world-06.png" style="width:400px">
