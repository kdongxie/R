CentOS 7

R-Server 설치 방법 

~~~
yum install epel-release
~~~

관리자 권한으로 설치를 진행한다. 

~~~
yum update
~~~

설치한 파일을 가상서버에 Update 한다.

~~~
shutdown -r now
~~~



~~~
yum install R -y
~~~



~~~
$ wget https://download2.rstudio.org/rstudio-server-rhel-1.1.463-x86_64.rpm
~~~

$ 는 사용자 권한으로 실행 시키라는 표시 

웹에서 R-studio를 다운받는다.

~~~
yum install rstudio-server-rhel-1.1.463-x86_64.rpm
~~~

다운 받은 R-studio의 설치를 진행하는다.

~~~
systemctl status rstudio-server
~~~

R-studio의 상태를 확인한다. 

~~~
systemctl start rstudio-server
~~~

R-studio의 Server를 실행시킨다. 

~~~
$ rstudio-server
~~~



~~~
$ rstudio-server active-sessions
~~~

R-studio를 Active진행

~~~
http://192.168.137.101 또는 ip:8787/ -> R Web GUI
~~~

192.168.137.101 은 서버의 주소이다. 

전체 형식은 192.168.137.101:8787 로 접속한다. 



