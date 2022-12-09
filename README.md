# spring-security-study
🔒 Spring Security 공부하기

### OAuth2
- [ ] OAuth2 인증

### 토큰 인증
- [ ] JWT 토큰 베이스 인증 처리
- [ ] JWT Authentication 생성 Filter 특정 URL은 필터링 배제 하는 방법
  - MicroService 종단 간은 JWT 토큰 필터링을 하지 않기 위함
  - AuthorizeRequests 로 권한 체크 시 permitAll 설정이랑은 관계 없음
  - 참고 (https://spring.io/guides/topicals/spring-security-architecture)
