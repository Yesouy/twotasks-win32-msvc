!-- 영상을 따라하기 전에 vscode에서 c/c++ 빌드 환경 만들 수 있게 해둬야 해! 이건 인터넷에 검색하면 잘 나오니까 굳이 설명하진 않을게
그렇게 환경을 설정한 뒤에 워크스페이스를 만들어
1. 영상 주인의 깃에서 zip다운받은 후에 src, include, .vscode 폴더만 내 워크스페이스에 붙여넣어
2. src과 include는 건드릴 필요가 없고 우리가 신경써야 할건 .vscode에 있는 파일들이야
3. .vscode의 setting.json 파일은 필요없어
4. 영상 속에서 깃 클론 부분만 제외하고 따라하기
5. 그러면 오류가 날텐데 여기서부터 본인 컴퓨터에 맞춰서 고쳐나가기
5-1. c_cpp_properties.json에서 compilerPath를 본인 경로로 바꾸기
5-2. 시스템 환경변수에 path에 compilerPath 상위 폴더 경로 추가하기
5-3 launch.json에서 program 경로를 ${workspaceFolder}/build/main.exe로 바꾸기
6. main 코드 교수님 피피티 참고해서 고치기
