# spring-security-study
🔒 Spring Security 공부하기

### 개념
- [Spring Security 아키텍처]([url](https://spring.io/guides/topicals/spring-security-architecture))

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
- [ ] Filter 구조
  - doFilter, doFilterInternal
  - [x] [Filter와 Interceptor](https://mangkyu.tistory.com/173)
  - [x] [필터(Filter)가 스프링 빈 등록과 주입이 가능한 이유](https://mangkyu.tistory.com/221)

## 참고
- [Deeplify 블로그](https://deeplify.dev/back-end/spring/oauth2-social-login)
- [Callicoder 블로그](https://www.callicoder.com/spring-boot-security-oauth2-social-login-part-1/)
- [Spring Security OAuth2 Login Flow](https://jyami.tistory.com/121)
