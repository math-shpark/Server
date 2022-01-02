# Tomcat Manager 등록

1. putty 접속
2. cd /opt/tomcat/apache-tomcat-9.0.56/webapps/manager/META-INF
3. vi context.xml
4. 하단의 <Valve~/> 모두 주석 처리 후 저장
5. cd ../../../conf
6. vi tomcat-users.xml
7. 하단의 <!-- <role>들어있는 부분 --> 수정
    
    ```html
    
    <role rolename="manager-gui"/>
    <role rolename="manager-script"/>
    <role rolename="manager-status"/>
    <user username="tomcat_admin" password="mcsn" roles="manager-gui,	manager-script, manager-status"/>
    <!--
    <user username="both" password="<must-be-changed>"	roles="tomcat,role1"/>
    <user username="role1" password="<must-be-changed>"	roles="role1"/>
    -->
    ```
    
8. ./shutdown.sh -> ./startup.sh 실행
9. [http://101.101.211.109:8080/manager/html](http://101.101.211.109:8080/manager/html) 로 접속
10. tomcat_admin / mcsn 으로 로그인
11. 배치된 것을 제거 -> 서버에 올라가져 있는 해당 웹 삭제
12. 시작 및 중지도 컨트롤 가능

---