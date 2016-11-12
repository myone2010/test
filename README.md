1 

명령어 설 명
( ① )
유효 사용자 아이디(Effective User ID)의
정보를 확인하는 명령이다.
( ② )
시스템에 접속할 당시의 계정명과 접속
정보를 확인하는 명령이다.
( ③ )
현재 시점에서 시스템을 사용하고 있는
내가 누구인가에 대한 자세한 정보를
보여준다. 사용자 아이디, 그룹아이디,
소속 그룹 정보 등을 확인할 수 있다

① whoami
② who am I
③ id 

2 

# ls -ld exam_dir
drwxr-xr-x. 2 tux penguins 21 May 2 22:44 exam_dir
# ls -l exam_dir/exam.txt
-rw-r--r--. 1 tux penguins 0 May 2 22:44 exam_dir/exam.txt
# ( ① )
# ( ② )
# ls -ld exam_dir
drwxrwx---. 2 super users 21 May 2 22:44 exam_dir
# ls -l exam_dir/exam.txt
-rwxrwx---. 1 super users 0 May 2 22:44 exam_dir/exam.txt

소유자와 소유그룹에는
모든 권한을 할당하고, 다른사용자계층에
어떠한 권한도 부여하지 않으려고 한다.

① chown -R super.users exam_dir 
 
② chmod -R 770 exam_dir 


- 2개의 명령에 옵션을 이용하여 소유권 및
허가권을 변경한다.
- 소유권은 tux에서 super로 변경한다.
- 소유그룹은 penguins에서 users로
변경한다.
- 허가권 변경의 옵션은 숫자 모드를
사용한다.

3 
매주 월요일부터 금요일까지에 실행되고,
오전 9시부터 오후 6시까지 5분 간격으로
자동으로 수행되게 설정한다.

*/5 9-18 * * 1-5 /services/health_check.sh 


4 
① -c 
② -o program 

5 

( ① )란 물리적으로 데이터가 저장되는 둥근 원판을
말한다. 전원이 켜지면 ( ① )는 쉬지 않고 계속해서
회전하면서 ( ② )에 의해 데이터가 저장되고 읽혀진다.
데이터를 기록하고 읽어내는 가장 기본적인 단위는
( ③ )이다. 1 ( ③ )는 512 byte의 데이터 영역과
69byte의 주소코드를 가지고 있다.

① 플래터 
② 헤드 
③ 섹터

6 
부팅 시 자동으로 마운트

vi ( ① )
( ② ) ( ③ ) ( ④ ) ( ⑤ ) 1 1

① /etc/fstab
② /dev/sdb1 
③ /home2 
④ ext4 
⑤ defaults,usrquota 

- 관련 파일명을 절대 경로로 적는다.
- 관련 디렉터리는 /home2이다.
- 장치 파일명은 /dev/sdb1이고, ext4로 파일
시스템을 생성하였다.
- 해당 영역은 기본 설정 옵션 이외에 사용자
디스크 제한이 가능하도록 설정한다.


7 
가. 사용자 접속시 성공한 로그를 기록하는 파일은
( ① )이고, 이 파일은 바이너리 파일로서 ( ② )
라는 명령어로 확인할 수 있다.
나. 사용자 접속시 실패한 로그를 기록하는 파일은
( ③ )이고, 이 파일은 바이너리 파일로서 ( ④ )
라는 명령어로 확인할 수 있다.

8
# vi ( ① )
( ② )
( ③ )
( ④ )

① /var/log/wtmp  
② last 
③ /var/log/btmp 
④ lastb
 
- ① : 관련 파일명을 절대 경로로 적는다.
- ② : 로테이션 주기는 한 달 단위로 설정한다.
- ③ : 로그 파일명에 해당 날짜를 덧붙여서
생성하도록 한다.
- ④ : 로테이션은 최대 5번으로 설정한다.

① /etc/logrotate.conf 1점 
② monthly 1점 
③ dateext 1점 
④ rotate 5 1점 

9

# ( ① ) /var/log/secure
-------------e- /var/log/secure
# ( ② ) ( ③ ) /var/log/secure
# ( ① ) /var/log/secure
-----a-------e- /var/log/secure

① lsattr 
② chattr 
③ +a 

10 

# ( ① ) ( ② )=/dev/sdb1 ( ③ )=/dev/sda1 ( ④ )=1024

① dd 1점 
② of 1점 
③ if 1점 
④ bs 1점

- 백업하려는 대상장치는 /dev/sda1이고,
/dev/sdb1에 보관한다.
- 한 번에 입출력하는 블록 사이즈 단위는
1024byte이다.

11 

vi /etc/fstab
( ① ) ( ② ) ( ③ ) timeo=30,soft,retrans=5 0 0

① data.example.com:/shared
② /remote_data
③ nfs 3점 

- NFS 서버 도메인은 data.example.com이고 공유 디렉터리명은 /shared이다.
- NFS 클라이언트에서 마운트할 디렉터리명은 /remote_data이다.

12 
vi /etc/vsftpd/vsftpd.conf에 있음
# vi vsftpd.conf
( ① ) = 002
( ② ) = 21
( ③ ) = YES

① local_umask 3점 
② listen_port 3점 
③ xferlog_enable 3점 

- ① 파일생성시 적용되는 umask값은 “002"이다.
- ② vsftpd 데몬이 외부 접속 요청에 통신할 ftp 포트는 “21”이다.
- ③ 파일 송수신 로그를 지정된 파일에 저장한다.

13 아파치 웹 2.x 서버
(10점) 

# vi /etc/httpd/conf/httpd.conf
( ① ) 1120
( ② ) webadmin.example.com:1120
( ③ ) “/var/www/html/webadmin”
( ④ ) webadmin@example.com
( ⑤ ) index.php index.html index.htm

① Listen 2점 
② ServerName 2점 
③ DocumentRoot 2점 
④ ServerAdmin 2점 
⑤ DirectoryIndex 2점 

- 웹 서버 포트 번호를 1120으로 변경한다.
- 웹 서버 도메인을 webadmin.example.com으로 설정한다.
- 웹 문서가 위치하는 디렉터리는 /var/www/html/webadmin으로 설정한다.
- 관리자 이메일주소는 webadmin@example.com로 설정한다.
- 클라이언트의 요청에 index.php, index.html, index.htm 순서로 응답하도록 설정한다.


14 
다음은 DNS 서버의 존(zone) 파일 설정이다. 조건에 맞게 ( 괄호 ) 안에 알맞은 내용을

$TTL 1D
          네임서버 관리자이메일 주소
@ IN SOA ( ① ) ( ② ) (
2014051301 ; serial
1D ; refresh
1H ; retry
1W ; expire
3H ) ; minimum
IN NS ( ① ) 네임서버
IN A 192.168.12.22
IN ( ③ ) ( ④ ) MS(메일서버) 0 , 주소값
www IN A 192.168.12.22
www1 IN ( ⑤ ) www 커넥트네임
www2 IN ( ⑤ ) www 커넥트네임 CNAME

- 네임 서버의 주소는 ns.linux.or.kr로 설정한다.
- 관리자 이메일주소는 posein@linux.or.kr로 설정한다.
- 메일 서버는 linux.or.kr로 설정한다.
- 호스트명이 www1 및 www2를 요청했을 경우에는 www로 연결되도록 설정한다.

① ns.linux.or.kr. 2.4점 
② posein.linux.or.kr. 2.4점 
③ MX 0 (0대신에 양의 정수값 모두 가능) 2.4점 
④ linux.or.kr. 2.4점 
⑤ CNAME 2.4점 


15 

# vi /etc/hosts.deny
ALL: ALL
# vi /etc/hosts.allow
( ① ): 192.168.6.7
( ② ): ( ③ )

① in.telnetd 4점 
② vsftpd 4점 
③ 192.168.12.


- 텔넷서비스는 호스트의 IP 주소가 192.168.6.7만 허가한다.
- FTP 서비스는 192.168.12.0 네트워크 대역의 호스트만 허가한다.
- FTP 서버는 vsftpd를 사용한다.


16 iptables 정책을 저장하는 과정

가. 관련 명령어를 사용한 정책 저장 및 반영
# ( ① ) > firewall.sh
# ( ② ) < firewall.sh
나. 관련 스크립트를 이용한 저장과 설정된 정책 확인
# service iptables ( ③ )
# cat ( ④ )
 
① iptables-save 2점 
② iptables-restore 2점 
③ save 2점 
④ /etc/sysconfig/iptables 2점


- ① : iptables로 설정된 정책을 파일로 저장하는 명령어를 적는다.
- ② : 파일에 저장된 iptables 정책을 불러들여서 설정하는 명령어를 적는다.
- ③ : iptables 정책을 저장하는 인자값(argument)를 적는다.
- ④ : 관련 스크립트에 의해 정책이 저장되는 파일명을 절대경로로 기재한다.


1 

# cat ( ① )
HOME=/home
INACTIVE=-1
EXPIRE=
SHELL=/bin/bash
SKEL=( ② )

- 사용자 생성 시에 참고하는 설정 파일의
절대경로를 적으시오.
- 사용자 생성 시에 제공되는 파일 목록이
들어 있는 디렉터리를 절대경로로 적으시오.

① /etc/default/useradd 2점 
② /etc/skel 2점 


2 리눅스에서 파일시스템을 검사

# umount /dev/sdb1
# fsck ( ① ) ( ② ) ext4 /dev/sdb1

① -N 2점 어떻게 할건지만 알려줌
② -t 2점 파일검사할 디렉토리

HUP(Hangup) 시그널을
무시하고 해당 프로그램이 지속적으로 실행

# ( ① ) tar cvf home.tar /home ( ② )

① nohup 2점 
② & 2점 


4 --rebuilddb 4점 

- RPM 패키지를 관리해주는 데이터베이스를
다시 작성한다.

5

# ( ① ) igb
# lsmod
Module Size Used by
igb 23872 1
# vi ( ② )
alias eth0 e1000
 
① modprobe 또는 insmod 2점 
② /etc/modprobe.conf


6 
① 83 [Linux]
1개:2점 
2개:3점 
3개:4점 
② 82 [Linux swap / Solaris]
③ 83 

8e LVM

7 

# cat /etc/( ① )
authprive.* /var/log/secure
mail.* /var/log/maillog
*.emerg *
( ② ) /var/log/warn.log

① rsyslog.conf
② *.warn

① : syslogd 데몬의 주 설정 파일이다.
② : 모든 메세지 종류 중 warning 이상의 레벨
메세지가 /var/log/warn.log 파일에 기록
으로 남긴다.

8 

/var/log/messages {
( ① )
create ( ② ) root root
( ③ ) 5
}

① weekly 
1개:2점 
2개:3점 
3개:4점 
② 0600 
③ rotate 

- messages 파일의 순환주기를 1주일로 한다.
- 실행권한을 0600로 하며, root 소유권을
가지고 root 그룹에 소속된다.
- 관련 파일의 생성은 최대 5개로 제한한다.

9 nosuid 4점 

# mount -o ( ① ) /dev/sdb1 /home

- SetUID/SetGID 파일들이 존재하는 홈 디렉
터리에 SetUID/SetGID 비트가 동작하지
않도록 원천 봉쇄할 수 있는 마운트 옵션
이다.

10 

rsync ( ① ) ( ② ) ( ③ ) /home
192.168.10.100:/backup

① --delete 
② -a [유지]
③ -v [자세히]

- 로컬 디렉터리는 /home
- 원격지 서버는 192.168.10.100 이고, 디렉
터리는 /backup 이다.
- 원본파일이 삭제되었다면, 백업본 파일도
삭제 한다.
- 퍼미션, 링크, 날짜 등의 모든 정보는 동
일하게 유지 한다.
- 백업 진행사항을 자세히 출력한다.

11 
(9점) 
① ServerName 3점 
② ServerRoot 3점 
③ DocumentRoot 3점 

Listen 80
( ① ) www.ihd.or.kr
( ② ) “/usr/local/apache”
( ③ ) “/www”

- 웹서버의 도메인은 www.ihd.or.kr 이다.
- 웹서버의 설치 디렉터리는 /usr/local/apache 이다.
- 서버의 인덱스 페이지가 위치하는 곳은 /www 이다.

12 NFS 서버

/etc/exports
( ① ) 192.168.10.10( (②), (③) )

① /data/nfs 3점 
② rw 3점 
③ root_squash 3점 
클라이언트에서 루트를 서버상에 nobody 사용자로 매핑 한다.

13 

vsftpd.conf
( ① ) = 21
( ② ) = 022
ftp_data_port = ( ③ )

① listen_port 4점 
② local_umask 4점 
③ 20 4점 

14 

(3) 서비스 데몬 실행
# service ( ① ) start
(4) 네트워크 설정(네트워크 브리지 설정 포함)
(5) 가상머신 생성 및 게스트 OS 설치
# ( ② )
① libvirtd 3점 
② virt-manager 3점
 
15 

# cat ntp.conf
( ① ) nomodify notrap
( ② )
( ③ )
# service ( ④ ) start
 
