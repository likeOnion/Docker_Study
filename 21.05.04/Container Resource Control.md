컨테이너의 자원을 제한하지 않을 경우 컴퓨터에 과부하가 발생해 오히려 호스트가 멈출 수도 있음, 따라서 컨테이너에 적절한 제한을 두는 게 효율적임

docker update (변경사항) (컨테이너 이름) 을 통해 생성된 컨테이너 옵션에 변경을 줄 수 있음

1. 메모리

    --memory = "(할당할 양)"

        -ex) --memory="1g"
    
    --memory-swap-"(할당할 양)" 을 통해 메모리가 적어서 에러가 발생하는 경우 추가적으로 할당할 수 있음, 보통 기존 할당량의 2배

        -ex) --memory="1g" --memory-swap="2g"

2. CPU

    --cpu-shares 1024 : 시스템에 존재하는 cpu 중 얼마나 사용할지 설정, default 1024, 이는 cpu 1의 비중

    --cpuset-cpu 0 : 사용할 cpu 지정, 0부터 시작

    --cpu-period, --cpu-quota : cpu 주기 설정,주기가 줄어들면 성능 감소 :: 알아만 둬

    --cpus 0.5 : cpu 직접 할당 0.5는 전체 cpu의 50% 사용한다는 뜻

3. Block I/O (알아만 두기)

    --device-write/read-bps (디바이스):(값) : 초당 작업 제한

    --device-write/read-iops (디바이스):(값) : 초당 i/o 제한
