# 도로롱의 항해일지

나물볶음이 제작한 DHO Navigator용 **Midnight Rose** 테마 리소스팩입니다.
도로롱 선박, 장미 목적지, 찻잔 경유지와 유형별 거점 마커로 항해 화면을 꾸밉니다.

![도로롱의 항해일지](pack/thumbnail.jpg)

## 받기

[Releases](https://github.com/DHO-Unofficial-Dev/dho-pack-dororong/releases/latest)에서 `dororong-<버전>.dho-pack`을 받습니다.
같은 이름의 `.sha256` 파일로 내려받은 파일의 SHA-256을 확인할 수 있습니다.

## 설치

1. DHO Navigator 2.2.1 이상(3.0.0 미만)을 켭니다.
2. `Navigator 설정 › 리소스팩 › 리소스팩 설치`에서 받은 `.dho-pack` 파일을 고릅니다.
3. 설치한 팩을 켭니다. 직접 옮긴 HUD 위치·크기·투명도는 팩보다 우선합니다.

기존 `도로롱 항해일지` 1.0.0 또는 시험판 1.0.6을 사용했다면 먼저 비활성화하세요.
1.0.1부터 팩 ID는 **`dho.namulmix.dororong`**, 제작자 ID는 `dho.namulmix`입니다.
기존 팩과 ID가 달라 이번 판은 별도 팩으로 설치되며 설정을 자동 이전하지 않습니다.
새 팩을 켠 뒤 정상 표시를 확인하면 예전 팩을 제거할 수 있습니다. 이후 업데이트는 새 ID를 유지합니다.

## 1.0.1 — Navigator 2.2.1 지원

- 팩 이름을 **도로롱의 항해일지**로 변경했습니다.
- 제작자 표시명 **나물볶음**, **Midnight Rose** 디자인과 24px 거점 마커를 유지합니다.
- Navigator 2.2.1 공개 제작 키트의 검사·빌드·아카이브 검증을 통과했습니다.
- 새 버전 확인 주소를 연결했습니다. 앱 시작 때 배포 사이트에 새 버전을 묻고 리소스팩 관리 목록에 안내합니다.
  자동 설치는 하지 않으며 `앱 설정 › 모듈·리소스팩 › 시작할 때 새 버전 확인`에서 끌 수 있습니다.
- 새 버전 확인 기능 때문에 최소 Navigator 버전은 2.2.1입니다. 2.2.0 사용자는 Navigator부터 업데이트하세요.

## 구성

| 구성요소 | 바꾸는 것 |
| --- | --- |
| `navigatorTheme` | Navigator 본창 색 |
| `surfaceTheme` | 정보 HUD, 조향 방향 리본, 중앙 조향 표식 |
| `mapAppearance` | 지도 HUD와 해안선·해역·항해선 색 |
| `markerSet` | 선박·목적지·경유지·거점·개인 표식 |
| `appIcon` | 창 아이콘 |
| `moduleSurfaceTheme` | `org.dho.example.navigation` 예제 모듈의 화면 스타일 |

모듈 스타일은 해당 예제 모듈이 설치된 경우에만 쓰이며 다른 모듈의 화면까지 바꾸지 않습니다.

## 1.0.0

- 항구는 분홍 핀, 개척도시는 라벤더 깃발, 내륙은 민트 산으로 구분합니다.
- 세 거점 마커는 모두 24×24이며 Navigator의 확대·축소 비율을 따릅니다.
- 핀 끝과 깃대 아래가 실제 거점 좌표를 가리키도록 기준점을 맞췄습니다.
- 목적지 장미, 도로롱 선박, 찻잔 경유지와 나머지 마커·화면 색은 유지했습니다.
- Navigator 2.2.0 공개 Pack 도구로 검사·빌드·아카이브 검증을 통과했습니다.

실제 해안선·거점 데이터에 배치한 브라우저 목업으로 비교했습니다. Windows 앱의 설치·활성화와
게임 위 HUD 실화면 검수는 아직 수행하지 않았습니다.

## 직접 빌드

`pack/`은 팩 원본입니다. Node.js 20 이상과
[공개 Pack 제작 키트](https://dhoport.app/navigator/docs/resource-pack/tooling)를 사용합니다.
아래 명령은 제작 키트 폴더에서 실행하며 저장소 경로를 환경에 맞게 바꿉니다.

```sh
node tools/validate-pack.mjs /path/to/dho-pack-dororong/pack
node tools/build-dho-pack.mjs /path/to/dho-pack-dororong/pack /path/to/dororong-1.0.1.dho-pack
node tools/verify-archive.mjs /path/to/dororong-1.0.1.dho-pack
node tools/check-update-response.mjs https://raw.githubusercontent.com/DHO-Unofficial-Dev/dho-pack-dororong/main/update-check.json --kind pack --id dho.namulmix.dororong
```

## 라이선스

제작자: 나물볶음. 원본의 별도 재배포 허락 없는 라이선스 조건을 유지합니다.
캐릭터 관련 권리는 각 권리자에게 있으며, 자세한 범위는 [LICENSE](LICENSE)를 참고하세요.