① restrict 192.168.0.0 mask 255.255.255.0 3점 
② server time.kriss.re.kr 3점 
③ server time.bora.net 3점 
④ ntpd 3점 

- ① : NTP 서버 요청을 허용할 네트워크 대역을 192.168.0.0/255.255.255.0으로 설정한다.
- ② : NTP 서버에서 시간 정보를 time.kriss.re.kr로 요청한다.
- ③ : NTP 서버에서 시간 정보를 time.bora.net으로 요청한다.
- ④ : NTP 서비스 데몬을 시작한다.

16 

- iptables 명령어를 수행하는 서버의 IP는 192.168.10.1이다.
- INPUT 체인의 기본 정책은 DROP 이다.
- ① : 프로토콜은 icmp이며 icmp echo request 패킷이 외부로 나가는 것에 대해 허용한다.
- ② : 프로토콜은 icmp이며 외부에서 들어오는 icmp echo reply 패킷에 대해서 허용한다.
- ③ : 프로토콜은 icmp이며 외부에서 들어오는 icmp destination-unreachable 패킷에
대해서 허용한다.

① -p icmp --icmp-type echo-request
② -p icmp --icmp-type echo-reply
③ -p icmp --icmp-type destination-unreachable


 /boot/grub/grub.conf 
1 
# useradd ( ① ) sysadmin test7
# usermod ( ② ) /bin/sh ( ③ ) admin test7

① -G (--groups) 
② -s (--shell) 
③ -G 

2 

# fdisk /dev/sda
Command (m for help): ( ① )
Partition number (1-6): 5
Hex code (type L to list codes): ( ② )

① t 2점 
② 8e 2점 


3

# ps -l
F S UID PID PPID C PRI NI ADDR SZ WCHAN TTY TIME CMD
4 S 501 4305 4304 0 75 0 - 1350 wait4 pts/0 00:00:00 bash
# ( ① ) ( ② ) 4305
 
① renice 2점 
② 10


4 
# rpm -Uvh vsftpd.2.4.0-2.src.rpm
# ( ) -ba vsftpd.spec

rpmbuild 

5 
다음은 GRUB에 대한 내용이다. ( 괄호 )
안에 알맞은 내용을 적으시오.

grub-install (--recheck)

6 

# mkdir /backup
# mount -t ext3 /dev/sdb1 /backup
# vi /etc/fstab
( ① ) ( ② ) ( ③ ) defaults 1 2


① /dev/sdb1  
② /backup 
③ ext3 

7 

( ) 파일에는 시스템이 부팅 할 때 보이는
시스템 정보 메시지들이 기록된다. 따라서 시스템 부팅시
이상한 메시지가 나오면 이 파일을 보고 확인이 가능
하다. 일반적으로 커널 정보, 콘솔, CPU, 메모리, 각
장치 정보 등이 출력된다.

/var/log/dmesg

8 

( ① ) ( ② ) ( ③ ) ( ④ ) ( ⑤ ) root /etc/backup.sh

① 0 또는 00 분
② 4 또는 04 시
③ * 일
④ * 월
⑤ 1,3,5 또는 mon,wed,fri 

9 /etc/grub.conf

timeout=( ① )
splashimage=(hd0,0)/grub/splash.xpm.gz
hiddenmenu
( ② ) -md5 $1NmiJ1$5tumUAi5FlupA3Msu1m.
title Linux Server (2.6.18-308.el5)
root (hd0,0)
kernel /vmlinuz-2.6.18-308.linux ro
root=/dev/VolGroup00/LogVol00 rhgb quiet
initrd /initrd-2.6.18-308.linux.img

① 10 2점 
② password 2점 

10 

# cd /home
# tar cvf( ① ) /backup/backup_` ( ② )`.tar.gz .

① z 
② date +%m%d

- ① : 백업 파일이 생성될 때 압축을 한다.
(압축은 gzip를 사용한다.)
- ② : /backup 디렉터리안에 백업 파일이
생성 되어야 하며 backup_<오늘날짜>
.tar.gz 파일이 생성되어야 한다.
(예: /backup/backup_0513.tar.gz)

11 
order ( ① ), ( ② )
allow from .example.com
deny from ( ③ )
① allow 3점 
② deny 3점 
③ all 3점 

- example.com 도메인을 제외한 모든 도메인으로부터 접근을 거부한다.

12 

/etc/openldap/slapd.conf
suffix "dc=( ① ), dc=( ② )
rootdn "cn=Manager,dc=( ① ),dc=( ② )"

① ihd 3점 
② org 3점 
13 
(9점) 

# vi ( ① )
admin@linux.co.kr posein
admin@windows.co.kr yuloj
# ( ② ) ( ① ) < ( ① )

① /etc/mail/virtusertable 4.5점 
② makemap hash 4.5점 


14 

$TTL 86400
@ IN SOA ns.example.com. root.example.com. (
20150426
( ① )
( ② )
( ③ )
1D
)
example.com. IN NS ns.example.com.
ns IN A 192.168.0.100

- ① : 보조 네임서버가 주 네임서버에 접속하는 시간은 3시간이다.
- ② : 접속 실패 시 다시 시도할 시간 간격은 15분이다.
- ③ : 주 네임서버에 데이터가 없다면 1주 이후에 지워진다.

① 3H
② 15M
③ 1W


15 
ddns-update-style interim;
ignore client-updates;

subnet 192.168.0.0 netmask 255.255.255.0 {
option ( ① );
option ( ② );
option ( ③ );
option ( ④ );
option time-offset -18000;
option default-lease-time 21600;

① routers 192.168.0.1 3점 
② subnet-mask 255.255.255.0 3점 
③ domain-name “example.com” 3점 
④ domain-name-servers 192.168.1.1 3점 

- ① : DHCP 클라이언트에게 할당되는 게이트웨이 정보는 192.168.0.1 이다.
- ② : DHCP 클라이언트에게 할당되는 서브넷 마스크 정보는 255.255.255.0 이다.
- ③ : DHCP 클라이언트에게 할당되는 도메인 네임은 example.com 이다.
- ④ : DHCP 클라이언트에게 할당되는 도메인 네임 서버 IP 주소는 192.168.1.1이다.

16 
(12점) 

- 패킷은 거부 메시지 없이 무조건 거절한다. (DROP)
- 두 번째 이더넷카드(eth1)로 들어오는 패킷인 경우에만 포워딩을 허가한다.
- 어떠한 방화벽도 설정되어 있지 않고 커널에서 포워딩을 허가한 상태이다.

# iptables ( ① ) FORWARD DROP
# iptables ( ② ) FORWARD ( ③ ) eth1 ( ④ ) ACCEPT

① -P 3점 
② -A 3점 
③ -i 3점 
④ -j 3점


1
① groupadd [GID 생성 -g 옵션]
② usermod [그룹아이디 변경 -g 옵션]

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
② vmstat [1 10 1초 단위로 10회씩]
③ >> 

( ① ) -e
30 23 * * * ( ② ) 1 10 ( ③ ) /var/log/check.log

4 
① tar
② configure
③ prefix
④ enable

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
① -o 
② loop 
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
② -a, (--archive) 
③ -v, (--verbose) 


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


13 아파치 2.x

① ExtendedStatus 
② SetHandler 
③ Order 
④ Allow from admin.ihd.or.kr 
⑤ AuthConfig 

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
---------------------------------
웹 서버의 환경 설정 파일
/usr/local/apache/conf/httpd.conf
/etc/httpd/conf/httpd.conf

아파치 웹 서버 데몬
/usr/local/apache/bin/httpd

httpd.conf
Listen        : 특정 IP 주소 또는 포트에 연결이 가능하도록 해준다.
DocumentRoot        : 제공할 문서의 상위 디렉토리. 모든 요청은 이 디렉토리로부터 처리된다.
allow from        : 나열되는 주소들에 대한 접근을 가능하도록( all )
deny from        : 나열되는 주소에 대한 접근이 불가하도록 ( all )
DirectoryIndex        : 디렉토리의 파일들을 순서대로 보여줄 때 파일명 들을 나열한다.
<IfModule mod_include.c>        : 명시된 모듈의 상태를 확인.
UserDir    disable            : http://도메인/~계정 형식으로의 접석을 허용치 않을 시
UserDir    public_html        : 기본적으로 http 서버가 읽어들일 디렉토리명
</IfModule>
------------------------------------
14 송수신메일

localhost.localdomain RELAY
localhost ( 1 )
( 2 ) REJECT
admin@ihd.or.kr ( 3 )
spam@hacker.com ( 4 )

① RELAY 2점 
② spam.com 2점 
③ OK 2점 
④ DISCARD 2점 

- spam.com이라는 도메인의 모든 메일을 수신/발신을 거부한다.
- ihd.or.kr의 사용자 admin만 무조건 수신을 허용한다.
- spam@hacker.com에서 오는 메일을 받아 완전히 폐기한다.

15 
rsync 데몬
① no 4점 
② access_times 4점 

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

- rsync 서비스를 활성화 한다.
- rsync 사용시간을 09시부터 18시 까지로 제한한다.

16 

조 건
- 공인 목적지 주소는 211.111.222.3 이고, tcp 프로토콜 기반의 80번 포트로 요청이 들어오면 내부
목적지 주소인 192.168.1.3으로 변경한다.
- 192.168.1.3 은 내부서버로 웹서비스 중이다.

iptables -t nat ?A ( ① ) -p ( ② ) -d 211.111.222.3 ( ③ ) 80 ?j ( ④ ) --to
192.168.1.3

① PREROUTING 3점 
② TCP 3점 
③ --dport 또는 --destination-port 3점 
④ DNAT 3점




1 

[root@ihd ~]# useradd -u ( ① ) -g ihdg -G
support -( ② ) /bin/bash -( ③ )
2015-12-30 ihd

① 520 
② s 
③ e 

- 로그인 아이디 : ihd
- UID : 520
- 소속될 그룹 : ihdg(기본 그룹, GID : 500),
support(GID : 501)
- 기본 쉘(Shell) : /bin/bash
- 계정사용 종료일 : 2015년 12월 30일

2 
LVM (Logical Volume Manager)을 통하여 생성하고자 한다. 파티션
디바이스의 /dev/sdb1에 10G, /dev/sdb2에
10G를 이용하여 20G의 /data 디렉토리를
생성하는 과정

(1) PV (Physical Volume) 생성
[root@ihd ~]# ( ① ) /dev/sdb1 /dev/sdb2
(2) VG (Volume Group) 볼륨 그룹 생성
[root@ihd ~]# ( ② ) ihd_vg /dev/sdb1 /dev/sdb2
(3) LV (Logical Volume) 생성
[root@ihd ~]# ( ③ ) -( ④ ) 20G ihd_vg
-( ⑤ ) data

① pvcreate 
② vgcreate 
③ lvcreate 
④ L 
⑤ n [or -name]


3 

(1) ( ① )는 리눅스 시스템의 전반적인 운용상황을
실시간으로 모니터링하거나 프로세스 관리를 할
수 있도록 사용하는 유틸리티이다. 아래는 ( ① )을
실행하면서 옵션으로 “a : 메모리 사용에 따라
정렬”, “H : 모든 개별 쓰레드가 보여짐”의 옵션을
이용하여 출력한 상태이다. 또한, 프로그램을 실행한
후에 모든 CPU의 상황을 보기위하여 명령어
“( ② )”을 수행한 후의 화면이다.

PID USER PR NI VIRT RES SHR S %CPU %MEM TIME+ COMMAND
2322 root 20 0 188m 35m 1716 S 0.0 0.2 0:00.06 glusterfs
2323 root 20 0 188m 35m 1716 S 0.0 0.2 0:00.00 glusterfs
2336 root 20 0 188m 35m 1716 S 0.0 0.2 0:00.00 glusterfs

(2) PID가 2322, 2323인 두 개의 프로세스를 무조건
중지시키기 위해 명령어 kill 을 한번만 이용하여
완성하시오.

[root@ihd ~]# kill ( ③ ) 2322 2323
(3) 시스템의 모든 프로세스들을 트리(tree)구조로 확인
할 수 있는 명령어는 ( ④ ) 이다.


① top 
② 1  
③ -9
④ pstree 

4 

(1) 설치된 httpd 패키지 중에 초기 설치시와 다른
점이 있는지를 검사하고자 한다.
# rpm -( ① ) httpd
S.5....T. c /etc/httpd/conf/httpd.conf
(2) (1)의 실행 결과에서 변경된 항목은 ( ② ),
MD5 체크섬, 갱신일 이다.
(3) httpd 패키지에 의해 설치된 파일 목록을 보려고
한다.
# rpm -( ③ ) httpd

① V or -verify  
② 파일 크기 or 파일 사이즈 
③ ql 

5 

(1) 모듈의 로드를 위한 명령어는 ( ① ) 이다.
(2) 커널과 커널 모듈을 컴파일하여 설치한 후에 모듈
사이의 의존성을 검사하고 커널과 모듈 간의 의존성을
갖도록 하기 위한 명령어는 ( ② ) 이다.


① modprobe or insmod 2점 
② depmod 2점 


6 

root@ihd ~]# fdisk -l

