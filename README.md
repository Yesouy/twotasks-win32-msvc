Vscode와 FreeRTOS 환경 세팅하고 빌드에 실행해보기

1. vscode와 build tool 다운받기
Visual Studio Code: [https://code.visualstudio.com/]
(파일 > 기본 설정 > 설정 > "원격 측정: 원격 측정 수준" Enable)
Visual Studio Build Tools: [https://aka.ms/vs/17/release/vs_BuildTools.exe]
(c++ build)

2. Visual Studio Code 열고 Extention에서 "C/C++ Extension Pack" Enable

3.git이랑 FreeRTOS 다운받기
Git [https://gitforwindows.org/]
FreeRTOS  [https://freertos.org] -- (압축 해제 위치 C:\Users\컴퓨터 이름)

4. 윈도우 FreeRTOS 환경변수 설정 --
  FreeRTOS 파일 위치 복사
  "시스템 변수(S)"에 새로만들기
  변수: FREERTOS_PATH
  값: 예시)C:\Users\컴퓨터 이름\FreeRTOSv202212.01))

5. 윈도우 검색에 "Developer Command Prompt" 검색해서 맨위에 cmd 앱 실행

6. 프롬프트에 code . 적고 엔터

7. Clone 레포지토리 눌러서 [https://github.com/vsserafim/twotasks-win32-msvc.git] 복붙하고 엔터

8. 파일 탐색기 켜지면 원하는 경로에 프로젝트 폴더 생성하고 그곳에 select

9. src, include, .vscode 폴더 남겨놓고 setting.json 파일 삭제

10. c_cpp_properties.json에 compilerPath를 본인 경로로 바꾸기

11. 시스템 환경변수가서 "(컴퓨터 이름)에 대한 사용자 변수(U)" Path 편집

12. c_cpp_properties.json에 compilerPath 상위 폴더 경로 Path 맨위에 추가
예시) C:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\VC\Tools\MSVC\14.39.33519\bin

13. launch.json에서 program 경로를 ${workspaceFolder}/build/main.exe로 바꾸기

14. main.c 코드 원하는 코드로 짜기


++ 빌드하고 실행하기 ++
1. New folder로 "build" 폴더 생성

2. "main.c" 파일에서 ctrl + Shift + B (Run Build)

3. 빌드 성공하면 Build finished successfully 뜨면서 "build" 폴더에 파일들 생성됨
※ 오류가 나면 Problems에서 읽어 보고 해결하기 보통 FreeRTOSConfig.h 설정값을 바꾸라는 오류일거임 Maybe.. ※

4. 그중에 "main.exe" 파일 우클릭하고 Open in integrated Terminal 눌러서 터미널 켜기

5. 터미널에 .\main.exe 치면 실행 완료 ( 터미널에서 ctrl + c 누르면 멈춤 )



Reference -- https://www.youtube.com/watch?v=cY-lirISLcs&t=42s
