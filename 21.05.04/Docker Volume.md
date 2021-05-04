도커 이미지 위에 도커 컨테이너가 얹혀지는 형식으로 컨테이너가 생성됨 : 컨테이너의 운용 데이터나 로그 등은 컨테이너에 저장 됨 - 컨테이너 삭제 시 같이 삭제 됨

도커 볼륨을 이용해서 해당 로그들을 Persistant하게 변경할 수 있음 : 호스트와 볼륨을 공유할 수 있음

방식 1 : 호스트와 볼륨 공유
    -docker run -v (호스트 디렉토리/파일):(컨테이너 디렉토리/파일)
    
     호스트와 볼륨 공유 시 호스트 디렉토리를 컨테이너에 복사해 오는 형식으로 동작함

방식 2 : 컨테이너끼리 볼륨 공유
    - docker run --volume-from (볼륨을 사용하고 있는 컨테이너 이름) : 볼륨을 사용하고 있는 컨테이너의 볼륨 디렉토리를 복사해 옴

방식 3 : docker volume 사용
    - docker volume create --name (이름) 로 volume 생성 가능, 로컬 디렉토리처럼 사용 가능
    
     -v (생성한 볼륨 이름 ):(컨테이너 디렉토리) 로 사용 가능

docker inspect --type (타입) (이름) : 해당 도커의 구성 단위의 정보 확인 가능, image, volmue 등에 동일하게 사용 가능

    -ex) docker inspect --type volume myvolume

mount : -v와 동일한 용도로 사용 가능함

    - --mount 로 사용 가능, type은 볼륨을 공유할 떄는 volume, 호스트 디렉토리를 컨테이너 내부로 마운트하는 경우는 bind

     ex) docker run -i -t --name mount_container --mount type=bind source = (호스트 디렉토리) target=(컨테이너 디렉토리)