Device Boot Start End Blocks Id System
/dev/sda1 * 1 13 104391 ( ① ) Linux
/dev/sda2 14 1305 10377990 ( ② ) Linux LVM
① 83 2점 
② 8e 2점 


7 

none : 그에 대한 모든 로그 메시지 무시
( ① ) : 정보 메시지
( ② ) : 경고 메시지
error : 에러 메시지
emerg : 시스템 패닉

① info 
② warn 

8 

(1) 시스템이 부팅할 때 보이는 서비스 데몬들의 부트에
관련된 정보가 기록되는 파일
(2) 시스템이 부팅할 때 보이는 시스템 정보 메시지 파일
(3) 시스템에 사용자가 원격접속 및 원격 로그인 등
인증관련 정보를 기록하는 파일

① boot.log 
② dmesg 
③ secure 

- 로그파일은 /var/log 디렉토리에 위치함.

9 vi /boot/grub/grub.conf 보면알게됨

timeout=( ① )
splashimage=(hd0,0)/grub/splash.xpm.gz
hiddenmenu
( ② ) -md5 $1NmiJ1$5tumUAi5FlupA3Msu1m.
title Linux Server (2.6.18-308.el5)
root (hd0,0)
kernel /vmlinuz-2.6.18-308.linux ro
root=/dev/VolGroup00/LogVol00 rhgb quiet
initrd /initrd-2.6.18-308.linux.img

- 부트로더 접근시간을 10 초로 제한 한다.
- 부트로더 접근시 패스워드 인증을 한다.

① 10 2점 
② password 2점 


10

다음은 dd를 이용하여 디스크를 복제하려고
한다. 다음 조건에 맞는 백업 명령어를
적으시오.
■ 조 건
- 입력 디바이스는 /dev/sda 이다.
- 출력 디바이스는 /dev/sdc 이다.
- 한번에 입출력하는 블록 사이즈 단위는
1024 byte 이다.
 
dd if=/dev/sda of=/dev/sdc bs=1024 (bs=1024 대신 cbs=1024 인정) 
    인풋 파일 아웃풋 파일  블록사이즈

11 

- 포트는 8080 으로 변경한다.
- 웹 서버의 도메인을 www.ihd.or.kr로 변경한다.
- 웹 문서가 위치하는 디렉토리를 “/var/www/html"로 변경한다.
- 관리자 이메일주소는 admin@ihd.or.kr로 변경한다.
- 클라이언트의 요청에 index.jsp, index.html, index.htm 순으로 응답하도록 설정한다.

# vi /etc/httpd/conf/httpd.conf
( ① ) 8080
ServerName ( ② )
( ③ ) "/var/www/html"
ServerAdmin ( ④ )
( ⑤ ) index.jsp index.html index.htm


① Listen 3점 
② www.ihd.or.kr
③ DocumentRoot 3점 
④ admin@ihd.or.kr 3점 
⑤ DirectoryIndex 3점 


12 NFS 서버 /etc/exports 

- NFS 서버의 호스트 이름은 ihd_nfs 이다.
- /nfsdata 디렉토리는 특정 네트워크 (192.168.100.0)에서만 접근이 가능하도록 하고,
/nfsbackup 디렉토리는 특정 호스트 (192.168.100.10)에서만 접근이 가능하게 한다.
클라이언트에서 접근하는 root 사용자를 root 권한으로 허가되도록 설정한다. 또한, 파일
생성 및 삭제도 가능하도록 설정한다.

모든 클라이언트는 읽기, 쓰기가 가능하며, 클라이언트 (192.168.100.10)는 타임아웃
시간을 2.5초로 설정한다.

(1) 서버
# vi /etc/exports
/nfsdata 192.168.100.0(rw,( ① ))
/nfsbackup 192.168.100.10(rw,( ① ))

(2) 클라이언트 (192.168.100.20)
# vi /etc/fstab
ihd_nfs:/nfsdata /data nfs rw 0 0

(3) 클라이언트 (192.168.100.10)
# vi /etc/fstab
ihd_nfs:/nfsbackup /backcup nfs rw,( ② )=25 0 0

참고
/etc/exports 파일에 설정하는 옵션중에 root를 포함하여 모든 사용자의 권한을 nobody(또는 nfsnobody) 권한으로 변경할 때 사용하는 옵션

all_squash

root_squash : 클라이언트의 root를 서버의 nobody 사용자로 매핑
no_root_squash : 클라이언트의 root와 서버의 root를 동일하게 설정
all_squash : 모든 사용자의 권한을 nobody로 권한으로 변경
no_all_squash : 서버와 클라이언트 사용자가 하나의 권한을 가짐

 
① no_root_squash 4점 
② timeo 4점 

13

시스템관리자는 sendmail을 이용하여 메일서비스를 운영하고자 한다. 다음 조건에 맞도록
sendmail을 적으시오.(9점)
■ 조 건
- 모든 호스트에 대해서 SMTP포트(TCP/25)를 리스닝 하도록 설정한다.
- 192.168.100.xxx 의 모든 ip의 Relay를 허용한다.

# vi /etc/mail/( ① )
DAEMON_OPTIONS ('Port=smtp, Name=MTA') dnl <- 수정
# ( ② ) /etc/mail/sendmail.mc > /etc/mail/sendmail.cf
# vi /etc/mail/access
localhost RELAY
127.0.0.1 RELAY
( ③ ) RELAY
  
① sendmail.mc 
② m4 
③ 192.168.100 


14 DNS zone 파일 /etc/named.conf 

$TTL 86400
@ IN SOA ns.linux.co.kr. root.linux.co.kr. (
42 ; serial (d. adams)
3H ; refresh
15M ; retry
1W ; expiry
1D ) ; minimum
IN NS ns.linux.co.kr.
IN ( ① ) 10 mail.linux.co.kr.
IN A 192.168.10.11
( ② ) IN A 192.168.10.12
mail IN A 192.168.10.( ③ )

- 메일 서버의 주소는 192.168.10.13 이다.
- 192.168.10.12 는 www 도메인 IP 이다.

(12점) 
① MX 4점 
② www 4점 
③ 13 4점 

15 가상머신 KVM
[root@linux]# service ( ① ) start
[root@linux]# ( ② )

① libvirtd 4점 
② virt-manager 4점 

16 

(8점) 
① -P 4점 
② FORWARD 4점

iptables ( ① ) ( ② ) DROP

- 패킷은 거부 메시지 없이 무조건 거절한다. (DROP)
- 어떠한 방화벽도 설정되어 있지 않다.


1 

# groupadd ( ① ) ( ② ) white
# groupmod ( ③ ) ( ④ ) white

- white그룹을 생성하면서, 그룹ID를 555로
지정한다.
- white그룹의 이름을 IHD로 변경한다.

① -g 
② 555 
③ -n 
④ IHD 


2 

chmod ( ) /share
# ls -ld /share
drwxrwxrwt 2 root root 4096 Apr 25 14:20 /share

1777 

3 
- root 권한으로 crontab 명령어를 사용해서
설정하는 것으로 가정한다.
- 백업 스크립트 파일명은 /home/IHD/backup.sh
이고, 실행권한은 설정되어 있다.
- 매주 토요일 오전 3시 30분에 스크립트가
자동으로 수행되게 설정한다.

30 3 * * 6 /home/IHD/backup.sh 
0부터 일요일이니까

4 
/white 디렉터리를 확장자 white.tar.bz2 압축
한 후 /tmp 디렉터리로 이동시켰다. 압축
해제작업을 수행하고자 할 때

# mv white.tar.bz2 /tmp
# ( ① ) -d white.tar.bz2
# tar ( ② ) white.tar

① bzip2
② -xvf

tar명령어로 묶인 파일을 풀 때에 진행과정이
화면에 표시되도록 하시오. (v) 인듯

5 

커널 컴파일을 진행하기 전에 설치된 모듈
사이의 의존성을 검사하는 명령어는 ( ① ) 이다.
또한, 이 명령어는 모듈이 생성된 디렉터리
안에 모듈간의 의존성 목록 파일을 생성하는데,
이 파일명은 ( ② )이다.

① depmod 
② modules.dep 

6 
시스템이 비정상
적인 종료로 인하여 중요한 백업 디렉터리로
사용되는 파일시스템 점검

# umount /dev/sdc1
umount: /: device is busy.
# ( ① ) -mk /backup
# umount /backup
# fsck ( ② ) /dev/sdc1
# mount /dev/sdc1 ( ③ )

① fuser 
② -yf 
③ /backup 

- 백업 디렉터리의 마운트 지점(Mount Point)은
/backup이고 장치 파일명은 /dev/sdc1이다.
- 마운트를 해제할 수 없는 상황이라서 특정
명령어를 사용하여 프로세스를 종료한다.
- 강제적으로 파일시스템을 체크하고 파일
시스템이 손상되었다면 자동으로 수정한다.
- /backup을 다시 마운트한 후에 파일생성
관련 점검을 한다

7 
프린트 필터(Filter), 프린트 스풀(Spool),
디렉터리 등을 포함하고 있는 환경 설정 파일은
( )이다.

printcap 

8 

/var/log/messages {
( ① )
create ( ② ) root root
( ③ ) 5
}

■ 조 건
- messages 파일의 순환주기를 일주일로 한다.
- 실행권한을 0600로 하며, root 소유권을
가지고 root 그룹에 소속된다.
- 관련 파일의 생성은 최대 5개로 제한한다.

주기 권한 rotate되는 로그개수제한

① weekly 
② 0600 
③ rotate 


9 

시스템의 접속에 관한 보안 로그파일인 ( ① )은
시스템의 불법 침입이 의심이 될 때 확인하는
로그이고, 시스템에 관련된 중요한 이벤트들은
모두 ( ② )파일에 기록된다.

① secure 
② messages 

10 

cat /etc/hosts.deny
( ① ) : ALL
# cat ( ② )
( ① ) : ( ③ )
■ 조 건
- 파일명은 절대경로로 작성하시오.
- 텔넷 서비스를 192.168.3.0 네트워크 사용자만
허가한다.
- 텔넷 서버이름은 in.telnetd이다.

① in.telnetd 
② /etc/hosts.allow 
③ 192.168.3. 


11 임의의 서버로 백업하기 위한 /etc/rsyncd.conf

상위 디렉터리의 접근을 제한하며, 백업 서버의 주소는 190.10.1.1이다

[web]
( ① ) /home/ihd/www
comment = web
uid = nobody
gid = nobody
use chroot = ( ② )
hosts allow = ( ③ )

① path 
② yes 
③ 190.10.1.1 


12 

Listen ( ① )
NameVirtualHost 172.19.120.32
<Virtual Host 172.19.120.32:( ① ) >
DocumentRoot ( ② )
( ③ ) virtual.ihd.or.kr
</VirtualHost>

- 서비스 할 도메인은 virtual.ihd.or.kr 이다.
- /var/www/apache/html의 웹문서로 웹서비스를 제공하려고 한다.
- 웹서버에 추가로 사용되는 포트는 8080 포트이며 웹서버 IP는 172.19.120.32 이다.

① 8080 
② /var/www/apache/html 
③ ServerName 


13 

#vi /etc/pam.d/sshd
#%PAM-1.0
auth include system-auth
account required pam_nologin.so
password include system-auth
session include system-auth
( ① ) required ( ② )

① session 
② pam_loginwhite.so 

사용자가 ssh를 이용하여 해당시스템에 접속하고자 할때 session 인증을 pam_loginwhite.so
라이브러리로 인증받게 설정하시오. (/lib/security/pam_loginwhite.so 파일은 존재한다.)


14 

#( ① ) if=/dev/zero of=/swapfile bs=1024 count=10240
#( ② ) /swapfile 10240
#( ③ ) /swapfile

① dd 
② mkswap 
③ swapon 

15 리버스 존(Reverse Zone)

$TTL 2d ; 172800 seconds
@ IN SOA ns.ihd.or.kr. root.ihd.or.kr. (
2003080800 ; serial number
3h ; refresh
15m ; update retry
3w ; expiry
3h ; nx = nxdomain ttl
)
IN NS ns.ihd.or.kr.
13 IN ( ① ) exam.ihd.or.kr.
( ② ) IN ( ① ) ( ③ )

① PTR
② 7 
③ www.ihd.or.kr. 

IP주소가 192.168.0.7인 www.ihd.or.kr 도메인이 조회가 되도록 설정한다.

16 

① 윈도우에서 접근할 때 나타나는 폴더명은 “data”가 되도록 설정한다.
② 설명은 “Web Data”라고 설정한다.
③ 공유 디렉터리의 경로는 “/home/jalin/data”이다.
④ posein, yuloje 2명의 삼바 사용자만 접근이 가능하도록 설정한다.
⑤ posein 사용자만 파일 생성 및 삭제가 가능하도록 설정한다.

① [data] 
② comment = Web Data 
③ path = /home/jalin/data 
④ valid users = posein yuloje 
⑤ write list = posein

1 

white 라는 사용자 계정의 암호를 다음 조건에
맞게 변경시키고자 할 때 ( 괄호 )안에 알맞은
옵션을 적으시오.
# chage ( ① ) ( ② ) white
# chage ( ③ ) 10 white

