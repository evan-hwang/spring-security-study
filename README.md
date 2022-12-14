# spring-security-study
๐ Spring Security ๊ณต๋ถํ๊ธฐ

### ๊ฐ๋
- [Spring Security ์ํคํ์ฒ]([url](https://spring.io/guides/topicals/spring-security-architecture))

### OAuth2
- [ ] OAuth2 ์ธ์ฆ
- [ ] oauth2Login, authorizeRequests ์์
- [ ] oauth2Login ์ธ์ฆ ์ฒ๋ฆฌ ์ค ๋ฐ์ํ ์๋ฌ
  - OAuth2AuthenticationSuccessHandler ๋ด๋ถ์์ AuthenticationException ๋๋ AccessDeniedException ๋์ง๋๊ฒ ๋ง๋? ๋์ง๋ค๋ฉด ์ด๋ป๊ฒ ์ก์ง?
  - Authentication ๊ฐ์ฒด ์์ฒด๊ฐ ๋์ด์จ๋ค๋๊ฑด ์ด๋ฏธ ์ธ์ฆ ์ฒ๋ฆฌ ๋๋ค๋ ๊ฒ
  - oauth2Login์์๋ `DefaultOAuth2UserService` ์์ฒด๊ฐ `UserDetailsService`๋ฅผ ๋์ฒดํ๋ค.
  - `DefaultOAuth2UserService`์์ ์ฌ์ฉ์ ์ธ๋ถ ์ ๋ณด ์กฐํํ  ๋๋ถํฐ ์๋ฌ๋ฅผ ๋ ๋ฆฌ๋ฉด๋์ง ์๋? `AuthenticationProvider` ๊ฐ์ ์ญํ ์ ๋ฌด์์ธ๊ฐ
  - ์์ฒญ์ MVC ๊ณ์ธต์ ๋๋ฌํ๊ธฐ ์ ์ Security ํ๋ ์์ํฌ์ ์ํด ๊ฑฐ๋ถ๋๋ฏ๋ก @ControllerAdvice์ฌ๊ธฐ์๋ ์ต์์ด ์๋๋๋ค.

### ํ ํฐ ์ธ์ฆ
- [ ] JWT ํ ํฐ ๋ฒ ์ด์ค ์ธ์ฆ ์ฒ๋ฆฌ
- [ ] JWT Authentication ์์ฑ Filter ํน์  URL์ ํํฐ๋ง ๋ฐฐ์  ํ๋ ๋ฐฉ๋ฒ
  - MicroService ์ข๋จ ๊ฐ์ JWT ํ ํฐ ํํฐ๋ง์ ํ์ง ์๊ธฐ ์ํจ
  - AuthorizeRequests ๋ก ๊ถํ ์ฒดํฌ ์ permitAll ์ค์ ์ด๋์ ๊ด๊ณ ์์
  - ์ฐธ๊ณ  (https://spring.io/guides/topicals/spring-security-architecture)
  
### Spring ํํฐ ๊ตฌ์กฐ ์๋ฒฝ ์ ๋ฆฌ
- [ ] [Filter ๊ตฌ์กฐ](https://docs.spring.io/spring-security/reference/servlet/architecture.html#servlet-filters-review)
  - doFilter, doFilterInternal
  - [x] [Filter์ Interceptor](https://mangkyu.tistory.com/173)
  - [x] [ํํฐ(Filter)๊ฐ ์คํ๋ง ๋น ๋ฑ๋ก๊ณผ ์ฃผ์์ด ๊ฐ๋ฅํ ์ด์ ](https://mangkyu.tistory.com/221)

## ์ฐธ๊ณ 
- [Deeplify ๋ธ๋ก๊ทธ](https://deeplify.dev/back-end/spring/oauth2-social-login)
- [Callicoder ๋ธ๋ก๊ทธ](https://www.callicoder.com/spring-boot-security-oauth2-social-login-part-1/)
- [Spring Security OAuth2 Login Flow](https://jyami.tistory.com/121)
