# PRO4500 LightCrafter 공통 제어 모듈

이 저장소는 PRO4500 / LightCrafter 4500 계열 라이트엔진을 제어하는
공통 소스 모듈입니다. Android 휴대폰 카메라 기반 작업 공간과 XIMEA UV
카메라 기반 작업 공간에서 `GUI/` 경로의 Git submodule로 사용합니다.

## 출처

이 공통 모듈과 이를 사용하는 parent 작업 공간들의 초기 PRO4500/
LightCrafter 4500 제어 뼈대는
[lee-lab-skku/PRO4500_Control_System](https://github.com/lee-lab-skku/PRO4500_Control_System)을
바탕으로 확장되었습니다.

## 포함 범위

이 저장소에는 두 작업 공간에서 공통으로 사용하는 라이트엔진 제어 계층을
둡니다.

- DLPC350 명령/API 소스
- DLPC350 USB 전송 소스
- LightCrafter 4500 GUI 리소스
- 제어 빌드에 필요한 HIDAPI 소스

카메라 동기화, 스캔 순서, 저장 정책처럼 작업 공간마다 달라지는 코드는
parent 저장소에 남겨 둡니다.

## 사용하는 parent 저장소

- Android 휴대폰 카메라 기반 작업 공간:
  [lee-lab-skku/PRO4500_Android_CONTROL](https://github.com/lee-lab-skku/PRO4500_Android_CONTROL)
- XIMEA UV 카메라 기반 작업 공간:
  [lee-lab-skku/PRO4500_CONTROL_ximea](https://github.com/lee-lab-skku/PRO4500_CONTROL_ximea)

## Submodule 사용 방법

parent 저장소에서는 이 저장소를 `GUI/` 경로에 submodule로 둡니다.

처음 clone할 때는 submodule까지 함께 받습니다.

```bash
git clone --recurse-submodules <parent-repo-url>
```

이미 clone한 저장소라면 다음 명령으로 submodule을 초기화합니다.

```bash
git submodule update --init --recursive
```

이 저장소의 공통 라이트엔진 코드를 수정한 뒤에는 parent 저장소에서
`GUI` submodule pointer도 함께 갱신해 커밋해야 합니다.
