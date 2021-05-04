생성된 컨테이너는 기본적으로 네트워크 연결이 안돼있음 : IP와 포트를 호스트 컴퓨터의 IP와 포트에 바인딩해야 함

포트 바인딩 형식 : docker run -p (호스트 IP) : 호스트 포트 : 컨테이너 포트 (호스트 포트 미입력시 해당 컨테이너 포트와 호환되는 무작위 호스트 포트 연결)

	-여기서 중요한 게 이미지에 맞지 않도록 포트를 잘못 설정하는 경우 정상적으로 컨테이너가 동작하더라도 서비스가 실행 안되는 경우가 생길 수 있음
 
docker run 옵션 : -d(백그라운드에서 실행) -e(컨테이너 내부의 환경변수 설정), --link(링크하려는 대상이 Running 중이어야 연결 가능)

우분투 명령어

	apt-get [옵션] 로 실행

		- 옵션 : update(업데이트), istall/remove 패키지(패키지 설치, 삭제)

	service 패키지 start  : 서비스 스타트

	echo : i/o 관리(?) 명령
	
		-example : echo test >> /root/test  : root 디렉토리의 test 파일에 test라고 입력 후 저장
	
	vi : text 편집기

		-example : vi /root/test  : 위에서 생성한 test 파일 편집기로 open

apache2를 통해 실제 서버 개설 실행

AH00558 에러 발생 : ServerName이 설정되어 있지 않아서 생기는 오류로 컨테이너에 진입해서

	-echo "ServerName localhost" >> /etc/apache2/apache2.conf 입력 후 서비스 재시작하면 오류 없이 정상 동작
