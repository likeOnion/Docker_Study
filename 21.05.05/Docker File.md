
### 도커 파일  
#### 완성된 이미지를 생성하기 위해 설치해야할 패키지, 소스 코드 등 필요한 작업들을 한 곳에 기록한 파일  
#### 어플리케이션에 필요한 패키지를 명시할 수 있고, 이미지 생성을 자유화할 수 있다는 장점이 있음  
#### 한 줄이 `명령어(대문자) 옵션`으로 구성되며 이 한 줄이 하나의 명령이 됨  
---
`도커 파일 명령어 목록`
|명령어|내용|비고|
|:---:|:---:|:---:|
`FROM`|생성할 이미지의 베이스 이미지| 필수 입력
`MAINTAINER`|이미지를 생성한 개발자|도커 1.13이후로 사용 안함, LABEL maintainer 로 사용 가능
`LABEL`|이미지에 메타데이터 추가|여러개 저장 가능
`RUN`|이미지를 만들기 위해 컨테이너 내부에서 실행할 명령|
`ADD`|파일을 이미지에 추가함|DockerFile이 위치한 Context에서 추가함
`WORKDIR`|작업할 디렉토리 지정|윈도우 CMD에서 CD 명령어와 같은 역할
`EXPOSE`|DockerFile의 빌드로 생성된 이미지에서 노출할 포트 설정
`CMD`|컨테이너가 실행될 때마다 실행할 명령어 설정|DockerFile에서 한 번만 사용 가능
`ENV`|DockerFile에서 사용될 환경 변수 지정|
`VOLUME`|빌드된 이미지로 컨테이너 생성 시 호스트와 공유할 컨테이너 내부의 디렉토리 지정|
`ARG`|BUILD 명령어를 실행할 때 추가로 입력을 받아 DockerFile내에서 사용될 변수의 값을 설정|
`USER`|컨테이너 내에서 사용될 사용자 계정의 이름이나 USERID를 설정하면 이후의 명령어는 사용자 권한으로 실행함|
`ONBUILD`|빌드된 이미지를 기반으로 다른 이미지가 DockerFile로 실행될 때 실행할 명령어|
`STOPSIGNAL`|컨테이너가 정지될 때 사용될 시스템 콜의 종류 지정|
`HEALTHCHECK`|이미지로부터 생성된 컨테이너에서 동작하는 어플리케이션의 상태 체크|
`SHELL`|셸 지정|셸은 유닉스와 대화하기 위한 인터프리터, 리눅스는 "/bin/sh -c", 윈도우는 "cmd /S /C"
`COPY`|로컬 디렉토리에서 읽어들인 파일을 이미지에 복사|ADD는 URL 등도 입력 가능, ADD가 좀 더 포괄적이지만 COPY가 조금 더 확실하고 안전함
`ENTRYPOINT`|컨테이너가 시작될 때 수행할 명령 지정|스크립트의 역할도 수행 가능, ENTRYPOINT가 설정돼있으면 CMD는 ENTRYPOINT의 인자 역할

  
책에는 도커 파일의 명령어가 전부 __리눅스__ 로 쓰여 있어서 실습은 못함 ~~솔직히 도커 파일까지 쓸 일이 있을까 의문이긴 함~~