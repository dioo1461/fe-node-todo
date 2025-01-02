# fe-node-todo

## 설명

터미널에서 간단한 todo list를 관리할 수 있는 프로그램입니다.

## 구현

- TODO 추가
  - 이름, 마감일을 입력받아 TODO를 추가합니다.
  - 마감일은 `YYYY-MM-DD` 형식으로 입력받으며, 형식이 잘못된 경우 오류 메시지를 출력합니다.
- TODO 목록 조회
  - 현재까지 추가된 TODO 목록을 조회합니다.
  - TODO 목록은 이름, 마감일로 구성되어 있습니다.
- TODO 수정
  - 수정할 TODO의 번호를 입력받아 이름, 마감일을 수정할 수 있습니다.
- TODO 완료
  - 완료할 TODO의 번호를 입력받아 완료 처리할 수 있습니다.
- TODO 저장
  - File System을 이용해 TODO 목록을 저장할 수 있습니다.
  - 프로그램을 종료한 후에도 TODO 목록을 유지할 수 있습니다.

## 고찰

### readline.question 사용

- 터미널을 통해 사용자의 입력을 받아 TODO를 추가하거나 수정할 때 사용했습니다.
- `readline.on`을 통해 입력을 처리할 때, 여러 개의 입력을 받아야 하는 경우 이를 처리하지 않고 넘어가는 문제가 있었습니다.
- 이를 해결하기 위해 `readline.question`을 사용했습니다.

### File System 연동

- TODO 목록을 저장하고 불러오기 위해 File System을 사용했습니다.
- TODO 목록은 JSON 형식으로 `data.json` 파일에 저장됩니다.

## 추가 고려 사항

### 기능 추가

- TODO 삭제
  - TODO 목록에서 특정 TODO를 삭제할 수 있도록 구현할 수 있습니다.
- TODO 검색
  - TODO 목록에서 특정 이름을 가진 TODO를 검색할 수 있도록 구현할 수 있습니다.

### 구조 개선

- `Todo` 클래스 추가
  - `Todo` 클래스를 추가해 TODO의 이름, 마감일, 완료 여부를 관리할 수 있습니다.
  - `Todo` 클래스를 통해 TODO의 정보를 관리하고, `TodoManager` 클래스에서 TODO 목록을 관리할 수 있습니다.
