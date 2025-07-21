# BudgetLog Dev-note

```
VSCODE Extension - ERD Editor로 ERD 작성함.
```


> JPA로 만든 테이블의 컬럼의 정렬이 안됨
> ``` 
> Application.yaml 파일에서
> spring.init.mode = always
> spring.init.schema-locations : classpath:/schema.sql
> 두 개의 설정을 통해서 DDL을 직접 실행해서 테이블을 생성함 => 테이블 컬럼의 순서가 내가 작성한 대로 생성됨.
> ``` 

> schema.sql 로 DDL 작성시 문제점
> ``` 
> spring.init.mode = always 설정을 할 경우, schema.sql을 앱을 실행할때 마다 실행함.
> schema.sql에 DDL이 있을 경우, table already exist 에러가 발생
> 
> how-1) DDL을 변경한다. CREATE TABLE IF NOT EXISTS => sql 자체는 매번 실행됨.
> how-2) profile 을 2개 만들어서 관리한다??
>        => dev, prod yaml 파일을 2개 만들어서 처음에 dev에서만 DDL이 동작하도록 설정
> ``` 



# DB 스키마 변경사항 및 생각

```
USER_AUTH 테이블 LOGIN_ID 삭제 및 email 추가

가계부 앱을 사용하는데, 회원가입을 해야함. 그런데 여러가지를 입력받는 것 보다
이메일을 아이디로 사용하여, 사용자가 입력하는 부분을 최소화하기 위함.

기술적으로는 로그인 아이디를 입력하는 것과 이메일을 사용하는 것 둘 다 가능하지만
사용자 경험으로 생각하여, 이메일을 입력받는 것이 좋다고 판단됨.
```
```
USER_AUTH, USER_INFO 2개의 테이블로 나눈 이유
하나의 USER 테이블로 관리해도 기술적으로 문제가 되는것은 없으나

```

# MariaDB 접속에러

```
access denied for user 'budgetlog'@'localhost' (using password: yes)

budgetlog 계정의 만료?? 됨에 따라서 발생한 오류로 일단 파악함..

```