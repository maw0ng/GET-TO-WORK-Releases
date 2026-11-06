# GET TO WORK — Windows 다운로드

할 일 · 집중 타이머 · 3D 데스크톱 펫 · 작업방 · 레트로 미니홈피를 한 앱에서.

이 저장소는 **설치 파일 배포 전용**입니다. 소스 코드는 공개하지 않습니다.

## 다운로드

[**최신 버전 받기 (Releases)**](https://github.com/maw0ng/GET-TO-WORK-Releases/releases/latest) → `GET-TO-WORK-Setup-<버전>.exe`

- Windows 10 / 11 (64비트)
- 설치는 내 계정에만 됩니다 (관리자 권한 필요 없음)
- 한 번 설치하면 새 버전은 앱이 알려 주고 자동으로 업데이트됩니다

## 파일 확인 (선택)

각 릴리스에는 `SHA256SUMS.txt`가 함께 있습니다. PowerShell에서:

```powershell
Get-FileHash .\GET-TO-WORK-Setup-1.0.0.exe -Algorithm SHA256
```

출력된 값이 `SHA256SUMS.txt`의 값과 같으면 받은 파일이 손상되거나 바뀌지 않은 것입니다.

자동 업데이트는 앱이 직접 확인합니다:
`latest.yml`(업데이트 정보)은 배포자의 Ed25519 키로 서명되어 있고(`latest.yml.sig`), 앱은 서명·버전·파일 이름·SHA-512가
모두 맞는 경우에만 설치합니다. 이 저장소가 아닌 곳의 파일은 설치하지 않습니다.

## Windows 경고에 대해

- **"Windows의 PC 보호" (SmartScreen)**: 현재 설치 파일은 코드 서명 인증서로 서명되어 있지 않아, 다운로드가 아직 많지 않은
  동안 경고가 나올 수 있습니다. 위의 방법으로 파일을 확인한 뒤 `추가 정보 → 실행`을 누르면 설치됩니다.
- **백신 경고**: 백신이 파일을 위협으로 표시하면 실행하지 말고 [이슈](https://github.com/maw0ng/GET-TO-WORK-Releases/issues)로 알려 주세요. 백신을 끄거나 예외를
  추가하라고 안내하지 않습니다.

## 제거

`설정 → 앱 → GET TO WORK → 제거`. 할 일·기록 같은 내 데이터는 기본으로 남겨 두며, 제거할 때 지울지 물어봅니다.
서버에 저장된 계정·코인·인벤토리·미니홈피는 PC와 상관없이 유지됩니다.

## 릴리스 파일

| 파일 | 설명 |
|---|---|
| `GET-TO-WORK-Setup-<버전>.exe` | 설치 파일 |
| `GET-TO-WORK-Setup-<버전>.exe.blockmap` | 차등 업데이트용 정보 |
| `latest.yml` / `latest.yml.sig` | 자동 업데이트 정보와 서명 |
| `SHA256SUMS.txt` | 파일 체크섬 |
