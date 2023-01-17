# spring-security-study
🔒 Spring Security 공부하기

### 개념
- [Spring Security 아키텍처]([url](https://spring.io/guides/topicals/spring-security-architecture))
- [ ] CSRF
- [ ] CORS

### OAuth2
- [ ] OAuth2 인증
- [ ] oauth2Login, authorizeRequests 순서
- [ ] oauth2Login 인증 처리 중 발생한 에러
  - OAuth2AuthenticationSuccessHandler 내부에서 AuthenticationException 또는 AccessDeniedException 던지는게 맞나? 던진다면 어떻게 잡지?
  - Authentication 객체 자체가 넘어온다는건 이미 인증 처리 됐다는 것
  - oauth2Login에서는 `DefaultOAuth2UserService` 자체가 `UserDetailsService`를 대체한다.
  - `DefaultOAuth2UserService`에서 사용자 세부 정보 조회할 때부터 에러를 날리면되지 않나? `AuthenticationProvider` 같은 역할은 무엇인가
  - 요청은 MVC 계층에 도달하기 전에 Security 프레임워크에 의해 거부되므로 @ControllerAdvice여기서는 옵션이 아닙니다.

### 토큰 인증
- [ ] JWT 토큰 베이스 인증 처리
- [ ] JWT Authentication 생성 Filter 특정 URL은 필터링 배제 하는 방법
  - MicroService 종단 간은 JWT 토큰 필터링을 하지 않기 위함
  - AuthorizeRequests 로 권한 체크 시 permitAll 설정이랑은 관계 없음
  - 참고 (https://spring.io/guides/topicals/spring-security-architecture)
  
### Spring 필터 구조 완벽 정리
- [ ] [Filter 구조](https://docs.spring.io/spring-security/reference/servlet/architecture.html#servlet-filters-review)
  - doFilter, doFilterInternal
  - [x] [Filter와 Interceptor](https://mangkyu.tistory.com/173)
  - [x] [필터(Filter)가 스프링 빈 등록과 주입이 가능한 이유](https://mangkyu.tistory.com/221)
- authorizeRequests와 커스텀 필터 동작 순서는?
  - <img width="413" alt="스크린샷 2023-01-13 오후 3 59 20" src="https://user-images.githubusercontent.com/10377550/212263997-46a1da62-969d-4f63-9806-9601d6f1c9d3.png">
  - `authorizeRequests`는 인가 처리에 대한 정의로 `FilterSecurityInterceptor` 필터를 생성합니다.
  - 즉 해당 로직도 필터를 생성하므로 커스텀 필터 정의 순서에 따라 동작 순서가 달라집니다.
- 특정 엔드포인트에 필터 체인 정의하기
  - <img width="860" alt="스크린샷 2023-01-13 오후 4 31 42" src="https://user-images.githubusercontent.com/10377550/212264320-c2b8d361-097c-43bc-a515-81a68942a1e5.png">
  - `antMatcher`를 이용해 특정 엔드포인트에 대한 내용을 정의할 수 있습니다.
  - 참고자료
    - 필터 체인을 특정 endpoint와 엮기 (https://www.springcloud.io/post/2022-02/spring-security-match-to-specific-requests/#gsc.tab=0)
    - How to apply Spring Security filter only on secured endpoints? (https://stackoverflow.com/questions/36795894/how-to-apply-spring-security-filter-only-on-secured-endpoints)
- [ ] [web.ignoring](https://ohtaeg.tistory.com/11)
- [ ] antMatcher

## 참고
- [Deeplify 블로그](https://deeplify.dev/back-end/spring/oauth2-social-login)
- [Callicoder 블로그](https://www.callicoder.com/spring-boot-security-oauth2-social-login-part-1/)
- [Spring Security OAuth2 Login Flow](https://jyami.tistory.com/121)
