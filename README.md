# protobuf-c
https://github.com/protobuf-c/protobuf-c

# ProtoBuf-C 사용법 

(공통사항)
1. https://www.msys2.org/ 에서 msys2 다운로드 및 업그레이드 수행 (다운로드/업그레이트 홈페이지 참고)
2. msys2.exe 실행하고 pacman -S base-devel  통해서 개발툴 모두 설치 
3. 윈도우 환경변수 path에 msys64\mingw64\bin\ 와 msys64\usr\bin\ 경로 추가 

(MinGW에서 빌드할 경우)
1. msys64\home\user\ 디렉토리에 https://github.com/protobuf-c/protobuf-c 에서 git 소스 체크 아웃 
2. mingw64.exe 실행 
3. https://github.com/protobuf-c/protobuf-c 에 설명과 같이 ./autogen.sh && ./configure && make && make install 실행 
  3.1 .configure 과정에서 아래와 같은 에러가 발생하면, 컴파일러를 설치 
    configure: error: in `/home/admin/protobuf-c-master/protobuf-c-master':
    configure: error: no acceptable C compiler found in $PATH
    See `config.log' for more details
  3.2 c 컴파일러 설치 방법 
   

4. (3)번에 의해 protobuf-c의 라이브러리와 실행파일이 생성됨 
5. /t 디렉토리(테스트 폴더)에서 protoc --c_out=. test-proto3.proto
6. /t 디렉토리(테스트 폴더)에서 생성된 c파일로 실행 파일을 만들 경우 gcc -o test-proto3 test-proto3.c test-proto3.pb-c.c
-lprotobuf-c

(STM 프로젝트에서 빌드할 경우)
1. msys2.exe 실행하고 pacman -S mingw-w64-x86_64-protobuf-c 을 통해 protobuf-c 패키지 설치 
2. (1)번에 의해서 protoc 파일과 라이브러리가 설치됨
3. 사용자가 원하는 기능이 포함된 proto 파일 생성
4. 윈도우 명령어창에서 protoc --c_out=. *.proto 
5. xxx.c, xxx.h 파일 생성 
6. xxx.c, xxx.h 생성 폴더에 protobuf-c.c protobuf-c.h 파일 복사 또는 빌드경로에 소스파일 있는 디렉토리 추가
7. 프로젝트 빌드
