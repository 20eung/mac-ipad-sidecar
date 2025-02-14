# macOS Sonama 14에서 Mac mini에서 iPad를 단일 모니터로 사용하는 방법

## 반드시 필요한 준비물

### 1. macOS Monterey 12.6 버전부터 SideCar에 연결하기 위해서는 반드시 HDMI 또는 Thunderbolt를 통해 **모니터 연결 필요**
- 반드시 필요한 준비물: HDMI 더미
- 대략 1500원선에서 구입가능하며, 작은 크기로 구매
![hdmi-dummy.png](/Files/hdmi-dummy.png)

## macOS 설정하기
### 2. 유니버설 컨트롤(Universal Control) 끄기
- 유니버설 컨트롤이 켜져있는 경우 사이드카(SideCar) 연결이 안됨
- 시스템 설정 > 디스플레이 > 고급... > SideCar Off
  ![sidecar-off.png](/Files/sidecar-off.png)

### 3. SideCar로 사용할 iPad 이름 확인 및 SideCar 연결 확인
- 시스템 설정 >> 디스플레이 >> 디스플레이 추가에서 iPad 이름 확인
  ![display-add.png](/Files/display-add.png)

- 디스플레이 추가 후 연결해보기
  ![display-add-test.png](/Files/display-add-test.png)

### 4. SideCar 자동 연결 프로그램 내려받기 및 iPad 이름으로 파일 이름 변경
- 새로운 SideCar 자동 연결 프로그램 다운로드
- [https://kimsungjin.tistory.com/686](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbFk2b3JydndIdmZ4RFNzbGNSZDRuY0dEZmdqQXxBQ3Jtc0ttZFNhejk5S2N0aG51UzR2ekhZVnNzc1Q4QTVmNk1EMkNOWmE1ODhFbm8tM3N2VndSMjZ1ZlpyaERjOFhEb0lKQ1JFdXlUcGFKZ0lHNE9jTjgzdFhwS0owOWdzaXBTOWJxTWRVczUzbUJGNzFyOWNxMA&q=https%3A%2F%2Fkimsungjin.tistory.com%2F686&v=Iz-xkxqjTeg)
- 압축파일을 해제하여 응용 프로그램에 붙여넣기
- 파일이름 SideCar_Sonoma.app 을 iPad 이름으로 변경

### 5. SideCar 자동 연결 프로그램 실행 테스트와 경고 메시지 해결
- SideCar 자동 연결 프로그램을 처음 실행하면 게이트키퍼에서 경고창이 뜨면 `확인` 클릭
- 시스템 설정 >> 개인정보 보호 및 보안 >> 보안 >> `그래도 열기` 클릭
  ![sidecar-app-open-security-ignore.png](/Files/sidecar-app-open-security-ignore.png)

- 관리자 암호 입력 후 `설정 수정` 클릭
- 다시 게이트키퍼 경고창이 뜨면 `열기` 클릭하면 2개의 경고창이 뜸
- `AppleScript 실행` 경고 메시지는 '확인' 클릭
- `손쉬운 사용 접근 권한` 경고 메시지는 `시스템 설정 열기` 클릭 후 SideCar 자동 연결 프로그램을 켬
  ![sidecar-app-accessibility-permit.png](/Files/sidecar-app-accessibility-permit.png)

- 시스템 설정 변경이므로 관리자 암호 입력 후 `설정 수정` 클릭
- 시스템 설정 >> 개인정보 보호 및 보안 >> 손쉬운 사용
- 손쉬운 사용 설정 마친 후 다시 SideCar 자동 연결 프로그램을 실행하면 `System Events`를 제어하려고 한다는 경고창이 뜨면 `확인` 클릭
- `시스템 설정`을 제어하려고 한다는 경고창이 뜨면 `확인` 클릭
- 잠시 후 화면이 깜빡이며 SideCar에 연결이 되고 시스템 설정은 자동으로 종료됨
- 시스템 설정 >> 개인정보 보호 및 보안 >> 자동화
  ![sidecar-app-accessibility-automation.png](/Files/sidecar-app-accessibility-automation.png)

- 모든 설정 완료 후 SideCar 자동 연결 프로그램 종료 후 다시 실행하여 경고메시지 없이 SideCar에 연결되는지 확인

### 6. FileVault 끄기 및 자동 로그인 설정
- SideCar를 모니터로 사용하려는 경우 로그인을 해야 사용할 수 있음
- 로그인 전까지는 SideCar 화면을 볼 수 없음
- 그래서 자동 로그인을 설정해야 함
- 자동 로그인을 설정하기 위해서는 반드시 FileVault를 꺼야 함
- 시스템 설정 >> 개인정보 보호 및 보안 >> FileVault >> `끄기...`
- 시스템 설정을 변경하는 것이므로 관리자 암호를 입력한 후 `잠금 해제` 클릭
- FileVault를 정말 끌 것인지 물어보는데 `암호화 끄기` 클릭
- 시스템 설정 종료 후 다시 실행
- 시스템 설정 >> 사용자 및 그룹 >> 다음으로 자동 로그인 >> 계정 선택
  ![auto-login.png](/Files/auto-login.png)
  
- 시스템 설정을 변경하는 것이므로 관리자 암호를 입력한 후 `잠금 해제` 클릭
- 자동 로그인 계정의 암호를 입력하고 `확인` 클릭

### 7. SideCar 자동 연결 프로그램을 로그인 자동 실행 항목에 등록
- 시스템 설정 >> 일반 >> 로그인 항목 및 확장 프로그램 >> 로그인 시 열기 >> `+`
- 응용 프로그램에서 SideCar 자동 연결 프로그램을 추가
  ![sidecar-app-login-items.png](/Files/sidecar-app-login-items.png)

### 8. 최종 테스트
- 1차 테스트
	- 모니터가 연결된 상태에서
	- SideCar 자동 연결 프로그램을 실행하여
	- 잘 되는지 수 차례 확인
- 2차 테스트
	- 시스템 종료한 다음
	- 모니터 제거 후
	- HDMI 더미를 연결한 상태에서
	- 전원을 켜고 테스트 진행
	- SideCar 연결시도 음성 안내 후 iPad에서 macOS 화면 보이면 정상
	- SideCar 연결 전에 iPad를 켜서 잠금해제 상태를 유지하는 것이 좋음

---
## Reference
1. https://youtu.be/Iz-xkxqjTeg?si=KakZrRgmqhRVJwgX
 