- white가 설정한 암호를 2013년 12월 20일에
만료 되게 한다.
- white가 설정한 암호가 만료되기 10일 전
부터 경고메시지를 출력하게 한다.


① -E 
② 2013/12/20 (또는 2013-12-20) 
③ -W

 
2

리눅스 파일 시스템을 ext2에서 ext3로 변경
하려고 할 때 ( 괄호 )에 알맞은 내용을 적으시오
# ( ① ) ( ② ) /dev/sda6
■ 조건
- ext2로 운영중인 장치파일명은 /dev/sda6이다.
- ext2에서 ext3 파일시스템으로 변환시
데이터는 보존되도록 한다
 
① tune2fs 2점 
② -j 2점 [데이터 보존인듯]

3 

ps 명령의 결과가
다음과 같았다. 시스템접속을 허락하지 않은
white 사용자를 로그아웃시키기 위한 작업

white 32301 3185 0 12:22 ?
01:05:32 sshd: white@pts/3

kill -9 32301


4

( ① ) http://isodirect.test.org/os/i386/
whitesample-2.6.2.rpm
# rpm ( ② ) whitesample-2.6.2.rpm
 
① wget 2점 
② -ivh

- URL을 이용하여 현재 디렉토리에 다운
로드한다.
- 설치중 메시지를 출력하며, 진행과정으로
#으로 표시되도록 옵션을 작성한다.

5 

#make ( ① ) : 이전에 생성되었던 파일등을 삭제
#make ( ② ) : 커널생성(bzip2 형식)
#make ( ③ ) : 모듈 컴파일
#make ( ④ ) : 모듈 설치

① clean 1점 
② bzImage (I는 대문자) 1점 
③ modules 1점 
④ modules_install 1점 


6 백업 디렉토리로 사용
(가) fdisk /dev/sdc
(나) mkfs.ext4 /dev/sdc1
(다) mount /dev/sdc1 /backup
(라) mkdir /backup 

(가) - (나) - (라) - (다) 

7 

cat /etc/hosts
192.168.0.100 RLogserver
# vi ( ① )
*.err;kern.debug /dev/console
*.err;*.crit;*.emerg /var/log/critical.log
*.notice ( ② )

① /etc/syslog.conf 2점 
② @RLogserver 2점 

8 

리눅스 기본 명령어를(옵션포함) 이용하여
실시간으로 모니터링 한다

( ) /usr/local/apache/logs/access_log

tail -f



9

ssh 설정 파일의 내용 중 일부이다.
root 계정으로 접근할 수 없도록 텍스트
편집기로 추가하려고 한다. ( 괄호 ) 안에
내용을 적으시오.
# vi sshd_config
Port 22
Protocol 2,1
Protocol 2,1
( )

PermitRootLogin no 

10 rsync을 이용하여 원격지 서버로
백업

rsync -av /data 192.168.0.100:/backup 

- 로컬디렉토리는 /data 이다.
- 원격지 서버 IP주소는 192.168.0.100
이고, 디렉토리는 /backup이다.
- 백업 진행 상황을 자세하게 출력한다.
- 심볼릭 링크, 특성, 퍼미션, 소유권 등은
그대로 보존한다.



번호 답 안 점수 
11 
(8점) 

#vi /etc/httpd/conf/httpd.conf
( ① ) 8080
( ② ) www.ihd.or.kr

① Listen 
② ServerName  

- 포트는 8080 으로 사용한다.
- 도메인명은 www.ihd.or.kr 이다.

12 

쿼터설정을 하여 white 사용자에 대한 공간을 할당하고자 한다. 다음
조건에 맞게 ( 괄호 ) 안에 알맞은 내용을 적으시오.(12점)
#vi /etc/fstab
/dev/sdb1 /usehome ext3 defaults,( ① ) 1 1
#( ② ) white
#( ② ) ( ③ ) white black

① usrquota 4점 
② edquota 4점 
③ -p 4점 

- /etc/sdb1 파티션에 사용자 쿼터에 대한 설정을 적용한다.
- white 사용자의 쿼터 설정후 white 사용자의 설정과 black 사용자의 쿼터설정을
동일하게 적용한다.

13 

service ftp
{
생략
.
.
( ① ) = 09:00-19:00
( ② ) = 3
}

- ftp 서비스를 09시부터 19시 까지만 접속 가능하다.
- 사용자 최대 동시 접속수는 3명으로 제한 한다.

① access_times 
② instances 

14 

subnet 192.168.1.0 netmask 255.255.255.0 {
( ① ) 192.168.1.10 192.168.1.100;
option routers 192.168.1.254;
option subnet-mask 255.255.255.0;
option broadcast-address 192.168.1.255;
default-lease-time 1600;
max-lease-time 17200;
deny ( ② )
}
host admin {
hardware ethernet 00:A0:4B:23:64:7F;
( ③ ) 192.168.1.2;
}
 
① range 4점 
② unknown-clients 4점 
③ fixed-address 4점 

- 클라이언트에게 부여할 수 있는 IP 주소의 범위는 192.168.1.10부터 192.168.1.100이다.
- 인증되지 않는 클라이언트는 거부한다.
- admin 호스트는 00:A0:4B:23:64:7F MAC 주소는 192.168.1.2번의 IP로 고정시킨다.


15 DDoS 공격유형을 파악하고자 패킷 덤프(Packet Dump)를 이용한 유입 트래픽을 확보

eth2 인터페이스에서 흐르는 패킷 중 192.168.0.100 IP 주소를 가지고 있는 패킷만 출력한다.

tcpdump -i eth2 host 192.168.0.100 8점 

16 

# iptables ( ① ) FORWARD DROP
# iptables ( ② ) FORWARD ( ③ ) eth1 ( ④ ) ACCEPT

(12점) 
① -P 3점 
② -A 3점 
③ -i 3점 
④ -j 3점

- 패킷은 거부 메시지 없이 무조건 거절한다. (DROP)
- 두 번째 이더넷카드(eth1)로 들어오는 패킷인 경우에만 포워딩을 허가한다.
- 어떠한 방화벽도 설정되어 있지 않고 커널에서 포워딩을 허가한 상태이다.


1 

usermod ( ① ) IHD ( ② ) /home/IHD/posein
( ③ ) posein

① -g 
② -d 
③ -m 

- 기본 그룹을 “IHD”로 변경
- 홈디렉토리를 “/home/IHD/posein”으로 변경
- 기존에 사용하던 디렉토리 및 파일을 그대로
옮겨올 것.

2 

mount ?t ( ① ) -o ( ② ),( ③ )
rhel-server-6.2-i386-dvd.iso /mnt

① iso9660  
② ro 
③ loo

- rhel-server-6.2-i386-dvd.iso CD-ROM
파일시스템 이미지파일이고, 읽기전용으로
마운트한다.

3 kill -9 27183


4 

# tar ( ① ) backup.tar.bz2
# tar ( ② ) backup.tar.gz backup

- 관련 파일은 현재디렉토리에 존재한다.
- 묶고 푸는 과정을 화면에 나타낸다.
- tar 명령어를 사용하면서 동시에 압축관련
옵션을 사용한다. (반드시 표기할 것)

① jxvf 
② zcvf


5 
① depmod 2점 
② modules.dep 2점 


6 
프린 터 큐 의 상 태 를 모 니터 링 할 수 있 는
명령어는 ( ① ) 이며, 프린터 큐에 있는 인쇄
작업을 취소할 때 사용하는 명령어는 ( ② ) 이다.

① lpq (또는 lpstat 또는 lpc) 2점 
② lprm (또는 cancel 또는 lpc) 2점 


7 

klogd 데몬에 의해 기록되는 중요한 커널의
이벤트들은 모두 ( ① ) 로그파일에 기록되며,
syslogd 데몬의 의해 기록되는 메시지 로그를
실시간으로 모니터링 하고자 하는 명령어는
“tail ( ② ) /var/log/messages” 이다.

① dmesg (또는 /var/log/dmesg) 2점 
② -f 2점 


8 

로그파일은 기존의 로그 파일에 덧붙여서 기록
되어지기 때문에 /var/log 디렉토리안에 로그
파일의 크기는 계속 커지게 된다. 이를 방지하기
위해서 로그 파일을 조각으로 나누어 관리해
주어야 한다.

① logrotate (또는 /usr/sbin/logrotate) 2점 
② /etc/logrotate.conf 2점 


9 

# scp ( 1 ) ( 2 ) ihd@www.ihd.or.kr:( 3 )

① -r  
② ihd (또는 ihd) 
③ dump (또는 dump) 

ihd/ 디렉토리 안의 모든 파일과 하위 디렉
토리를 ihd@www.ihd.or.kr 원격지 서버
주소의 dump 디렉토리 안에 복사한다.

10 
tar -cvzf /Backup/home.tar.gz /home --exclude=/home/ihd 


- tar 명령을 이용한다.
- gzip 형태로 압축한다.
- 압축할 데이터는 /home/ihd를 제외한
/home 디렉토리이다.
- 생성될 압축파일은 /Backup에 위치하며
이름은 home.tar.gz이다
 
11 

<VirtualHost ( ② )>
DocumentRoot ( ③ )
ServerName ( ④ )
</VirtualHost>

① Listen 8080 3점 
② 192.168.10.123:8080 3점 
③ /usr/local/apache/html 3점 
④ www.ihd.or.kr:8080


12 

① /data 디렉토리는 특정 네트워크(192.168.4.0)에서만 접근이 가능하게 하고, 클라이언트
에서 접근하는 root 사용자를 nobody 권한으로 설정한다.

② /backup 디렉토리는 특정호스트(192.168.4.122)에서만 접근이 가능하게 하고, 클라이언트
에서 접근하는 root 사용자를 root 권한으로 허가되도록 설정한다. 또한, 파일 생성 및
삭제도 가능하도록 설정한다.


① /data 192.168.4.0/255.255.255.0(root_squash)
② /backup 192.168.4.122(rw,no_root_squash) 


13 xinetd 설정 내용

service telnet
{
flags = REUSE
socket_type = stream
wait = no
user = root
server = /usr/sbin/in.telnetd
log_on_failure += USERID
disable = no
( ① ) = 192.168.10.22
( ② ) = 192.168.10.0/24
access_times = ( ③ )
( ④ ) = 5
}

- telnet 서비스에 대해 192.168.10.22를 허용하지 않는다.
- telnet을 192.168.10.0/24 IP 대역대만 접속이 가능하다.
- 서비스를 오전 09시부터 오후 6시까지만 접속 가능하다.
- 최대 동시 접속수는 5로 한다.

① no_access 3점 
② only_from 3점 
③ 09:00-18:00 3점 
④ instances 3점 
14 

( ① ) utmp, wtmp, lastlog로부터 특정 엔트리를 제거한다.
( ② ) sun4 기반 커널들의 이더넷 스니퍼이다.
( ③ ) 체크섬값을 가장하는 도구이다.
( ④ ) 매직 패스워드를 통하여 관리자로 로그인하는 도구이다.

① z2 2점 
② Es 2점 
③ Fix 2점 
④ SI 2점 

15 

/sbin/iptables ( ① ) ( ② ) -s 172.168.1.10 ( ③ ) tcp ( ④ ) 22 ?j ( ⑤ )
/sbin/iptables ( ① ) ( ② ) -s 0/0 ( ③ ) tcp ( ④ ) 22 ?j ( ⑥ )
/sbin/iptables ( ① ) ( ② ) -s 192.168.0.10/24 ( ③ ) tcp ( ④ ) 80 ?j ( ⑥ )

① -A 2점 
② INPUT 2점 
③ -p 2점 
④ --dport (또는 --estination-port) 2점 
⑤ ACCEPT 2점 
⑥ DROP 2점 

공격을
시도하고 있는 IP는 192.168.0.10/24 대역대와 같으며 접근통제정책을 통하여 해당되는 IP에
대하여 web 접속을 차단한다. 또한, 22포트는 172.168.1.10 IP에서만 접속을 허용한다.

16 

/etc/hosts.deny
( ① ):( ② )
/etc/hosts.allow
( ③ ):192.168.1.10
vsftpd :( ④ )
sendmail:ALL ( ⑤ ) hacker.co.kr
( ⑥ ): localhost

- 모든 서비스에 대한 모든 클라이언트 접속을 차단한다.
- telnet 서비스는 192.168.1.10 호스트만 vsftpd 서비스는 192.168.1.20 호스트만 허용한다.
- sendmail 서비스는 hacker.co.kr 도메인을 제외한 다른 시스템들은 접근을 허용한다.
- 로컬호스트(localhost)는 모든 서비스에 대한 접근을 허용한다.
- 대소문자를 구분하여 작성한다.

① ALL 2점 
② ALL 2점 
③ in.telnetd 2점 
④ 192.168.1.20 2점 
⑤ EXCEPT 2점 
⑥ ALL 2점


1 

yuloje라는 사용자 계정을 일시적
으로 접속을 막기위해 passwd와 usermod
명령어를 사용할 때

