# Learn Spring Boot

## JDK 설치

- 구글 AdoptOpenJdk 검색
- OpenJDK 8 버전
  cmd에서 다음 명령어로 설치 확인 java -version

## IDE 준비

인텔리제이 설치 - 무료 버전으로 설치

## 스프링 부트 프로젝트 생성

- [스프링 부트 프로젝트 생성](start.spring.io)

1. 사이트 좌측 설정

- Project - Gradle Project
- Language - Java
- Spring Boot - 2.5.5
- Artifact - firstproject
- Packaging - Jar
- Java - 8

2. 사이트 우측 설정 (필요한 도구들 가져오기)

- Spring Web
- H2 Database
- Mustache
- Spring Data JPA

3. GENERATE 클릭하면 프로젝트가 생성된다.
4. zip파일 압축풀고 인텔리제이로 열어준다.

## 프로젝트 실행

- 메인 메서드를 실행하면 8080 포트로 실행된다.
- 웹서버 동작

## 뷰 템플릿과 MVC 패턴

- Mustache는 뷰 템플릿을 만드는 도구
- Controller(처리과정), Model(데이터)

### 뷰 템플릿 만들기

- 뷰 템플릿을 만들려고 src/main/resources/templates에서 greetings.mustache 파일을 생성하면 mustache를 인식하지 못한다.
- 인텔리제이에서 Help > Find Action > plugins > Marketplace에서 mustache 검색
- Handlebars/Mustache 설치
- 다시 src/main/resources/templates에서 greetings.mustache 파일을 생성

### 컨트롤러 만들기

- src/main/java/com.example.firstproject 에서 New > Package 로 controller 패키지를 만든다.
- src/main/java/com.example.firstproject/controller 에서 New > Java Class 로 FirstController 를 만든다.
- @Controller로 컨트롤러를 선언
- 함수 안에 불러올 mustache 파일명을 return 값으로 넣어서 선언
- @GetMapping으로 접근할 uri를 선언

```Java
package com.example.firstproject.controller;

import org.springframework.stereotype.Controller; // 컨트롤러를 선언하면서 자동으로 생성
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller // 1) 컨트롤러를 선언
public class FirstController {

    @GetMapping("/hi")
    public String niceToMeetYou(Model model) {
        model.addAttribute("username", "yeonwook");
        return "greetings"; // templates/greetings.mustache -> 브라우저로 전송!
    }
}
```

## 강좌

- [듣던 강좌 05](https://www.youtube.com/watch?v=5vfxeRJJsWo&list=PLyebPLlVYXCiYdYaWRKgCqvnCFrLEANXt&index=5)
