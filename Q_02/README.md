# 2번 문제

주어진 프로젝트 내에서 제공된 스크립트(클래스)는 다음의 책임을 가진다
- PlayerStatus : 플레이어 캐릭터가 가지는 기본 능력치를 보관하고, 객체 생성 시 초기화한다
- PlayerMovement : 유저의 입력을 받고 플레이어 캐릭터를 이동시킨다.

프로젝트에는 현재 2가지 문제가 있다.
- 유니티 에디터에서 Run 실행 시 윈도우에서는 Stack Overflow가 발생하고, MacOS의 유니티에서는 에디터가 강제종료된다.
- 플레이어 캐릭터가 X, Z축의 입력을 동시입력 받아서 대각선으로 이동 시 하나의 축 기준으로 움직일 때 보다 약 1.414배 빠르다.

두 가지 문제가 발생한 원인과 해결 방법을 모두 서술하시오.

## 답안
##### MoveSpeed 프로퍼티명과 접근하려는 값의 변수 명이 같아 재귀적으로 계속 호출하게 된다.
- 접근하려는 값의 변수명을 프로퍼티명과 다르게 해준다.

##### 이동에 있어 정규화가 되어 있지 않아 대각선으로 이동할 시 상하좌우 이동의 입력값을 모두 받아 속도가 달라지게 된다.
- Normalize()을 통해 플레이어의 이동속도를 일정하게 맞춘다.