passwd ?( ① ) yuloje
usermod ?( ② ) yuloje

① l 2점 (엘)
② L 2점 


2

작성한 백업 스크립트인 /etc/backup.sh 파일이
매주 월요일, 수요일, 금요일 오후 9시 5분에
실행되도록 crontab에 등록 할 때 ( 괄호 )
안에 알맞은 내용을 적으시오.

 5 21 * * 1,3,5 


3 

[root@ihd ~]# ls ?ld /project
drwxrwxrwx 2 root root 4096 Dec 22 21:05 /project
[root@ihd ~]# chgrp ( ① ) /project
[root@ihd ~]# chmod ( ② ) /project


① ihd  
② 3770

- /project는 ihd 그룹에 속한 사용자만
접근, 파일 생성 및 삭제 가능
- /project 디렉토리는 파일 삭제시 본인이
생성한 파일만 가능
- /project 디렉토리에 생성된 파일은 자동
으로 그룹소유권이 ihd로 지정

4 

rpm ( ① ) sendmail
rpm ( ② ) /bin/ls

① -qc (또는 --query --configfiles ) 
② -qf (또는 --query --file) 

- 설치된 sendmail 패키지 중에 환경설정
관련된 파일만을 찾고자 한다.
- /bin/ls 파일을 설치한 프로그램 이름을
알고자 한다.


5 

make modules는 커널 환경설정에서 모듈로
설정한 기능들을 컴파일하고, 컴파일된 모듈을
설치하려면 ( ① ) 명령을 수행해야 한다. 이
명령어를 수행하면 ( ② ) 디렉토리에 모듈
파일이 생성된다.

① make modules_install 2점 
② /lib/modules


6 
새로운 디스크의 파티션 구조나 마운트 정보를
변경할 때 수정하는 파일을 절대경로를 포함
하여 작성하시오.

/etc/fstab


7

( ① ) OK 정상적인 파일전송
( ② ) No Content
클라이언트의 요구를 처리
하였으나 전송할 데이터가
없음
( ③ ) Forbidden
사용권한에 관계없이
내용을 볼 수 없음
( ④ ) Not Found 문서을 찾을 수 없음

① 200 1점 
② 204 1점 
③ 403 1점 
④ 404 1점 


8
              로그이름   관련데몬이름
보안 로그 /var/log/( ① ) ( ② )
부팅 로그 /var/log/( ③ )
 
① secure 
② xinetd 
③ boot.log 


9 
생성된 데이터베이스를 기준으로 파일의
무결성을 검사

/usr/sbin/tripwire ( 1 )
Parsing policy file : /etc/tripwire/tw.pol
***Processing Unix File System ***
Performing intergrity check ...
Wrote report file : /var/lib/tripwire/( 2 )/
test-20120512-05942.tar


① --check 
② report


10 

- ( 1 )은 시스템을 설치한 후 사용자들이
시스템을 사용해 보기 전에 시스템의 모든
파일들과 프로그램들을 백업한다.
- 풀 백업은 일반적인 기준에 의하여 주기적
으로 시스템의 모든 파일들과 프로그램들을
백업한다.
- 변경분 백업은 앞선 백업에서 변경된 부분
만을 골라 주기적으로 백업한다.
- ( 2 )은 모든 것을 한꺼번에 백업하고 그
다음부터는 앞선 백업에서 변경된 부분만을
골라서 백업한다.
- 다단계 백업은 좀더 적은 비용을 들이면서도
백업 보장 기간을 늘리기 위해 백업한다.


① 데이 제로 백업 2점 
② 단순 백업 2점


11 
(10점) 


① 웹 서버의 도메인을 www.ihd.or.kr로 변경한다.
② 웹 문서가 위치하는 디렉토리를 “/usr/local/apache/www”로 변경한다.
③ 관리자 이메일주소는 posein@ihd.or.kr로 변경한다.
④ 웹 서버에 대한 요청이 있을 때 index.html, index.htm, index.php 순으로 전달되도록 설정
한다.
⑤ 개인 홈페이지 서비스를 위한 홈디렉토리 내의 디렉토리명은 www로 지정한다.


① ServerName www.ihd.or.kr
② DocumentRoot “/usr/local/apache/www
③ ServerAdmin posein@ihd.or.kr 2점 
④ DirectoryIndex index.html index.htm index.php 2점 
⑤ UserDir www 2점 


12 

httpd.conf 파일의 설정항목과 설정값

① 클라이언트에서 존재하지 않는 문서 요청시 회사의 메인 홈페이지(www.ihd.or.kr)로 연결
시킨다.
② 클라이언트에서 접근이 허락되지 않는 페이지 요청시에는 /error/miss.html의 내용을 보여
준다.

(6점) 
① ErrorDocument 404 http://www.ihd.or.kr 
② ErrorDocument 403 /error/miss.html 


13 

① 윈도우에서 접근할 때 폴더명은 “www”가 되도록 설정한다.
② 주석은 “Web Directory”라고 설정한다.
③ 웹 디렉토리의 경로는 “/usr/local/apache/htdocs”이다.
④ posein, yuloje 2명의 삼바 사용자만 접근이 가능하도록 설정한다.
⑤ yuloje 사용자만 파일 생성 및 삭제가 가능하도록 설정한다.

① [www] 3점 
② comment = Web Directory 3점 
③ path = /usr/local/apache/htdocs 3점 
④ valid users = posein yuloje 3점 
⑤ write list = yuloje 3점 


14 

localhost.localdomain RELAY
localhost ( 1 )
( 2 ) REJECT
admin@ihd.or.kr ( 3 )
spam@hacker.com ( 4 )

- spam.com이라는 도메인의 모든 메일을 수신/발신을 거부한다.
- ihd.or.kr의 사용자 admin만 무조건 수신을 허용한다.
- spam@hacker.com에서 오는 메일을 받아 완전히 폐기한다.


① RELAY 2점 
② spam.com 2점 
③ OK 2점 
④ DISCARD 2점 


15 

/etc/named.conf
( 1 ) "ihd.or.kr" IN {
type ( 2 );
( 3 ) "ihd.or.kr.zone";

$ORIGIN ihd.or.kr.
$TTL 10
@ IN SOA ns.ihd.or.kr. root.ihd.or.kr. (
( 4 )
6H
1H
2W
12H )
IN NS ns.ihd.or.kr.
IN ( 5 ) mail.ihd.or.kr.
ns IN A 100.1.1.10
mail IN A 100.1.1.20
www IN A 100.1.1.30
admin IN ( 6 ) www

① zone 2점 
② master 2점 
③ file 2점 
④ 2012032912 2점 
⑤ MX 10 2점 
⑥ CNAME 2점 


- 네임서버는 MASTER(주네임 서버)이고, zone 파일은 ihd.or.kr.zone이다.
- zone 파일의 시리얼 값은 2012032912 이다.
- 메일은 mail.ihd.or.kr로 수신하며 우선순위는 10이다.
- www.ihd.or.kr은 또다른 이름의 admin.ihd.or.kr이 가능하게 설정한다.

16 

( 1 ) 상대방의 키보드 사용 내력을 특정한 파일로 저장해서 이 파일을 참조하여
중요한 정보를 빼내올수 있도록 할 수 있는 프로그램의 일종 이다.

( 2 ) 응용 프로그램 수준으로 응용 프로그램의 정상적인 동작을 하지 못하게 함으
로써 네트워크 기능을 마비시킨다. 여기서 말하는 응용 프로그램은 Mail Storm(메일
폭풍), Java Applet(자바 애플릿), inetd(인터넷 슈퍼 서버) 이다.

( 3 ) 지정된 버퍼의 크기보다 더 많은 데이터를 입력해서 프로그램이 비정상적으로
동작 하도록 만드는 것을 의미하는 공격이다.

( 4 ) 시스템 설계자나 관리자에 의해 고의로 남겨진 시스템의 보안 허점으로 응용
프로그램이나 운영체제에 삽입된 프로그램 코드를 말한다. Worm.ExploreZip 같은 것
들이 하나의 예이다.

① 트로이 목마 
② DOS 공격 또는 DDOS  
③ 버퍼 오버플로 
④ 웜 바이러스 백도어



작업식
 
데몬의 실행 모드는 크게 2가지로 나뉜다. StandAlone모드와 Super Daemon에 의한 Inetd 모드이다.
 
 
Appache 
설치 디렉토리
/usr/local/apache
 
웹 서버의 환경 설정 파일
/usr/local/apache/conf/httpd.conf ( 전체 환경 설정, 가상 호스트 설정, 메인 서버 환경 설정
 
아파치 웹 서버 데몬
/usr/local/apache/bin/httpd
 
CGI
웹 브라우저에서 HTML로 여러가지 정보를 표현할 수 있지만, 그 기능만으로 모든 정보 처리를 다 할 수는 없다.
이것을 보충하기 위한 외부 프로그램과 웹 서버 간의 연결 역할을 하기 위한 규약. Common Gateway Interface.
CGI 프로그램은 통상적으로 C, C++, 펄, 쉘, PHP등을 사용하여 구현한다.
 
SSL
WWW 브라우저와 WWW서버간에 데이터를 안전하게 주고받기 위한 업계 표준 프로토콜.
웹제품 뿐만 아니라 파일 전송 규약등 다른 TCP/IP 응용 프로그램에 적용할수 있으며, 인증 암호화 기능이 있다.
/usr/local/apache/conf/httpd.conf의 끝부분에 위치한 <IfDefineSSL> </IfDefineSSL> 사이에 포함
 
 
 
Samba
설명
리눅스와 윈도우 등의 시스템이 공통적으로 자원을 공유하고 관리할 수 있는 방법.
리눅스 서버에서 사용하는 디스크를 윈도우즈와 같은 다른 운영체제에서도 사용할 수 있다.
 
환경 설정
/etc/samba/smb.conf
 
삼바 서버 데몬
/etc/rc.d/init.d/smb
 
삼바 사용자 설정
/usr/bin/smbadduser    : 사용자 추가.
/usr/bin/smbpasswd    : 사용자의 비밀번호 수정
SWAT
Samba Web Administrator Tool의 약자로서 웹에서 루트 계정으로 삼바를 설정 할 수 있는 유틸리티.
901 포트 사용
/etc/xinet.d/swat    : 설정파일 경로
 
 
 
NFS
설명
근거리 통신망 등 정보 통신 네트워크에 접속되어 있는 다른 컴퓨터에 있는 파일이나 파일 시스템을 공용하기
위한 분산 파일 공유 시스템 소프트웨어.

지정된 클라이언트에서는 단지 마운트를 통해 NFS 서버의 자원을 자신의 자원인 양 똑같이 사용하는것이 가능.
네트워크 트래픽이 걸려 속도가 느려지는 단점
반드시 보안 문제를 신중하게 생각해야 한다.
 
설정 파일
/cat/exports
 
서버 데몬
/etc/init.d/nfs
 
사용 예제
mount ihd.linux.net:/home/ihd /mnt/nfs_d
 
 
 
 
FTP
설명
인터넷상의 컴퓨터들간에 파일을 교환하기 위한 표준 프로토콜.
 
 
 
 
SMTP
설명
TCP/IP의 상위층 응용 프로토콜의 하나로 컴퓨터간에 전자 우편을 전송하기 위한 프로토콜인 RFC 821에 규정.
 
MUA
사용자들이 메일을 보기 위해 사ㅛㅇ하는 프로그램. Eudora, Outlook, Pine
 
MTA
한 호스트에서 메일을 받아 다른 호스트로 메일을 전달하는 역할. Sendmail
 
MDA
수신된 메시지를 해당 사용자의 메일 박스에 저장해 주는 역할
 
Sendmail 설정파일
sendmail.cf, local-host-names, aliases, aliases.db, access, access.db
 
 
 
xinetd
설명
인터넷 서비스에서 여러 개의 데몬을 함께 관리하기 위해 만든 데먼들.
StandAlone으로 실행되지 않고 슈퍼데몬에 의해서 실행된다.
 
설정파일
/etc/xinetd.conf, /etc/services, hosts.allow, hosts.deny
 
서비스 종류
telnet, ftp, pop3, imap
 
 
 
DNS
설명
컴퓨터가 식별하기 쉬운 숫자로 구성된 주소와 인간이 식별하기 쉬운 문자로 구성된 주소간의 이름풀이를 도와주는 시스템
전체적으로 계층형 모델을 따르는 분산 데이터베이스 구조를 이룬다.
 
설정 파일
/etc/named.conf, /varnamed, /var/named/named.local, /var/named/localhost.zone, /var/named/named.rev
 
서버 실행 경로
/etc/rc.d/init.d/named
 
 
 
 
Proxy
설명
인터넷 접속을 대행하고 그결과를 보관하고 보관된 내용을 재전송 해줌으로써 전체저인 대역폭을 절감하는 효과
사용자가 웹 브라우저를 이용하여 인터넷 서핑을 할 때 현저히 느리 ㄴ속도를 보완해주기 위한 방법.
 
설치 디렉토리
/usr/local/squid
 
서버 실행 경로
/usr/local/squid/bin/squid
 
환경설정 파일
/etc/squid/squid.conf
 
 
 
NIS
설명
Networ Information System.사용자들에게 투명한 네트워크 환경을 제공.
passwd와 group 파일의 내용과 같으 ㄴ정보를 네트워크상에 있는 모든 호스트에게 배포하는데 사용하는 일반적인 데이터베이스 액세스 기능을 제공. 모든 호스트에 동일한 계정을 가지게 하여 네트워크가 단일 시스템으로.
 
설정 파일
/etc/nsswitch.conf
 
서버 실행 경로
/usr/bin/ypbind
 
 
 
 
DHCP
설명
동적으로 IP를 할당해 주고 할당을 받는 것.
 
설정 파일
/etc/dhcpd.conf
 
서버 실행 파일
/etc/rc.d/init.d/dhcpd
 
접기
 
 
3. 오답노트
 
접기
 
단답식
 
COMMAND &        : 명령어를 백그라운드로 실행
Ctrl-Z        : 포그라운드 프로세스를 잠시 중지.
fg        : 일시정지된 프로세스를 포그라운드에 복귀.
Ctrl-C        : 사용중인 포그라운드 프로세스 강제 종료
ssh-keygen        : ssh의 인증키를 생상헐 수 있다.다.
scp        : ssh 접속 후 파일을 복사 할 수 있다.
ssh 터널링 :    ssh접속을 다른 프로그램이 사용할 수 있도록 포트 포워딩 해주는 것.
cron                               : 리눅스 시스템에서 반복적으로 어떤 특정한 시간에 작업을 시작할 수 있도록 예약
usermod -d /opt/IHD IHD  : IHD계정의 홈 디렉토리를 /home/IHD에서 /opt/IHD로 변경.
rpm -qR http                    : 설치된 http패키지의 현재 의존성이 있는 패키지들을 사전 검토하려할 경우.
mkfs -t xfs /dev/sdc1       : /dev/sdc1를 xfs파일 시스템으로 만든다.
/usr/local/apache/logs/access_log    : httpd데몬이 액세스 로그
fsck.vfat        : vfat 파일시스템의 점검 명령어
rpm -ql        : 리눅스 시스템에 설치된 설치 경로 검색
lspci        : 현재 시스템에 물리적으로 장착된 PCI 장치들에 대한 정보
insmod    : 리눅스 커널에 모듈을 탑재
lsmod        : 탑재된 모듈을 확인
/var/log/dmesg        : 부팅시의 메시지가 저장된 파일
dmesg        : 부팅시의 메세지를 확인하는 명령어
/etc/pam.d        : PAM의 구성파일 저장 경로. 사용자 인증의 핵심이다.
rdist        : 여러 시스템들 사이에서 파일 동기화 및 파일의 변경여부를 확인하여 데이터를 동기화 하는 명령어
mkinitrd        : 새로운 부트 이미지를 생성하는 명령어
logrotate      : 시스템에 있는 모든 로그 파일을 관리. 로그파일을 자르고, 보관하고, 삭제하고, 압축하고 메일로 보냄
last        : 최근에 접속한 사용자 로그인 정보.
sudo        : 부분적인 root 권한으 요구하는 일반 계정자들에게 권한 부여하는 프로그램
/etc/sudoers        : sudo 유저로 등록하기 위한 설정파일        EX) ihd    ALL=(ALL)    ALL
pwunconv        : 시스템 shadow 시스템을 해제하고 사용자 정보를 이전
pwconv        : 해제한 shadow시스템을 정상적인 shadow시스템으로 재 적용하는 명령어
makemap        : sendmail의 access.db 파일을 만드는 명령어
adduser -g 그룹1 -G 그룹2        : 그룹1을 기본그룹으로 그룹2를 추가 그룹으로.
fstab        : 파일시스템을 구성하는 파티션이나 리무버블 디스크 등이 마운트 포인트가 기록되어 있는 파일
디바이스명    마운트포인트    파일시스템의종류    옵션    덤프여부    fsck체크여부
옵션 : default - 일반, noauto - 리무버블 미디어 드라이버용, ro - 읽기전용, usrquota - 사용제한
덤프여부 : 0 - 덤프안함, 1 - 덤프함
fsck체크여부 : 0  - 체크안함, 나머지 숫자는 적은 숫자부터 체크한다. 1은 루트파티션 전용
chkconfig        : 지정된 런레벨 부팅 시 자동으로 서비스를 실행. Ex) chkconfig --level 3 telnet on
rpm --nodeps        : 의존성 무시
rpm -- force        : 강제
 
 
작업식
 
