# Spring-Legacy-basic

### Project Start and Setting
1. Spring Legacy Project 만들기
2. pom.xml  
   자바 버전, spring-framework 버전 수정  
   dependency 설정  
3. web.xml  
   [ context-param을 listener를 통해 servlet에서 사용 ]  
   encoding filter 추가  
4. root-context.xml  
   [ dataSource -> sqlSessionFactoryBean -> sqlSessionTemplate ]  
   sqlSessionFactoryBean: DB와 mapper 연결, ORM typeAliases 지정  
   
   xsi:schemaLocation url 추가  
   http://www.springframework.org/schema/context  
   http://www.springframework.org/schema/context/spring-context-3.1.xsd  
     
   db.properties 파일을 해당 패키지에 넣기  
   <context:property-placeholder>로 db.properties 데이터 가져오기 - xmlns:context 추가  
  
5. mapper xml파일 생성  
   dtd 추가, mapper 껍데기 생성  
   DB 데이터 추가, 수정, 삭제하는 query 생성  
   - id: DAO에서 연결할 mapper의 method  
   - parameterType: method의 파라미터 Type  
   - resultType: method의 return Type  
  
6. Spring에서 DB 데이터를 담고 있을 DTO class 생성  
7. Tomcat 정상 작동하는지 확인  
  
--------
### Spring MVC Start
