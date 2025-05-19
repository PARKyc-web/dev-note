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