hosts.allow
Xinetd에 영향을 받는 데몬들은 TcpWrapper프로그램에 의해 접근이 제어된다.
/etc/hosts.allow파일을 통해서 접근 허가를 하고 /etc/hosts.deny파일을 통해서 접근을 거부한다.
 
DaemonList:    ClientList:    option(생략가능): option(생략가능)
DaemonList = 접근을 제어할 서비스. 서비스네임이 아니라 실제 그 서비스를 가동시키는 데몬 프로그램.( ALL )
  즉 각 서비스의 xinetd 설정 파일에서 server 지시자로 설정해 둔 프로그램을 적어두면 된다.
ClientList    = 접근을 제어할 클라이언트를 정의하는 부분. 도메인, IP주소, IP/Mask 등 , 를 구분자로( ALL )
 EXCEPT = 다수의 호스트를 설정할 때 특정 호스트를 제외 할 수 있다.
Ex) 10.10.10.0/255.255.0.0 EXCEPT 10.10.13.13 --> 10.10.13.13을 제외.
option        = 허가되지 않은 호스트에 대해 경고메시지, 연결거부, 허락하기 전에 특정 명령 실행
출처 : http://jjangu.pe.kr/blog/335
 
 
 
 
 
httpd.conf
Listen        : 특정 IP 주소 또는 포트에 연결이 가능하도록 해준다.
DocumentRoot        : 제공할 문서의 상위 디렉토리. 모든 요청은 이 디렉토리로부터 처리된다.
allow from        : 나열되는 주소들에 대한 접근을 가능하도록( all )
deny from        : 나열되는 주소에 대한 접근이 불가하도록 ( all )
DirectoryIndex        : 디렉토리의 파일들을 순서대로 보여줄 때 파일명 들을 나열한다.
<IfModule mod_include.c>        : 명시된 모듈의 상태를 확인.
UserDir    disable            : http://도메인/~계정 형식으로의 접석을 허용치 않을 시
UserDir    public_html        : 기본적으로 http 서버가 읽어들일 디렉토리명
</IfModule>
 
 
named.conf
이 파일에는 기본저으로 zone파일의 위치하는 디렉토리와 2개의 Zone파일이 선언되어 있다.
 
option {
directory "/var/named"        // Zone 파일의 경로
}
zone "ihd.org" {                        // 사용하고자 하는 도메인 선언
    // . : 캐시서버, 0.0.127.in-addr.arpa : 로컬도메인에대한 역번환 정의
type master;                       // 기본 primary로 사용시에는 master으로 선언
file "ihd.zone"                    // 사용하고자 하는 zone파일의 이름을 선언.
}
named.conf - ihd.org.zone
// 네임서버와 관리자의 메일을 설정.
// IN : 인터넷 클래스를 의미.
// SOA : 반드시 필요한 부분. 무조건 첫번째 레코드로 지정. 주네임서버 이메일주소
// A : 도메인에 IP를 부여하는 항목
// NS : 도메인 네임서버를 지시.
// MX : 메일 라우팅 경로를 지시.
// PTR : IP주소에 대응하는 호스트 이름
// NA : 해당 zone을 담당하는 네임 서버 주소
@        IN        SOA        ns.domain.org    root.domain.org {    
20030101900    // Serial                                           
10800             // Refresh                                        
3600              // Retry                                            
3600000          // Expire                                         
43200             // Minimum                                     
}                                                                              
            IN    NS      ns.domain.org                             // 네임서버는 ns.domain.org를 사용한다.
            IN    A        10.0.0.184                                    
localhost     IN    A        127.0.0.1
www          IN    A        190.10.1.1                                   //  웹서버 IP는 190.10.1.1을 사용한다.
mail            IN    A        10.0.0.10                                     // 메일서버의 IP는 10.0.0.10를 사용.
domain.org  IN    MX      10    mail                                    // 메일 서버의 우선순위는 10
 
 
 
 
 
squid.conf
프록시 서버의 설정파일
 
access_log /usr/local/squid/logs/access.log    : 접근 로그를 기록하는 파일 지정.
acl     : 접근 리스트를 정의한다. EX) acl members src 192.168.3.0/255.255.255.0
cache_mem 8MB        : 캐시 사이즈 설정
cache_dir ufs /var/squid (500 16 256 )     : 캐시 디렉토리의 크기, 1,2차 하위디렉토리 갯수
http_access deny all        : 모든 접근을 거부.
 
 
 
 
mail/access
메일의 릴레이를 허용하거나 거부하는 파일
OK        : 지정된 호스트나 사용자에게서 무조건 메일 수신
RELAY        : 지정된 도메인에서 무조건 메일 수신
REJECT        : 지정된 도메인의 모든 메일의 송수신을 거부
DISCARD        : 지정된 도메인에게서 메일을 받아 모두 폐기.
 
 
Connect:localhost.localdomain    RELAY
Connect:localhost                      RELAY
Connect:127.0.0.1                       RELAY
spam.com                                 REJECT        // spam.com이라는 도메인에서 전소외는 모든 메일은 거부
spammer@spammer.com             DISCARD
 
 
 
 
Xinetd - telnet
service telnet
{
flags                      = REUSE                       
socket_type            = stream
wait                       = no
user                      = root
server                    = /usr/sbin/in.telnetd
log_on_failure        += USERID
disable                  = no
only_from               = 192.168.1.0/24                // 접속 할 수 있는 인가된 주소들
redirect                 = 192.168.0.15 23                // 접속 시 192.168.0.15의 23번 포트로 보낸다.
}
 
 
 
 
 
proftpd.conf
ftp의 한 종류
 
ServerName        : 서버의 이름을 설정
ServerType        : StandAlone인가 Inetd모드인가를 설정
MaxInstance        : 접속이 가능한 최대 사용자를 설정.
<VirtualHost test >        : tes란 이름을 사용하는 가상 호스트
Port    12345            : 사용할 Port는 12345
DefaultRoot    ~        : 기본 경로는 자신들의 홈 디렉토리( 자신의 홈 디렉토리를 벗어날 수 없도록 )
</VirtualHost>
 
 
 
 
procmailrc
스팸메일을 거르는 설정파일
 
SHELL="/bin/sh"                                        : 사용할 쉘은 /bin/sh
SENDMAIL="/usr/sbin/sendmail" : 0             : 사용중인 MTA의 위치
*^Subject:.*(광고|홍보)                               : 광고, 홍보 단어가 포함된 메일을
/dev/null                                                   : 수신제거
 
 
 
 
 
smb.conf
삼바서버의 설정파일
 
[public]                            : 공유 이름
comment = 공유폴더            : 설명
valid user = @users            : 접근을 허용할 그룹
writeable = yes                  : 쓰기 가능 여부
path = /public                    : 공유 경로

* 문제풀이 Tip

1. --help 와 man

문제에 주어진 명령어(예, rpm)의 옵션과 용법을 푸는 문제의 경우 rpm --help  ,  man rpm 을 이용하여 문제를 풉니다.

1) --help 사용 예

rpm --help | more  <- 한 화면씩 보기

rpm --help | grep group <- rpm --help 명령 중 키워드(group)만 검색

 

2) man 사용 예

man rpm 실행하면 rpm에 대한 설명이 나옵니다.

vi / vim 편집기처럼 필요한 옵션을 검색하여 사용하세요.

/ 누르고 단어를 입력하면 해당 단어를 검색할 수 있습니다.

그리고 n 을 누르면 "다음 찾기"가 됩니다.

q를 누르면 man 종료

 

2. find 명령어

conf 파일의 경로를 문의하시는 분들이 많습니다. 외우면 좋지만 너무 많죠.

시험 볼 때 find 명령어를 사용하세요.

USB 전체도 금새 검색됩니다.

 

- find 사용 예

find / -name *.conf    <- / 디렉토리 하위의 *.conf 검색

find / -name sendmail.cf   <- sendmail.cf 검색

find / -name *.conf | grep httpd  <- / 디렉토리 하위의 *.conf 검색하며 httpd 포함만 출력

 

3. 키워드 검색

--help, man, find 명령어를 잘 쓰려면 문제에 주어진 키워드나, 한글의 적절한 영단어 키워드 생각이 중요합니다.

 

4. vim 을 잘 쓰자

 
모드 전환은 ESC로 가능하죠?

/ 입력 후 문자열을 입력하면 해당 문자열을 검색할 수 있고 n 을 누르면 "다음 찾기"가 됩니다.

:$ 는 맨 마지막

:0 은 맨 처음 으로 이동 합니다.




5. 대/소문자 구분을 어려워하지 마세요.

작성한 답안 검증시

명령어가 오류없이 실행되면 '정상'

