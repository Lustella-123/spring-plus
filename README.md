# SPRING PLUS 주차 개인 과제

## 필수 기능

### Level. 1

#### 1. 코드 개선 퀴즈 - @Transactional의 이해

할 일 저장 기능을 구현한 API(/todos) 호출 시 발생하는 에러 해결

에러 로그:

jakarta.servlet.ServletException: Request processing failed: org.springframework.orm.jpa.JpaSystemException: could not execute statement [Connection is read-only. Queries leading to data modification are not allowed] [insert into todos (contents,created_at,modified_at,title,user_id,weather) values (?,?,?,?,?,?)]

정상적으로 할 일을 저장하도록 코드 수정

#### 2. 코드 추가 퀴즈 - JWT의 이해

User 테이블에 nickname 컬럼 추가 (중복 가능)

JWT에서 nickname을 추출하여 프론트엔드에서 화면에 출력

#### 3. 코드 개선 퀴즈 - AOP의 이해

UserAdminController의 changeUserRole() 메소드 실행 전에 AOP 동작하도록 수정

AdminAccessLoggingAspect 클래스의 AOP 코드 수정

#### 4. 테스트 코드 퀴즈 - 컨트롤러 테스트의 이해

org.example.expert.domain.todo.controller 패키지의 todo_단건_조회_시_todo가_존재하지_않아_예외가_발생한다() 테스트 실패 수정

#### 🚨5. 코드 개선 퀴즈 - JPA의 이해

할 일 검색 기능 개선

weather 조건 추가 (있을 수도, 없을 수도 있음)

수정일 기준 기간 검색 추가 (시작 및 끝 조건 선택 가능)

JPQL 사용 및 적절한 메소드명 설정

필요 시 서비스 단에서 여러 개의 쿼리(JPQL) 사용 가능

##### 🔥어려웠던점
- 조건을 추가하는 쿼리를 새로 만들어야 하는 것이 어려웠음. Querydsl을 사용하면 괜찮았을 것 같으나 **Jparepository 내에서 해결하고 싶어서** `Query문`을 쓰다보니 여러 `@Param`도 받아서 처리하는 등 힘들었음.

### Level. 2

#### 6. JPA Cascade

할 일을 저장할 때, 생성한 유저를 담당자로 자동 등록

JPA의 cascade 기능 활용

#### 7. N+1 문제 해결

CommentController의 getComments() API 호출 시 발생하는 N+1 문제 해결

SQL 쿼리 성능 개선

#### 8. QueryDSL 적용

findByIdWithUser JPQL 쿼리를 QueryDSL로 변환

N+1 문제 발생 방지

#### 🚨9. Spring Security 적용

기존 Filter 및 Argument Resolver 제거

Spring Security로 접근 권한 및 유저 권한 유지

JWT 기반 인증 방식 유지

##### 🔥어려웠던점
- 그냥 Spring Security 자체를 적용하는거는 할 수 있을 것 같았는데, 있던 코드를 수정하여 만드는 것이 어려웠음.
