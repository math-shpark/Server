# MySQL 서버 등록

1. putty 접속
2. `service mysql status` 입력
3. `Active : active (running)` 확인 후 ctrl+c 눌러서 나옴
4. mysql workbench 실행
5. 새 접속 만들기 클릭
6. connection name에 putty 아이디 입력
7. hostname에 공인 IP 주소 입력
8. Test Connection을 클릭해서 연결 여부 확인
9. n클라우드 홈페이지 접속
10. `ncloud-default-acg`
11. `0.0.0.0/0 - 3306 - mysql`
12. 서버 재시작
13. MySQL workbench에서 생성 확인 후 접속
14. `mysql_mc / timezone_leap` 추가
15. `timezone_leap` 맨위에 `use mysql` 추가
16. 번개 표시 누르고 대기
17. 완료되면 `mysql_mc`에서 체크
18. `cd /etc/mysql/`
19. `ls`
20. `my.cnf` 확인
21. `cat my.cnf`
22. `vi my.cnf`
23. 최하단으로 이동한 후 `i` 눌러서 수정 모드로 변환
24. 최하단에 라인 추가
    
    ```html
    default-time-zone=Asia/Seoul
    [client]
    default-character-set=utf8
    [mysql]
    default-character-set=utf8
    [mysqld]
    collation-server=utf8_unicode_ci
    init-connect='SET NAMES utf8'
    character-set-server=utf8
    ```
    
25. `esc` 누른 후 `:wq` 눌러 저장하고 나옴
26. `service mysql restart`
27. running 다시 확인
28. `mysql -uroot`
29. `alter user 'root'@'localhost'identified by '비빌번호';`
30. `create user '아이디'@'%' identified by '비밀번호';`
31. `grant all privileges on *.* to '아이디'@'%';`
32. 종료
33. 클라우드 홈페이지에 접속
34. public IP 신청, Zone : KR-2, 적용 서버 선택

---