환경설정 파일의 값은 man이나 vim 으로 열면 답이 눈에 보이니 그대로 적읍시다.




6. 로그 / 바이너리 위치

리눅스의 바이너리는 거의

/usr/bin

/bin

/sbin 에 존재 합니다.

 

로그는 /var/log 죠...

로그의 경우 Text 로그는 cat / vim 으로 내용을 볼 수 있으나

바이너리 로그는 해당 바이너리를 실행해야 결과를 볼 수 있는 점은 참고 하세요.

 


4-3 rpm 옵션 

>> -i,U,F 설치

>> -e 삭제

>> -q 옵션 ++

>> -qc : 환경설정 관련파일 검색 

>> -qi : rpm 정보

>> -qa : rpm 모든정보

>> -qf : 설치한 프로그램 이름 검색 

--- nodepes, force

--->> exam : rpm -qc sendmail

--->> exam : rpm -qf /bin/ls




[파일시스템]

4-8 SWAP영역 사용상황 확인 및 활성화 명령어

>> swapon // swapoff

>> mkswap -c (디스크검사) -f (무조건수행) 장치 (사이즈)

>> 1. 파티션 생성 mkswap -c /dev/hda1

>> 2. 파일 생성    dd if=/dev/zero of=/swapfile bs=1024 count=1024000

>> 3. 활성화        swapon -s (파티션 or 파일별 사용량 보여줌)

>> (모든 device 활성화 swapon -va)




fdisk 명령어 

>> fdisk /dev/hda0

>> fdisk m (설명) n (생성) p (파티션) t (swap) w (저장종료)

>> mke2fs /dev/hdb1 (ex2)

>> mkfs.ext3 /dev/hdb1 (ex3) , mkfs.ext4 /dev/hdb1 (ex4) 

>> mke2fs -T ext4 /dev/hdb1 (파일 시스템 지정 -T, -j ext3)




* 점검 fsck -t ext3 /dev/hda0 , e2fsck -c /dev/hda0




mount 명령어

>> mount -t (파일시스템 지정) (마운트 장치) (마운트 위치)

>> mount -t ext3 /dev/hda0 /mnt/hda0

>> mount -a (모든 시스템 mount) -o (ro,rw)




>> /etc/fstab (부팅시 마운트 대상), /etc/mtab (마운트 상황)




4-9 tar 옵션

>> c : 압축 , x : 해제

>> p : 파일의 퍼미션 변경없이 보존

>> z : tar 묶음 후 gzip 압축

>> f : 뒤에 지정 된 파일 또는 디바이스를 사용

>> C : 해제 할 디렉토리 지정

>> r : 기존 tar에 파일추가

-------->> exam : tar -xvzpf /etc/abc




4-12 Quota 사용자 디스크 사용량 제한

>> usrquota (사용자) , grpquota (그룹)

>> quotaon (쿼타 활성화), edquota (편집)




4-13 로그인 쉘 변경

>> /bin/bash -> /bin/csh

>> chsh -s (shell) /bin/csh ihdcp(계정)







4-16 심볼릭 링크 파일 생성

>> ln -s (symbolic)




4-21 fsck 파일시스템 체크

>> -A /etc/fstab 모든 파일시스템

>> -R root파일시스템 SKIP

>> -a autorepair 자동 수리





--------------------------------------------------------------------------------
 

5. 장치관리

 

커널 컴파일 방법

-- make mrproper (작업장 청소)

-- make confix , xconfig, nconfig, menuconfig (컴파일 설정)




실제 컴파일 과정

1) make clean (이전 설정 값 제거)

2) make bzImage (커널 이미지 생성)

3) make modules (모듈 컴파일)

4) make modules_install (모듈 설치 /lib/modules )

>>  make clean bzImage modules modules_install 또는 make all 또는 make  (한 방에 가능 ..)

5) depmod -ae -F System.map <kernel-version>  (의존성 검사)

6) make install

>> uname -r , -a 설정확인




모듈 관리

modprobe -r (제거) -c (설정확인) -l (전체리스트)

lsmod (사용중인 모듈리스트)

/etc/modprobe.conf (부팅 시 자동 모듈 로드)

insmod -k (미사용 모듈 자동 언로드)

modinfo (모듈정보확인)




mknod 장치파일 생성 명령어




lspci (시스템에 사용되는 PCI 정보 확인)

dmesg (부팅 시 화면출력 메시지 확인)




5-1

>> make install , /etc/modules.conf

--------> make modules_install, /lib/modules

5-2

>> fdisk, mount, -T   ??

--------> mkfs.xfs (mkfs -t xfs) , mount, -t

5-3

>> ?? alias , alias usb-uhci usb-uhci.o

--------> autoclean , insmod -k usb-uhci (modprobe -k usb-uhci)

5-4

>> mrproper, make menuconfig

--------> make mrproper , make menuconfig

5-5

>> /etc/modules.conf

--------> proc/modules

5-6

>>uname -r, -a

5-7

>> modprobe -c usb-uhci , modprobe -r usb-uhci    ??

--------> modinfo usb-uhci, rmmod usr-uhci

5-8

>> fdisk -l , mke2fs -T ext4 /dev/sdb1 , mount -o ext4 /dev/sdb1 /home2

--------> mount -t ext4 /dev/sdb1 /home2

5-9

>> a-c-d-b

5-10

>> ???

--------> mknod /dev/mydrv c 195 1, rm /dev/mydrv

5-11

>> modprobe -r (rmmod) , ipip  ide-cd ipchains cdrom 

5-12

>> ?? , lsmod , ?? , rmmod( modprobe -r)

--------> lspci( cat /porc/pci ) , lsmod, dmesg (cat /var/log/dmesg) , rmmod

5-13

>> insmod ne 

--------> lnsmod io=0x0300 irq=9 ne





--------------------------------------------------------------------------------





6. 시스템 보안 및 관리




모든 로그는 /var/log/ 기록 

messages - 모든 사항

secure - 원격접속

mailing - 메일 송수신

cron - crontab 

boot.log - 서비스 데몬들의 부트 정보

dmesg - 부팅 시 보이는 시스템 정보

wtmp - 최근 접속 사항 last 명령어로 확인

lastlog - 마지막 로그인 기록 

xferlog - FTP 기록

access_log - 아파치 로그 (http)

error_log - 아파치 에러로그




at - 예약작업 명령어

chkconfig , ntsysv 서비스관리 명령어




ssh - 원격 접속 명령어

ssh -l [계정] [주소] - 원격 로그인

ssk-keygen - 인증키 생성




ssh를 이용한 원격지 복사

- ihd/ 폴더 전체를 ihd@www.ihd.or.kr 원격서버의 dump/ 디렉토리에 복사하기




scp -r (하위디렉토리포함) ihd/ 

ihd@www.ihd.or.kr:/dump/




tripwire - 위,변조 방지 무결성체크 도구

tripwire -m i, --init (db초기화)

tripwire -m u, --update (업데이트)

tripwire -m p, --update-policy [경로] (경로파일 정책으로 업데이트)
 




백업관련 명령어

cpio, dump, taper, rdist, rmt, tar/gzip




dd 블록단위파일 복사

dd if=[파일입력 지정] of=[파일출력 지정] bs=[한 번에 입력할 byte양]

#dd를 이용하여 /dev/sda 를 /dev/sdc로 복사하기

#dd if=/dev/sda of=/dec/sdc bs=1024




HTTP 상태메시지 

200 - 정상파일전송

204 - 파일은 발견되나 내용없음(Not Content)

403 - 권한없음 (Forbidden)

404 - 페이지 없음 (File Not Found)

500 - 내부서버에러(Internal Server Error)





--------------------------------------------------------------------------------
7. 네트워크 서비스




7.1아파치 (httpd : apache)

1) 실행파일 /usr/local/apache/bin/

2) 로그        /usr/local/apache/log/

3) 설정        /usr/local/apache/conf/




7.2인증 서비스

1) NIS (ypinit , yppush, ypxfr, ypbind, ypserv)

- 부팅시 적용 ( /etc/sysconfig/network )

- DB map ( /var/yp/ )




service protmap start

service ypserv start

service yppasswdd start

service ypxfrd start

chkconfig protman on

... 동일하게




/etc/hosts NIS IP 추가

/etc/sysconfig/authconfig NIS사용 여부 수정 (USENIS=yes)

/etc/yp.conf 서버리스트 추가 ( domain abc.net server nis.abc.net)

/etc/nsswitch.conf




2) LDAP (LDIF 파일 포맷)




7.3 삼바SAMBA

- CIFS (common internet file system) smb확장버전

- swat (samba web administration tool) /etc/xinet.d/swat

/etc/samba/smb.conf




7.4 vsftpd

/etc/vsftpd/vsftpd.conf 설정




7.5 sendmail

/etc/mail/sendmail.mc

/etc/mail/access 접근설정

REJECT relay 비허용

DISCARD 메일 폐기

501 메일주소 차단

503 도메인 차단

550 메시지로 거부

553 발신자 정보없으면 거부

571 경로 제시 후 거부




7.6 DNS 

/etc/resolv.conf  

/etc/named.conf 네임서버 설정

/var/named  네임서버 zone 파일 경로




설정파일 검증

named-checkconf [경로]

named-checkzone [경로]




@@@ fdisk /dev/sda [Hex code 알수잇음]


@@@ vi /etc/vsftpd/vsftpd.conf

anonymous_enable = yes : 익명 ftp 서비스 활성화 여부 설정
local_enable = yes : 로컬 계정 사용자 접속 여부 설정
write_enable = yes : 쓰기 가능 여부 설정
local_umask = 022 : 파일 퍼미션 정의(파일의 퍼미션은 644)
dirmessage_enable=yes : 디렉토리 이동시 각 디렉토리 메시지 보여지게 할지 여부
anon_upload_enable = yes : 익명 FTP 접속자의 파일 업로드 권한 설정 
anon_mkdir_write_enable = yes : 익명FTP 접속자의 디렉토리 생성 권한 설정
dirmessage_enagle=yes : FTP접속자가 다른 디렉토리로 이동시, 알림메시지 출력여부 설정 
xferlog_enable=yes : FTP 접속자들의 업/다운로드 상황 로그파일 저장 여부 설정
connect_from_port_20=yes : standlone 모드를 운영하면서 데이터 전송포트 사용시 설정
chown_uploads=yes : 익명 FTP 서비스에서 익명 접속사 업로드한 파일의 소유권 자동 변경 설정 
chown_username=whoever :익명 FTP 서비스에서 익명 접속자가 업로드한 파일의 소유권 자동 변경한 후, 그 소유권을 변경할 사용자 설정 (root로 설정하지 말고)
xferlog_file=/var/log/xferlog : 로그파일 경로 설정
xferlog_std_format=yes : 로그파일 포맷 설정
idle_session_timeout=600 : idle 상태에서 접속을 유지할 최대 시간 설정(기본값 300초)
data_connection_timeout=120 : 파일 업/다운로드시 연결을 유지하는 시간 설정(기본값 300초)
nopriv_user=missflash : 익명 FTP 접속자가 접속하는데 사용할 사용자 설정 (기본값 nobody)
async_abor_eanble=yes : async ABOR명령 가능 여부 설정(기본설정 NO)
acscii_upload_enable=yes : ASCII 파일 업로드 가능 여부 설정(기본값NO)
ascii_download_enable=yes : ASCII 파일 다운로드 가능 여부 설정(기본값 NO)
ftpd_banner=welcome : FTP 접속자에게 보여줄 환영 메시지 설정 
deny_email_enable=yes : 익명 FTP접속시 접속을 거부할 이메일 설정(기본값 ㅜㅒ)
banned_email_file=/etc/vsftpd/banned_emails : 접속을 거부할 이메일의 파일 경로 설정
chroot_local_user=yes : 홈 디렉토리 위로 이동 제한 여부 설정(기본값 NO)
chroot_list_enable=yes : chroot에서 제외할 사용자 목록파일 사용 여부 설정(기본값 NO)
chroot_list_file=/etc/vsftpd/chroot_list : chroot에서 제외할 사용자 목록 파일과 경로 설정
ls_recurese_enable=yes FTP 접속자들의 ls -R 명령어 사용가능 여부 설정 기본값 no)
listen=yes : standlone모드로 서비스할때 설정 (기본값 xinetd)
pam_service_name=vsftpd :pam 인증에 사용할 설정파일의 이름 설정
userlist_enable=yes : userlist 에 있는 계정 접속 허용 
tcp_wrappers=yes : tcp_wrapper의 접근제어를 받도록 설정한다.


@@@ fsck 명령으로 시스템 점검
#fsck -y /dev/sdb1 : 복구할지 물어 보지 않고 자동 yes 처리 함
#fsck -a /dev/sdb1
 
