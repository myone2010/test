# test

1
① groupadd GID 생성 -g 옵션
② usermod 그룹아이디 변경 -g 옵션

( ① ) -g 700 ihdg
( ② ) -g 800 ihd

2 
① fdisk
② mkfs.ext4 
③ t 

① ( ① ) /dev/sdc : 디스크 파티션을 만든다. 
② ( ② ) /dev/sdc1 : 파티션을 ext4 파일시스템 
으로 생성한다. 
③ mkdir /backup2014 : 마운트 포인트를 생성한다. 
④ mount -( ③ ) ext4 /dev/sdc1 /backup2014 : 
파티션(/dev/sdc1)을 /backup2014 디렉토리에 
마운트한다. 

3 
① crontab 
② vmstat 1 10 1초 단위로 10회씩
③ >> 

( ① ) -e
30 23 * * * ( ② ) 1 10 ( ③ ) /var/log/check.log

4 
① tar 1점 
② configure 1점 
③ prefix 1점 
④ enable 1점 

[root@ihd src]# ( ① ) zxvf httpd-2.2.34.tar.gz
[root@ihd src]# cd httpd-2.2.24
[root@ihd httpd-2.2.24]# ./( ② ) --( ③ )
=/usr/local/httpd --( ④ )-modules=so
[root@ihd httpd-2.2.24]# make
[root@ihd httpd-2.2.24]# make install

5 
① make mrproper 
② make config 
③ bzImage 


① 커널 컴파일 시에 문제가 되는, 이전에 생성
되어 있던 오브젝트 파일(*.o)들을 삭제(정리)
하고 모든 설정과 커널의 소스를 초기 상태로
돌리기 위해 사용하는 명령어를 쓰시오.

② 커널 컴파일을 위한 커널 옵션 설정은 텍스트
문답 방법, 메뉴 형식의 방법, 확장된 메뉴 형식의
방법, X윈도우 형식의 방법이 있다. 이 중 텍스트
문답 방법의 명령어를 쓰시오.

③ 커널 컴파일 설정 이후의 과정을 완성하시오.
# make clean
# make ( ) : 커널 생성(bzip2 형식)
# make modules
# make modules_install


6 
① -o 2점 
② loop 2점 

mount ( ① ) ( ② )
linux-server-x86_64-dvd.iso /media/

7 
① monthly 
② 6 
③ 644 

로그 파일을 월 단위로 rotate 하며, 백업
로그는 6개로 유지하고, 생성된 로그파일의
퍼미션을 rw-r--r-- 으로 지정한다.


# see "man logrotate" for details
# rotate log files weekly
( ① )
# keep 4 weeks worth of backlogs
rotate ( ② )
# create new (empty) log files after rotating old ones
create ( ③ )
# uncomment this if you want your log files compressed
#compress


8 
① secure 2점 
② messages 2점 

로그들의 위치는 /var/log 디렉터리

시스템의 접속에 관한 보안 로그파일인 ( ① )은
시스템의 불법 침입이 의심이 될 때 확인하는
로그이고, 시스템에 관련된 중요한 이벤트들은
모두 ( ② )파일에 기록된다.

9

패스워드 관리(login.defs)

PASS_MIN_LEN ( ① )
( ② ) ( ③ )

① 9 
② PASS_MAX_DAYS 
③ 90 

- 패스워드 변경없이 사용가능한 기간을 90일로
지정한다.
- 패스워드 길이는 9 자리로 지정한다.


10 
① --delete, 
1개:2점 
2개:3점 
3개:4점 
② -a, (--archive) 
③ -v, (--verbose) (정답순서무관)


# rsync ( ① ) ( ② ) ( ③ ) /home
192.168.10.100:/backup

- 로컬 디렉터리는 /home
- 원격지 서버는 192.168.10.100 이고, 디렉
터리는 /backup 이다.
- 원본파일이 삭제되었다면, 백업본 파일도
삭제한다.
- 퍼미션, 링크, 날짜 등의 모든 정보는 동일
하게 유지 한다.
- 백업 진행사항을 자세히 출력한다.

