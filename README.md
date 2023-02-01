# spring-basic

### Project Start
1. Spring Legacy Project 만들기
2. pom.xml
   자바 버전, spring-framework 버전 수정
   dependency 설정
3. web.xml
   context-param을 listener를 통해 servlet에서 사용
4. root-context.xml
   [ dataSource -> sqlSessionFactoryBean -> sqlSessionTemplate ]
   sqlSessionFactoryBean: mapper 연결, 
   
   db.properties 파일을 해당 패키지에 넣기
   <context:property-placeholder>로 db.properties 데이터 가져오기 - xmlns:context 추가
