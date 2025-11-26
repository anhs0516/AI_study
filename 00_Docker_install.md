### 도커(Docker) 설치



### 1. 윈도우 도커 다운로드 

 #### 1-1 Windows용 Docker Desktop 설치 파일을 다운로드

 https://docs.docker.com/get-started/get-docker/

 <img width="1884" height="1549" alt="image" src="https://github.com/user-attachments/assets/71ca0dfb-0915-4313-b28c-90d993ac8d52" />

 <img width="1908" height="1528" alt="image" src="https://github.com/user-attachments/assets/65368943-c5cd-42d8-9526-92a79f43010a" />

 #### 1-2 Docker Command로 설치여부 확인

cmd 실행 후 docker --version

 <img width="323" height="46" alt="image" src="https://github.com/user-attachments/assets/e9f249c3-fc2e-4882-96a8-310e885cb631" />

 

### 2. 도커 실행 및 Python 최신 이미지 다운로드 및 실행

powershell을 실행 후 "docker run -it python" 명령어를 통해 최신 python을 다운로드 받고 코드 실행부분을 바로 켜주는 -it 옵션을 통해 코드를 입력할 수 있습니다.




### 문제 발생

윈도우 PC를 재부팅하고 나니 Docker Desktop 아이콘이 켜지지 않네요 

구글 검색해보니 윈도우에서 도커를 키면 이런 일들이 좀 있는 것 같습니다.

해결 메시지는 잘 보이지 않고 매번 지웠다 깔고 하는건 비효율적이라 생각되어 리눅스에 도커 설치해서 해보겠습니다..... 




### 1. 칼리 리눅스 도커 다운로드

우선 sudo apt update를 통해 업데이트 해줍니다

이후 

sudo apt install docker.io 로 도커 다운로드


### 2. Python 최신 이미지 다운로드 및 실행
```
docker run -it python
```

도커에서 python 최신 이미지를 다운받고 바로 실행

<img width="808" height="340" alt="image" src="https://github.com/user-attachments/assets/2b191989-19c1-4a00-8ed0-29595b48d48b" />

<img width="376" height="47" alt="image" src="https://github.com/user-attachments/assets/63b261a4-fb08-4588-9c88-9d568468388f" />


### 3. 이미 만들어놓은 컨테이너를 이용하여 Python 작업 이어나아가기

내가 만들어놓은 컨테이너 ID를 파악

<img width="1228" height="131" alt="image" src="https://github.com/user-attachments/assets/2db3e05f-8a0a-4028-938a-c2029286aaa8" />

만들어놓은 컨테이너 ID를 이용하여 시작 후 코드 입력 가능한 상태로 만들기

```
docker start -ai <컨테이너 ID>
```
위처럼만 하면 python 여러줄 입력불가

```

docker start <컨테이너 ID>
로 컨테이너를 시작 후 

docker exec -it <컨테이너 ID> /bin/bash

```
