# NextStep
도서 자바 웹 프로그래밍 NextStep 공부 내용

memos 에 공부 내용 정리


# 실습을 위한 개발 환경 세팅
* https://github.com/slipp/web-application-server 프로젝트를 자신의 계정으로 Fork한다. Github 우측 상단의 Fork 버튼을 클릭하면 자신의 계정으로 Fork된다.
* Fork한 프로젝트를 eclipse 또는 터미널에서 clone 한다.
* Fork한 프로젝트를 eclipse로 import한 후에 Maven 빌드 도구를 활용해 eclipse 프로젝트로 변환한다.(mvn eclipse:clean eclipse:eclipse)
* 빌드가 성공하면 반드시 refresh(fn + f5)를 실행해야 한다.

# 웹 서버 시작 및 테스트
* webserver.WebServer 는 사용자의 요청을 받아 RequestHandler에 작업을 위임하는 클래스이다.
* 사용자 요청에 대한 모든 처리는 RequestHandler 클래스의 run() 메서드가 담당한다.
* WebServer를 실행한 후 브라우저에서 http://localhost:8080으로 접속해 "Hello World" 메시지가 출력되는지 확인한다.

# 각 요구사항별 학습 내용 정리
* 구현 단계에서는 각 요구사항을 구현하는데 집중한다. 
* 구현을 완료한 후 구현 과정에서 새롭게 알게된 내용, 궁금한 내용을 기록한다.
* 각 요구사항을 구현하는 것이 중요한 것이 아니라 구현 과정을 통해 학습한 내용을 인식하는 것이 배움에 중요하다. 

### 요구사항 1 - http://localhost:8080/index.html로 접속시 응답

### 요구사항 2 - get 방식으로 회원가입

### 요구사항 3 - post 방식으로 회원가입
* Content-Length 길이만큼 Body를 읽는다.

### 요구사항 4 - redirect 방식으로 이동
* HTTP 응답 헤더 : 302

### 요구사항 5 - cookie
* url.startWith 에서 login.html 접근하는것과 login  접근하려고 할 때, 구분하기위해 equals 로 변경
* 브라우저는 Set-Cookkie 값을 읽어서 response Cookies 에 해당 값을 세팅한다.

### 요구사항 6 - 사용자 목록 출력
* Header에 Cookie 값 읽어서, 로그인 여부 체크
* 로그인 성공 시, Cookie 값이 세팅되고 난뒤에 Header에는 Cookie값이 항상 있다.
* Request 할 때마다, Cookie 값이 있는데 확인, 있다면 로그인 여부 체크

### 요구사항 7 - stylesheet 적용
* 클라이언트가 서버에 요청에 보내면, html을 응답으로 보낸다.
 브라우저는 index.html 을 읽은 다음에, 그 안에 포함되어 있는 css, js, image 를 분석한 뒤, 서버에 재요청한다.

* 개발자도구로 확인해보면 200 으로 나오긴 하지만, Content-Type 이 html로 인식해서 그렇다.
 css 파일에 대해서는 다른 Content-Type을 지정한다.

* request header를 보면 Accept: text/css 으로 요청이 오는데,
 이부분을 읽어서 response header에 Content-Type 값을 정해줘도 된다.
 
### heroku 서버에 배포 후
실습을 위한 개발 환경 세팅


# 5. 웹 서버 리팩토링, 서블릿 컨테이너/서블릿 과의 관계

### 요구사항 1 - 요청 데이터를 처리하는 로직으르 별도의 클래스로 분리한다(HttpRequest)

* 
