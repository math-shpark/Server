# Tomcat 서버 등록

1. putty에서 로그인
2. java -version
-> 개발때 사용했던 자바버전과 맞춰줘야함
3. apt update
4. apt upgrade
-> 네이버 클라우드는 기본버전 sql을 제공하기 때문에 업데이트 필요
5. apt install openjdk-8-jdk
-> 3~5번 설치중에 선택나올시 모두 엔터 혹은 y
6. cd /usr/lib/jvm 에서 ls
-> 1.8.0 있는지 확인
7. [https://tomcat.apache.org/download-90.cgi](https://tomcat.apache.org/download-90.cgi) 에서 Core - tar.gz 링크주소복사
-> [https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.56/bin/apache-tomcat-9.0.56.tar.gz](https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.56/bin/apache-tomcat-9.0.56.tar.gz)
8. 콘솔 wget [복사된 링크 주소]
9. ls 쳐서 tar.gz 확인
10. mkdir /opt/tomcat
11. mv apache-tomcat-9.0.56.tar.gz /opt/tomcat
12. chmod 777 apache-tomcat-9.0.56.tar.gz
13. ls 쳐서 색깔 빨강->초록으로 변경 확인
14. tar xvf apache-tomcat-9.0.56.tar.gz
15. ls 쳐서 파란색으로 압축풀린 파일 생성 확인
16. cd apache-tomcat-9.0.56
17. cd bin
18. ./startup.sh
19. 크롬에서 [http://49.50.173.116:8080/](http://49.50.173.116:8080/) 접속
-> 만약 ACG에 8080 규칙이 없으면 안뜸
20. [https://filezilla-project.org/download.php?type=client](https://filezilla-project.org/download.php?type=client) 에서 FileZilla(첫라인) 다운로드
21. 다운받은거 설치 = 모두 디폴트로
22. New Site -> 우측의 호스트는 서버접속용 IP -> 포트는 포워딩한 포트 -> 아래는 root에 개인 비밀번호입력 -> 확인
23. 좌측 상단에 만든거 선택
24. 리모트 사이트에서 /opt/tomcat/apache-tomcat-9.0.56/conf 입력
25. context.xml 덮어쓰기 (왼쪽->오른쪽 드래그)
26. /opt/tomcat/apache-tomcat-9.0.56/webapps 로 이동
27. war 파일 옮기기 (왼쪽->오른쪽 드래그)
28. putty로 해당 경로 들어가서 war 파일이 자동으로 압축이 풀려있는지 확인
29. 크롬에서 [[http://49.50.173.116:8080/cocoa](http://49.50.173.116:8080/cocoa)] 접속
-> url에 대소문자 구분 확실히 해야함
30. 뜨는거 확인

---