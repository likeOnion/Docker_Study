컨테이너 로깅 : 컨테이너의 로그를 관리하는 것, 표준 출력(StdOut)과 표준 에러 로그(StdErr) 출력을 기본적으로 지원함

형식 : docker logs (컨테이너 이름)

    -옵션 : --tail 10 (끝에서 10줄만 확인), --since 유니티타임 (유니티 타임 이후의 로그 출력), -t(타임 스탬프 확인), -f(실시간)

컨테이너 로그는 JSON형대로 도커 내부에 저장

--log-driver=(드라이버 이름) 으로 로그 드라이버 변경 가능

--log-opt로 옵션 변경 가능

    -옵션 : syslog-address(컨테이너 접근 주소), tag(로그와 함꼐 저장될 태그), syslog-facility="(퍼실리티)" (저장될 로그 종류, 기본은 daemon이며 mail, kern user 등 사용 가능)

syslog를 통해 로그 실습 진행(syslog는 유닉스 계열 로그 관리)

fluentd와 mongodb로 서버 개설, DB연동 데이터 저장 실습헀는데 서버 생성까지는 했는데 DB연동 못함