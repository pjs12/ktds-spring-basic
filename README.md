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
1. Main 페이지 jsp파일 생성  
   jstl 이용을 위해 taglib 작성  
   <%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>  
   
   JSTL 문법 알아놓기  
   - <c:choose> : Switch 문  
   - <c:when> : Switch case 역할  
   - <c:otherwise> : Switch default 역할  
   - <c:forEach> : 향상된 for문  
  
2. DAO interface, DAOImpl class 생성  
   mapper에서 생성한 query를 이어줌  
   - mapper에서 설정한 parameterType, resultType 유의하여 메소드 생성  
   - Autowired로 SqlSessionTemplate 객체 생성하여 메소드 생성  
  
3. Service interface, ServiceImpl class 생성  
   DAO에서 생성한 메소드 이어줌  
   - Autowired로 DAO 객체 생성하여 메소드 생성  
  
4. Controller class 생성  
   해당 url에 Service에서 생성한 메소드를 View에 이어줌  
   - Autowired로 Service 객체 생성하여 메소드 생성  
   - 데이터를 이용해야하면 ModelAndView Type, View만 보여주면되면 String Type  
  
   Get 형식, Post 형식 구분하여 Mapping  