6. fsck 주요 옵션
형식 : fsck [-옵션] [파일시스템 옵션] 파일시스템 또는 디스크 디바이스

 
-A 일반적으로 /etc/fstab에 나와 있는 파일 시스템들을 검사하고 /etc/rc 시스템 초기화 파일에서 일관적으로 점검한다.
-R -A옵션과 같이 사용하면 루트 파일 시스템을 제외한 모든 파일시스템을 점검한다.
-T 검사할때 제목을 보여주지 않는다.
-N 실제적으로 실행은 하지 않고 어떤 작업을 할것인가만 보여준다.
-P -A옵션과 같이 사용하면 다른 파일 시스템과 루트 파일 시스템을 병렬 처리하여 점검한다.
그러나 루트 파일 시스템에 에러가 있을 경우 바이너리 파일이 깨질수 있으니 좋지 않다.
-s fsck 동작을 시리얼화 한다. 대화형 모드에서 여러 파일 시스템을 점검할 때 유용
-V 실행되는 각 파일 시스템용 명령을 포함하여 자세한 출력을 수행한다.
-t 점검할 파일 시스템을 설정한다. 파일 시스템 앞에 no를 붙이면 지정한 파일 시스템을 제외한 나머지를 모두 점검 한다.
-a 사용자에게 질문하지 않고 자동적으로 복구한다. 권장하지 않음
-r 파일 시스템 복구 전에 복구 여부를 묻는다. 단 병렬로 작동할때는 권장하지 않음
--v 버전정보를 보여준다.

@@@ vi /etc/ntp/ntp.conf 

  restrict default nomodify notrap noquery 
  restrict 127.0.0.1 
  restrict 192.168.0.0 mask 255.255.255.0 nomodify notrap 

  # straum 2 server list 
  server ntp.ewha.net 
  server ntp1.epidc.co.kr 
  server time.bora.net 
  server time.wonkwang.ac.kr 
  server time.korserve.net 
  server noc6-3.koren21.net 

   driftfile /var/lib/ntp/drift 
   broadcastdelay 0.008 
   keys /etc/ntp/keys 

?/etc/ntp.conf와 driftfile 과 keys의 경우 배포본마다 위치가 다를 수 있으니 확인을 하도록 한다.
?restric 설정은 peer 들이 본 서버로 sync 하는 것에 대한 제한을 한다.
?restrict default nomodify notrap noquery 설정은 기본으로 모든 권한을 주지 않음을 의미한다.
?restrict 127.0.0.1 설정은 127.0.0.1 즉, 서버 자신에서는 모든 권한을 가진다.
?restrict 192.168.0.0 mask 255.255.255.0 nomodify notrap 설정은 192.168.0.0 ~ 192.168.0.255 c class 에서는 질의를 할 수 있는 권한을 가진다. 즉, 위의 2 라인은 항상 기본으로 들어가는 설정이며, peer 를 거느릴 서버에서는 (즉 A 의 입장에서는) 하위 peer 들의 질의를 받을수 있도록 3 번째 라인과 같이 restrict 설정을 해 주어야 한다.

설정을 마쳤다면, service ntpd restart 명령으로 ntpd 데몬을 시작하고, ntpq 명령을 이용하여 sync 를 잘 하고 있는지 확인을 한다.


iptables


INPUT : 호스트 컴퓨터를 향한 모든 패킷
OUTPUT : 호스트 컴퓨터에서 발생하는 모든 패킷
FORWARD : 호스트 컴퓨터가 목적지가 아닌 모든 패킷, 즉 라우터로 사용되는 호스트 컴퓨터를 통과하는 패킷
3) 매치(match)

iptables에서 패킷을 처리할때 만족해야 하는 조건을 가리킨다. 즉, 이 조건을 만족시키는 패킷들만 규칙을 적용한다.

--source (-s) : 출발지 IP주소나 네트워크와의 매칭
--destination (-d) : 목적지 ip주소나 네트워크와의 매칭
--protocol (-p) : 특정 프로토콜과의 매칭
--in-interface (i) : 입력 인테페이스
--out-interface (-o) : 출력 인터페이스
--state : 연결 상태와의 매칭
--string : 애플리케이션 계층 데이터 바이트 순서와의 매칭
--comment : 커널 메모리 내의 규칙과 연계되는 최대 256바이트 주석
--syn (-y) : SYN 패킷을 허용하지 않는다.
--fragment (-f) : 두 번째 이후의 조각에 대해서 규칙을 명시한다.
--table (-t) : 처리될 테이블
--jump (-j) : 규칙에 맞는 패킷을 어떻게 처리할 것인가를 명시한다.
--match (-m) : 특정 모듈과의 매치

-A (--append) : 새로운 규칙을 추가한다.
-D (--delete) : 규칙을 삭제한다.
-C (--check) : 패킷을 테스트한다.
-R (--replace) : 새로운 규칙으로 교체한다.
-I (--insert) : 새로운 규칙을 삽입한다.
-L (--list) : 규칙을 출력한다.
-F (--flush) : chain으로부터 규칙을 모두 삭제한다.
-Z (--zero) : 모든 chain의 패킷과 바이트 카운터 값을 0으로 만든다.
-N (--new) : 새로운 chain을 만든다.
-X (--delete-chain) : chain을 삭제한다.
-P (--policy) : 기본정책을 변경한다.

4) 타겟(target)

iptables는 패킷이 규칙과 일치할 때 동작을 취하는 타겟을 지원한다.

ACCEPT : 패킷을 받아들인다.
DROP : 패킷을 버린다(패킷이 전송된 적이 없던 것처럼).
REJECT : 패킷을 버리고 이와 동시에 적절한 응답 패킷을 전송한다.
LOG : 패킷을 syslog에 기록한다.
RETURN : 호출 체인 내에서 패킷 처리를 계속한다.
REJECT는 서비스에 접속하려는 사용자의 액세스를 거부하고 
connection refused라는 오류 메시지를 보여주는 반면 
DROP은 말 그대로 telnet 사용자에게 어떠한 경고 메시지도 보여주지 않은 채 패킷을 드롭한다. 관리자의 재량껏 이러한 규칙을 사용할 수 있지만 사용자가 혼란스러워하며 계속해서 접속을 시도하는 것을 방지하려면 REJECT를 사용하는 것이 좋다.

DNS -- TCP 53 / UDP 53
BASH
iptables -A INPUT -p tcp --dport 53 -j ACCEPT
iptables -A INPUT -p udp --dport 53 -j ACCEPT
웹서버

HTTP -- TCP 80
BASH
iptables -A INPUT -p tcp -m tcp --dport 80 -j ACCEPT
HTTPS -- TCP 443
BASH
iptables -A INPUT -p tcp -m tcp --dport 443 -j ACCEPT
-A INPUT -m state --state NEW -m tcp -p tcp -m multiport --dports 80,443 -j ACCEPT
MySQL -- TCP 3306
BASH
iptables -A INPUT -p tcp --dport 3306 -j ACCEPT 
FTP(passive mode)
BASH
iptables -A INPUT -p tcp --dport 21 -j ACCEPT
iptables -A OUTPUT -p tcp ?-sport 21 -j ACCEPT

iptables -A INPUT -p tcp --dport 1024:65535 -j ACCEPT
iptables -A OUTPUT -p tcp --sport 1024:65535 -j ACCEPT
메일서버

SMTP -- TCP 25
BASH
iptables -A INPUT -p tcp -m tcp --dport 25 -j ACCEPT
Secure SMTP -- TCP 465
BASH
iptables -A INPUT -p tcp -m tcp --dport 465 -j ACCEPT

A.시스템사용자 생성작업 
 
1./etc/passwd 파일에 사용자의 계정(ID 및 패스워드) 생성
2./etc/shadow 파일에 계정 패스워드 등록
3./etc/group 파일에 사용자의 그룹생성
4./home 에 사용자의 홈디렉토리 생성
5.ftp사용을 위한 FTP사용 환경설정
6.메일사용을 위한 메일환경 설정
7. 사용자의 로그인정보 및 환경설정
8. 사용자의 디렉토리 및 파일 소유주권 변경 및 확인
9. DB사용을 위한 환경설정
10. 기타응응용 소포트웨어 사용을 위한 설정
 
관련된 작업을 useradd 와 다른 명령어들을 이용하여 수행한다.
 
useradd 옵션들
-c 대부분 사용자명을 입력하며 ,finger로 확인하면 보여주는 간단한 작업
-d 생성하는 계정사용자의 홈디렉토리위치지정 (예 -d /home/copy)
-e 생성하는 계정의 사용종료일자 지정 (예 -e 2004-12-31)
-f 생성하는 계정의 패스워드 유효일자 지정 (예 -f -30 앞으로 30일동안 유효)
-g 생성하는 계정의 로그인그룹 (예 -g 1004)
-p 생성하는 계정의 패스워드
-s 생성하는 계정의 로그인 쉘
-u 생성하는 계정의 UID 지정
 
계정생성방법
uaeradd testuser : testuser 라는 계정생성
passwd testuser : testuser 의 패스워드설정
 
이렇게 생성한 생성작업은 /etc/passwd 에(ID,암호,UID,GID,이름,홈디렉토리,로그인쉘) 저장된다.
그리고 /etc/shadow 에도 암호정보와 계정 aging 정보가 등록된다.
/etc/group 파일에도 그룹정보가 등록된다.(GID 번호가 passwd 에 있는 GID와 동일)
 
계정생성 예제
 
useradd -d /user/bible2 -u 1000 -s /bin/sh bible2
홈디렉토리 : /user/bible2
UID : 1000
로그인 쉘  : /bin/sh
아이디 : bible2
 
useradd -d /home/sspark1 -u 600 -s /bin/csh sspark1
홈디렉토리 : /home/sspark1
UID : 600
로그인 쉘 : /bin/csh
아이디 : sspark1
 
useradd -d /usr/bible9 -u 510 -g 500,501 -s /bin/bash -f 10 bible9
홈디렉토리 /usr/bible9
UID 510
GID 500,501
로그인 쉘 : /bin/bash
계정유효(패스워드유효) 10일 
아이디 bible9
 
위예제같은경우 500,501 과 단독그룹 bible9  총 3개가 생성 또는 포함된다.
 
B.useradd 의 환경을 설정하는 useradd -D
useradd -D : changing the default values
useradd 의 -D옵션이다 이옵션은 useradd 의 기본환경 설정을 한다.
useradd로 생성되는 기본홈디렉토리의 위치를 변경하거나
기본그룹을 수정하거나 기본사용쉘 지정 등을 할 수 있다.
 
1줄요약 : useradd 시 자동생성되는 기본값을 수정
 
해당설정값을 확인 할 수 있다.
[root@localhost ~]# useradd -D
GROUP=100  
HOME=/home
INACTIVE=-1
EXPIRE=
SHELL=/bin/bash
SKEL=/etc/skel
CREATE_MAIL_SPOOL=yes
 
useradd -D 는 /etc/default/useradd 파일의 값을 변경한다.
 
수정법
-D만 추가될뿐 기존옵션은 그대로 작용
 
useradd -D -b /usr :기본디렉터리를 수정한다.
useradd -D -s /bin/sh :기본쉘을 수정
useradd -D -e 2015-12-31 :  기본으로 생성된 계정을 사용일을 2015년 12월31일 까지
 
useradd 에 관한 사용자 생성 및 관리와 밀접한 관계가있는 3개의 파일이있다. 
/etc/default/useradd
/etc/login.defs
/etc/skel/
 
useradd환경을 지배하는 3개의 파일 
 
useradd 가 참조하는 파일 /etc/default/useradd
GROUP=100 : 기본등록그룹의 GID
HOME=/home : 기본디렉터리
INACTIVE=-1 : 패스워드종료일 이후의 유효기간여부 설정 (0,1,-1 이상의 숫자)
EXPIRE= : 계정종료일자
SHELL=/bin/bash : 기본사용쉘 지정
SKEL=/etc/skel : 홈디렉토리에 복사할 기본환경의 위치
CREATE_MAIL_SPOOL=yes
[root@localhost ~]#  
 
옵션은 전에 설명하였는 useradd -D 로 수정하거나 /etc/default/useradd파일을수정한다
 
 
useradd 가 참조하는 2번째 /etc/login.defs
 
[root@localhost ~]# cat /etc/login.defs 

MAIL_DIR        /var/spool/mail   #메일 디렉토리 지정 

PASS_MAX_DAYS   99999 #패스워드 변경후 재변경없이 지속적으로 사용가능한 최대일자
PASS_MIN_DAYS   0  #패스워드 변경 후 다시 변경할 수 있는 최소일자
PASS_MIN_LEN    5 # 인정될 수 있는 패스워드의 최소길이
PASS_WARN_AGE   7 #패스워드 사용일자가 종료되기 7일전 부터 경고메시지 출력
 
UID_MIN                   500    #유저ID 숫자 최소값
UID_MAX                 60000 #최대값
 
GID_MIN                   500   #그룹ID 최소값
GID_MAX                 60000 #최대값
 
CREATE_HOME yes #홈디렉토리생성여부
MD5_CRYPT_ENAB yes #  패스워드암호화를 MD5 또는 DES 사용 
UMASK #umask(permission mask) 지정 미지정시 기본 022 유지
USERGROUPS_NEAB yes # userdel 실행시 멤버가 없는 그룹도 삭제됨
ENCRYPT_METHOD SHA512 # 암호화방법으로 SHA512사용여부