11 
① /etc/sysconfig/network 4점 
② ypserv 4점 

NIS Master 서버 설정

서버의 재부팅 후에도 NIS 도메인과 호스트네임이 유지되도록 ( ① ) 파일을 수정한다.
[root@ihd ~]# vi ( ① )
-------------------------------------------------------------
NISDOMAIN=ihd.or.kr
HOSTNAME=nis.ihd.or.kr
-------------------------------------------------------------
[root@ihd ~]# service ( ② ) start

12 
① ihdsmb 3점 
② path 3점 
③ valid users 3점 
④ writable 3점 

[ ① ]
( ② ) = /smbfile
( ③ ) = ihduser
( ④ ) = yes

부연설명

[public]                            : 공유 이름
comment = 공유폴더            : 설명
valid user = @users            : 접근을 허용할 그룹
writeable = yes                  : 쓰기 가능 여부
path = /public                    : 공유 경로


13 아파치

① ExtendedStatus 
② SetHandler 
③ Order 
④ Allow from admin.ihd.or.kr 
⑤ AuthConfig 

( ① ) on
<Location /server-status>
( ② ) server-status
( ③ ) deny,allow
Deny from all
( ④ )
</Location>
<Directory /server-status>
AllowOverride ( ⑤ )
</Directory>

웹 서버의 환경 설정 파일
/usr/local/apache/conf/httpd.conf ( 전체 환경 설정, 가상 호스트 설정, 메인 서버 환경 설정
 
아파치 웹 서버 데몬
/usr/local/apache/bin/httpd

14 
① RELAY 2점 
② spam.com 2점 
③ OK 2점 
④ DISCARD 2점 
15 
① no 4점 
② access_times 4점 
16 
① PREROUTING 3점 
② TCP 3점 
③ --dport 또는 --destination-port 3점 
④ DNAT 3점

정보통신기술자격(IHD.CP)검정시험 - 제1402회 리눅스마스터 1급 2차 시험 1 / 6 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
※ 다음 사항을 확인하신 후 시험을 시작하시기 바랍니다. 
○ 본 문제지는 총 6페이지이며, 16문제(단답식 : 1번～10번, 
작업식 : 11번～16번)로 구성되어 있습니다. 
페이지와 문제수가 맞는지 확인하시기 바랍니다. 
○ 과목별 문제수 및 문제당 배점 
- 단답식 : 10문제 × 4점 = 40점 
- 작업식 : 6문제 × 4～12점 = 60점 
○ 합격기준 
- 합계 60점 이상 
○ 답안지는 반드시 검정색 볼펜을 사용하여야 합니다. 
(검정색 이외의 필기구 및 연필 등 지우개로 지울 수 
있는 필기구를 사용할 경우 오답처리 됩니다.) 
- 답안지에 수검번호, 주민번호, 성명을 기재하여 주십 
시오. 
※답안지에 기재 오류시 발생되는 불이익은 수검자의 
책임으로 합니다. 
단답식(1-10) 
1. 그룹인 ihdg 및 일반 사용자 계정인 ihd에 
대한 관리 작업을 다음과 같이 실행하려고 
한다. 다음 ( 괄호 ) 안에 알맞은 명령어를 
적으시오. 
① 그룹 ihdg의 GID를 700번으로 생성하는 명령어를 
완성하시오. 
[root@ihd ~]# ( ① ) -g 700 ihdg 
② ihd의 그룹 아이디를 800번으로 변경하는 명령어를 
완성하시오. 
[root@ihd ~]# ( ② ) -g 800 ihd 
2. A회사에서 운영하던 리눅스 시스템들은 백업을 
로컬 DISK 에 용량을 할당하여 운영 중이다. 
1년간 운영한 해당 시스템은 공간이 부족 
하여 새롭게 DISK를 증설하여 용량을 확보 
하여야 한다. 다음과 같이 작업을 수행하는 
경우 아래 조건을 참조하여 ( 괄호 ) 안에 
알맞은 명령어를 적으시오. 
■ 조 건 
- 기존 백업의 위치는 /backup2013 이다. 
- 신규 백업의 위치는 /backup2014 이며, 
새롭게 추가된 하드디스크 전체를 할당하여 
사용하고자 한다. 
- 추가된 하드디스크의 장치명은 /dev/sdc 이다. 
- 명령어 또는 파일명은 절대경로를 포함하여 
작성한다. 
① ( ① ) /dev/sdc : 디스크 파티션을 만든다. 
② ( ② ) /dev/sdc1 : 파티션을 ext4 파일시스템 
으로 생성한다. 
③ mkdir /backup2014 : 마운트 포인트를 생성한다. 
④ mount -( ③ ) ext4 /dev/sdc1 /backup2014 : 
파티션(/dev/sdc1)을 /backup2014 디렉토리에 
마운트한다. 
3. 다음은 시스템의 프로세스 정보, 메모리 사용량, 
IO상태, CPU사용률 등의 정보를 출력한다. 
해당 명령어를 이용하여 매일 23시 30분에 
1초 단위로 10회씩 /var/log/check.log 파일로 
누적되어 저장되도록 명령어를 적으시오. 
다음은 해당 명령어를 실행했을 때의 예시이다. 
----------------------------------------------------------------- 
procs---------memory-------- --swap-- --io-- -system- ---cpu---- 
r b swpd free buff cache si so bi bo in cs us sy id wa st 
0 0 0 109740 127888 239684 0 0 1 1 8 9 0 0 100 0 0 
0 0 0 109616 127888 239684 0 0 0 0 78 144 0 0 100 0 0 
----------------------------------------------------------------- 
[root@ihd ~]# ( ① ) -e 
---------------------------------------------------- 
30 23 * * * ( ② ) 1 10 ( ③ ) /var/log/check.log 
----------------------------------------------------

정보통신기술자격(IHD.CP)검정시험 - 제1402회 리눅스마스터 1급 2차 시험 2 / 6 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
4. 시스템 운영자는 웹서비스를 제공하기 위하여 
RPM이 아닌 소스 파일을 이용하여 직접 
컴파일을 하고자 한다. 다음 ( 괄호 ) 안에 
알맞은 내용을 적으시오. 
[root@ihd src]# ( ① ) zxvf httpd-2.2.34.tar.gz 
[root@ihd src]# cd httpd-2.2.24 
[root@ihd httpd-2.2.24]# ./( ② ) --( ③ ) 
=/usr/local/httpd --( ④ )-modules=so 
[root@ihd httpd-2.2.24]# make 
[root@ihd httpd-2.2.24]# make install 
■ 조 건 
- 다운로드된 위치 : /usr/local/src 
- 설치할 위치 : /usr/local/httpd 
5. 시스템 관리자인 홍길동은 커널을 직접 컴파일 
하여 시스템을 운영하고자 한다. 다음 커널 
컴파일에 대한 명령어를 적으시오. 
① 커널 컴파일 시에 문제가 되는, 이전에 생성 
되어 있던 오브젝트 파일(*.o)들을 삭제(정리) 
하고 모든 설정과 커널의 소스를 초기 상태로 
돌리기 위해 사용하는 명령어를 쓰시오. 
② 커널 컴파일을 위한 커널 옵션 설정은 텍스트 
문답 방법, 메뉴 형식의 방법, 확장된 메뉴 형식의 
방법, X윈도우 형식의 방법이 있다. 이 중 텍스트 
문답 방법의 명령어를 쓰시오. 
③ 커널 컴파일 설정 이후의 과정을 완성하시오. 
# make clean 
# make ( ) : 커널 생성(bzip2 형식) 
# make modules 
# make modules_install 
6. 다음은 ISO 이미지 파일을 /media 에 마운트 
하는 명령어이다. ( 괄호 ) 안에 알맞은 내용을 
적으시오. 
[root@ihd ~]# mount ( ① ) ( ② ) 
linux-server-x86_64-dvd.iso /media/ 
7. 다음은 logrotate.conf 파일의 내용이다. ( 괄호 ) 
안에 알맞은 내용을 적으시오. 
# see "man logrotate" for details 
# rotate log files weekly 
( ① ) 
# keep 4 weeks worth of backlogs 
rotate ( ② ) 
# create new (empty) log files after rotating old ones 
create ( ③ ) 
# uncomment this if you want your log files compressed 
#compress 
■ 조 건 
- 로그 파일을 월 단위로 rotate 하며, 백업 
로그는 6개로 유지하고, 생성된 로그파일의 
퍼미션을 rw-r--r-- 으로 지정한다. 
8. 다음은 로그에 관련된 내용이다. ( 괄호 ) 
안에 알맞은 내용을 적으시오. 
시스템의 접속에 관한 보안 로그파일인 ( ① )은 
시스템의 불법 침입이 의심이 될 때 확인하는 
로그이고, 시스템에 관련된 중요한 이벤트들은 
모두 ( ② )파일에 기록된다. 
■ 조 건 
- 로그들의 위치는 /var/log 디렉터리안에 
존재한다. 
- 절대경로로 표기하지 말고, 파일명만 
적으시오.

정보통신기술자격(IHD.CP)검정시험 - 제1402회 리눅스마스터 1급 2차 시험 3 / 6 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
9. 다음은 패스워드 관리(login.defs)에 대한 
설정이다. ( 괄호 ) 안에 알맞은 내용을 적으시오. 
PASS_MIN_LEN ( ① ) 
( ② ) ( ③ ) 
■ 조 건 
- 패스워드 변경없이 사용가능한 기간을 90일로 
지정한다. 
- 패스워드 길이는 9 자리로 지정한다. 
10. 다음은 rsync을 이용하여 원격지 서버로 
백업을 하려고 한다. ( 괄호 ) 안에 알맞은 
내용을 적으시오. 
# rsync ( ① ) ( ② ) ( ③ ) /home 
192.168.10.100:/backup 
■ 조 건 
- 로컬 디렉터리는 /home 
- 원격지 서버는 192.168.10.100 이고, 디렉 
터리는 /backup 이다. 
- 원본파일이 삭제되었다면, 백업본 파일도 
삭제한다. 
- 퍼미션, 링크, 날짜 등의 모든 정보는 동일 
하게 유지 한다. 
- 백업 진행사항을 자세히 출력한다. 
- 작업식 문제 계속(다음장) -

정보통신기술자격(IHD.CP)검정시험 - 제1402회 리눅스마스터 1급 2차 시험 4 / 6 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
작업식(11-16) 
11. 다음은 NIS Master 서버 설정의 과정이다. 다음 조건에 맞도록 ( 괄호 ) 안에 알맞은 내용을 
작성하시오.(8점) 
■ 조 건 
- 도메인은 ihd.or.kr 이다. 
- 호스트네임은 nis.ihd.or.kr 이다. 
- portmap 관련 데몬은 활성화되어 있다. 
서버의 재부팅 후에도 NIS 도메인과 호스트네임이 유지되도록 ( ① ) 파일을 수정한다. 
[root@ihd ~]# vi ( ① ) 
------------------------------------------------------------- 
NISDOMAIN=ihd.or.kr 
HOSTNAME=nis.ihd.or.kr 
------------------------------------------------------------- 
[root@ihd ~]# service ( ② ) start 
12. 삼바(Samba) 서비스를 이용하여 디렉터리를 공유하고자 smb.conf 파일을 수정하려고 한다. 
다음 조건에 맞도록 ( 괄호 ) 안에 알맞은 내용을 작성하시오.(12점) 
. 조 건 
- 공유명은 ihdsmb 이다. 
- 공유하려는 디렉터리 위치는 /smbfile 이다. 
- 현재 /smbfile 디렉터리의 소유자는 ihduser 이다. 
- 공유된 디렉터리가 ihduser 사용자에 대해서만 읽고 쓰기가 가능하다. 
[ ① ] 
( ② ) = /smbfile 
( ③ ) = ihduser 
( ④ ) = yes

정보통신기술자격(IHD.CP)검정시험 - 제1402회 리눅스마스터 1급 2차 시험 5 / 6 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
13. 관리자인 홍길동은 운영중인 웹 서버(아파치 2.x)를 웹브라우저를 통해 서버의 실행에 대한 
모니터링을 하려고 한다. 다음 ( 괄호 ) 안에 알맞은 내용을 작성하시오.(12점) 
. 조 건 
- 관리자 PC 인 admin.ihd.or.kr 에서만 정보를 볼 수 있어야 한다. 
- 웹브라우저에서는 http://서버주소/server-status로 접근되어야 한다. 
- 사용모듈은 mod_info.c 이며, 웹페이지 인증을 통해 접근이 되어야 한다. 
( ① ) on 
<Location /server-status> 
( ② ) server-status 
( ③ ) deny,allow 
Deny from all 
( ④ ) 
</Location> 
<Directory /server-status> 
AllowOverride ( ⑤ ) 
</Directory> 
14. 다음은 한 회사 시스템 관리자의 메일 송수신 설정을 위한 내용이다. 관리자는 로컬 네트 
워크 사용자의 메일을 이 서버를 통해 보내고 받고, 그 외의 사용자는 아래 조건에 맞게 
설정하고자 할 때 ( 괄호 )안에 알맞은 내용을 작성하시오.(8점) 
localhost.localdomain RELAY 
localhost ( . ) 
( . ) REJECT 
admin@ihd.or.kr ( . ) 
spam@hacker.com ( . ) 
■ 조 건 
- spam.com이라는 도메인의 모든 메일을 수신/발신을 거부한다. 
- ihd.or.kr의 사용자 admin만 무조건 수신을 허용한다. 
- spam@hacker.com에서 오는 메일을 받아 완전히 폐기한다.

정보통신기술자격(IHD.CP)검정시험 - 제1402회 리눅스마스터 1급 2차 시험 6 / 6 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 
15. 다음은 xinetd 데몬으로 동작하는 rsync 데몬에 대한 설정이다. 다음 ( 괄호 ) 안에 알맞은 
내용을 작성하시오.(8점) 
service rsync 
{ 
disable = ( ① ) 
socket_type = stream 
wait = no 
user = root 
server = /usr/bin/rsync 
server_args = --daemon 
log_on_failure += USERID 
( ② ) = 09:00-18:00 
} 
. 조 건 
- rsync 서비스를 활성화 한다. 
- rsync 사용시간을 09시부터 18시 까지로 제한한다. 
16. 다음은 외부로 부터의 접근을 막기 위한 DNAT(Destination NAT) 설정이다. 다음 ( 괄호 ) 
안에 알맞은 내용을 작성하시오.(12점) 
[root@linux] # iptables -t nat .A ( ① ) -p ( ② ) -d 211.111.222.3 ( ③ ) 80 .j ( ④ ) --to 
192.168.1.3 
■ 조 건 
- 공인 목적지 주소는 211.111.222.3 이고, tcp 프로토콜 기반의 80번 포트로 요청이 들어오면 내부 
목적지 주소인 192.168.1.3으로 변경한다. 
- 192.168.1.3 은 내부서버로 웹서비스 중이다. 
※ 다음 사항을 확인하신 후 시험을 종료하시기 바랍니다. 
○ 답안지는 검정색 볼펜으로 작성하셨습니까? 
○ 답안지 및 문제지에 수검번호(뒷자리 6자리), 생년월일(6자리), 성명을 정확히 기재하셨습니까? 
○ 답안지에 문제에 대한 답안을 모두 기입하셨습니까? 
- 수고하셨습니다. -

