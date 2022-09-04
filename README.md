![cover](cover.jpg)

# 스프링 부트 핵심 가이드

- 장정우 지음
- 28,000원 | 2022년 6월 24일 발행 | 452쪽
- [책 홈페이지](https://wikibook.co.kr/springboot/)
- [도서 미리보기](http://www.yes24.com/Product/Viewer/Preview/110142898)
- [도서 관련 문의](https://wikibook.co.kr/support/contact/)

---

**입문자의 눈높이에 맞춰 차근차근 따라 하면서 배우는 스프링 부트 입문서!**

《스프링 부트 핵심 가이드》는 스프링 부트 기반의 애플리케이션을 개발할 때 필요한 기초적인 내용들을 소개하고, 스프링에서 제공하는 각종 라이브러리의 기능들을 이해할 수 있게 동작 원리를 상세히 설명합니다. 또한 ‘스프링 부트’다운 코드를 작성하는 방법에 초점을 맞춰 스프링 부트에서 제공하는 편의 기능들을 최대한 활용하고, 스프링 부트 기반의 애플리케이션을 어떻게 설계하고 구현하는지 안내합니다.
 
---
 
 ## 구입처
 
 - [예스24](http://www.yes24.com/Product/Goods/110142898)

4장 - talend api tester 사용법 소개
6장 - 데이타베이스 연동
 - 엔티티 관련 기본 어노테이션: 
   @Entity
   @Table
   @Id, @GeneratedValue - AUTO, IDENTITY, SEQUENCE, TABLE
   @Column
   @Transient
   
  - 스프링에서 관리하는 빈으로 등록
  @Component 또는 @Service


-getById()와 findById()의 차이  
 data/dao/impl/ProductDaOImpl.java
. getById(): em의 getReference()메소들 호출하면서 프락시 객체를 리턴. 실제 쿼리는 프락시 객체를 통해 최초로 접근되는 시점에 실행. 없으면 EntityNotFoundException,dmf qkftod
   예) Product selectProduct = productRepository.getById(number);
   
. findById(): 영속성 컨텍스트의 캐시에서 값을 조회하고 없으면 실제 데이타베이스에서 조회. 리턴 값으로 Optional 객체를 전달. IsPresent()를 이용해서 얻은 후에 get
   예) Optional<Product> selectProduct=productRepository.findById(number);
      if(selecProduct.isPresent())
         Product product = selectProduct.get();
         .. 
         product.setName(name);
         .. 
         updateProduct = productRepository.save(product);
