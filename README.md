# and-a-z

- USB로 안드로이드를 연결했을 때 데이터를 껐다가 켜는 것을 PC프로그램으로 제어

```adb
adb shell
svc data disable
svc data enable
```
  명령어를 script 파일로 작성후에, bat으로 기기로 복사 후 실행하도록 짜놓으면 bat을 실행할때마다 data를 껐다가 켜도록 할 수 
