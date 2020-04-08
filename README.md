# 20200330_spring-mybatis
## 비트캠프 final 팀프로젝트: spring-mybatis framework + MVC 

## 프로젝트 개요
* 팀 이름: TodakTodak
* 프로젝트명: 토닥토닥 프로젝트
* 참여인원: 5명
* 개발기간: 2020.01.17 ~ 2020.03.30 (전체 67일. working day: 45 x 8 = 360시간)
* 내용: 비영리단체의 업무 중, 인사관리, 전자결재, 일정관리를 중점으로 지원하는 그룹웨어.
* 개발환경: 
<pre>
Front-end : Client-Side-Script: HTML5, CSS3, JavaScript(ECMAScript3), jQuery, Ajax, BootStrap3, BootStrap4    Server-Side-Script : jsp-api 2.0, Servlet api 3.2

Data Handling : xml, json, plain-text

Back-end : JDK 1.7, Spring framework 3, Mybatis 3, Mybatis-spring 1.2, Oracle11g R 2 (AWS EC R2), 파일업로드 api – cos.jar, Jackson DataBind 2.5, Log4j 1.2

Open API : Daum 우편번호 찾기 API, Fullcalendar v4.3.1, Smart-editor v2, Flot Charts v3.0.0, Datepicker, JavaMail API v1.4
      
Tool : eclipse luna, Apache Tomcat 8.0, SQL Developer, STS, Erdwin, Git Bash, GitHub, StarUML, AWS, Chrome 8.0, Adobe Photoshop CC 2015, Adobe illustrator CC 2017</pre>   
   
* __나의 담당업무: PL, 문서작업, 후원관리 시각화, 형상관리, 공통로직 개발(로그인 세션처리, TX처리), 통합작업, 발표__
* 형상관리
	+ 툴 이름: Git, Github
	+ 사용방법: Git Bash를 사용. 로컬저장소에 깃디렉토리를 생성하고 그 디렉토리에 프로젝트파일을 push, pull 했음.

### 시스템 아키텍처
***
<p align="center">
<img src="/img/20200131_3조_토닥토닥_system_architecture.JPG" width="80%" height="60%" title="시스템 아키텍처"></img>
</p>   
   
* Presentation Layer, Controller Layer, Business Layer, Persistent Layer 4계층으로 나눔.
* MVC 패턴과, Facade패턴, DAO 패턴을 적용하고, 데이터 이동을 위해 VO를 사용.
* FrontController(Dispatcher Servlet)에서 사용자의 요청에 응답하고 handler mapping을 통해 적절한 Controller(Servlet)를 찾음.
* Controller(Servlet)에서는 필요한 데이터가 있으면 Service에 데이터를 요청하고 결과(model)를 FrontController에 반환.
* Service에서는 Java core 로직을 구현하고 Dao 데이터 요청하고 응답을 Controller에 반환.
* Dao에서는 적합한 mapper를 찾아 DB에 쿼리를 날리고, 결과를 Service에 반환.
* View Resolver에서는 반환된 결과를 적합한 View와 매칭.
* View에서는 html5, css3, js, jQuery, ajax, servlet api, jsp api 등을 사용해 웹페이지를 구현.
* 마지막으로 FrontController는 응답결과를 Client에게 반환.

### 프로젝트 제안서 (RFP)
***
<p align="center">
<img src="/img/프로젝트제안서.JPG" width="60%" height="40%" title="프로젝트제안서"></img>
</p>   

### 요구사항 정의서
***
<p align="center">
<img src="/img/요구사항정의서_전체.JPG" width="49%" height="40%" title="요구사항정의서_전체"></img>
<img src="/img/요구사항정의서.JPG" width="49%" height="40%" title="요구사항정의서"></img>
</p>   

### 요건 정의서
***
<p align="center">
<img src="/img/요건정의서_전체.JPG" width="49%" height="40%" title="요건정의서_전체"></img>
<img src="/img/요건정의서.JPG" width="49%" height="40%" title="요건정의서"></img>
</p>   

### WBS 프로젝트 일정
***
<p align="center">
<img src="/img/WBS프로젝트일정.JPG" width="60%" height="40%" title="WBS프로젝트일정"></img>
</p>   

### 명명규칙
***
<p align="center">
<img src="/img/명명규칙.JPG" width="60%" height="40%" title="명명규칙"></img>
</p>   

### 화면 정의서
***
<p align="center">
<img src="/img/로그인.JPG" width="49%" height="40%" title="로그인"></img>
<img src="/img/후원관리_모금액.JPG" width="49%" height="40%" title="후원관리_모금액"></img>
</p>   

### 테이블 정의서
***
<p align="center">
<img src="/img/테이블정의서_전체.JPG" width="49%" height="40%" title="테이블정의서_전체"></img>
<img src="/img/테이블정의서.JPG" width="49%" height="40%" title="테이블정의서"></img>
</p>   

### ERD
***
<p align="center">
<img src="/img/erd-physical.JPG" width="49%" height="40%" title="erd-physical"></img>
<img src="/img/erd2-physical.JPG" width="49%" height="40%" title="erd2-physical"></img>
<img src="/img/erd-logical.JPG" width="49%" height="40%" title="erd-logical"></img>
<img src="/img/erd2-logical.JPG" width="49%" height="40%" title="erd2-logical"></img>
</p>   

### 클래스 설계서
***
<p align="center">
<img src="/img/class_diagram_전체.JPG" width="49%" height="40%" title="class_diagram_전체"></img>
<img src="/img/class_diagram_1JPG.JPG" width="49%" height="40%" title="class_diagram_1JPG"></img>
</p>   

### 프로그램목록
***
<p align="center">
<img src="/img/프로그램목록_전체.JPG" width="49%" height="40%" title="프로그램목록_전체"></img>
<img src="/img/프로그램목록2.JPG" width="49%" height="40%" title="프로그램목록2"></img>
</p>   

### 프로젝트 구현 로그인
***
<p align="center">
<img src="/img/프로젝트_로그인.png" width="60%" height="40%" title="프로젝트_로그인"></img>
</p>   

### 프로젝트 구현 메인 (일정관리 페이지)
***
<p align="center">
<img src="/img/프로젝트_메인.png" width="60%" height="40%" title="프로젝트_메인"></img>
</p>   

### 프로젝트 구현 시각화
***
<p align="center"> 
<img src="/img/프로젝트_시각화.png" width="60%" height="40%" title="프로젝트_시각화"></img>
</p>
