---
title: Windows 10 Team 2020 업데이트 Preview 빌드 설치
description: Surface Hub 운영 체제, Windows 10 Team 2020 업데이트의 최신 업데이트를 지금 사용할 수 있습니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 6d370db0232ae1f93d1ba6b8ff15b5ff2cfa9f10
ms.sourcegitcommit: 19d2a78242777590bd09af3ac6552c07b032e0a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11142907"
---
# Windows 10 Team 2020 업데이트 Preview 빌드 설치 

[Windows 참가자 프로그램](https://insider.windows.com)에서 추가 비용 없이 Surface Hub 운영 체제, **windows 10 Team 2020 업데이트 미리 보기**의 preview 빌드를 사용할 수 있습니다. 

> [!NOTE] 
> Windows 10 팀 2020 업데이트의 최종 공용 릴리스를 지금 사용할 수 있습니다. 자세히 알아보려면 [Windows 10 Team 2020 업데이트](surface-hub-2020-update.md)를 참조 하세요.

Windows 10 Team 2020 업데이트는 Windows 10의 최신 기능과 함께 장치 배포 및 관리 효율성을 대폭 개선 합니다. 새로운 기능에 대해 자세히 알아보려면 다음 블로그 게시물을 참조 하세요. [공개 미리 보기에 대 한 새 Surface HUB OS 업데이트를 해제 했습니다.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) 알려진 문제는 알려진 문제점을 참조 하세요 [. Windows 10 Team 2020 업데이트](surface-hub-2020-team-update-known-issues.md)
 
## 필수 구성 요소

- [Windows 참가자 프로그램](https://insider.windows.com/)을 사용 하 여 등록 합니다.
- Windows 참가자 프로그램의 빠른 채널에서 Windows 10 Team 2020 업데이트 Preview 빌드를 다운로드 합니다.
- Preview 빌드를 설치한 후 필요한 펌웨어 업데이트를 다운로드 합니다. 참고: Windows 참가자 프로그램을 종료 하기로 결정 한 경우에도 펌웨어 업데이트를 제거할 수 없습니다.

## Surface Hub 준비

시작 하기 전에 Surface Hub에 Windows 업데이트에서 최신 업데이트가 있는지 확인 하 고 장치와 연결 된 BitLocker 키를 저장 해야 합니다.

**수동으로 업데이트를 확인 하려면 다음을 수행 합니다.**

1. Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.
2. **업데이트 & 보안**  >  **Windows 업데이트** 를 탐색 한 다음 **업데이트 확인**을 선택 합니다.

자세한 내용은 [Surface Hub에서 Windows 업데이트 관리](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub)를 참조 하세요.

**BitLocker 키를 수동으로 저장 하려면 다음을 수행 합니다.**

1. Surface Hub에 USB 드라이브를 삽입 합니다.
2. Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.
3. **& 보안**  >  **복구**업데이트로 이동 합니다.
4. **BitLocker**에서 **저장**을 선택 합니다. BitLocker 키가 USB 드라이브의 텍스트 파일에 저장 됩니다.

자세한 내용은 [BitLocker 키 저장](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)을 참조 하세요.
 
## Windows 10 Team 2020 업데이트 Preview 빌드 설치

1. Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.
2. **개인 정보 > 진단 & 피드백** 으로 이동 하 고 진단 데이터를 **전체**로 설정 합니다. 일부 지역 또는 조직은 MDM 정책 또는 PPKG 파일을 통해이 설정을 적용 해야 할 수 있습니다.
   - **MDM:** 다음 정책을 설정 합니다. 정수 값이 3 인 **/Vendor/MSFT/Policy/System/AllowTelemetry** :
    
        ![AllowTelemetry 분석을 3으로 설정](images/hub-2020-allow-telemetry.png)

    - **PPKG:** [Ppkg 파일](https://aka.ms/HubTltmtry)을 다운로드 합니다.

3. **업데이트 & 보안**  >  **Windows 참가자 프로그램** 으로 이동한 다음 등록할 **시작** 을 선택 합니다.
4. 메시지에 따라 회사 계정 (권장) 또는 개인 Microsoft 계정을 사용 하 여 Windows 참가자에 등록 합니다. 회사 계정으로 등록 하는 이점에 대 한 자세한 내용은 [비즈니스용 Windows 참가자 프로그램 등록](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)을 참조 하세요.
5. **참가자 설정 선택**에서 **빠른**을 선택 합니다.
6. Surface Hub에서 미리 보기 빌드와 필요한 펌웨어 업데이트를 다음 3 ~ 4 일 동안 자동으로 설치 하도록 허용 합니다. 이 장치는 일상적인 [유지 관리 창](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)에서 자동으로 업데이트를 다운로드 하 고 설치 합니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

- 첫 번째 유지 관리 창에서 Surface Hub는 Windows 업데이트에서 Preview 빌드를 다운로드 하기 시작 합니다.
- 두 번째 유지 관리 기간 동안 장치가 다시 시작 되어 업데이트를 완료 합니다.
- 세 번째 유지 관리 창에서 장치는 필요한 펌웨어 업데이트를 다운로드 하 여 설치 합니다.

> [!IMPORTANT]
> Microsoft는 장치에서 미리 보기 빌드와 필요한 펌웨어 업데이트 설치를 완료할 수 있도록 3-4 일간 Surface Hub를 예약 하는 것이 좋습니다. 이 과정 중 장치를 사용 하는 경우 그래픽, 오디오 및 사용자 인터페이스 문제가 발생할 수 있습니다.

### Preview 빌드 및 필수 펌웨어 업데이트를 수동으로 설치 하도록 선택 하는 경우:

1. Windows 참가자 프로그램에 등록 한 후에는 **설정**  >  **업데이트 & 보안**  >  **Windows 업데이트로** 이동한 다음 **업데이트 확인** 을 선택 하 여 Preview 빌드를 설치 합니다.
2. Preview 빌드를 설치한 후 (최대 14 시간까지 소요 될 수 있음) **지금 다시 시작** 을 선택 하 여 설치를 완료 합니다.
3. 장치가 다시 시작 되 면 **설정**  >  **업데이트 & 보안**  >  **Windows 업데이트로**이동한 다음 **업데이트 확인을 선택 하 여 필요한 펌웨어 업데이트를 설치**합니다.
4. 펌웨어가 설치 되 면 **지금 다시 시작**을 선택 합니다.

> [!WARNING]
> 필요한 펌웨어 업데이트를 설치 하지 않고 Preview 빌드를 설치 하는 경우 그래픽, 오디오 및 사용자 인터페이스 문제가 표시 될 수 있습니다.

> [!NOTE]
> Windows 참가자 프로그램을 종료 하 고 Surface Hub를 이전 버전의 운영 체제로 되돌리려는 경우 먼저 [장치를 재설정](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)해야 합니다. 나중에 장치를 다시 구성 하려면 [첫 번째 실행 프로그램](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) 을 거쳐야 합니다.
 

## 자세히 알아보기

- [알려진 문제점: Windows 10 Team 2020 업데이트](surface-hub-2020-team-update-known-issues.md)
- [공개 미리 보기에 대 한 새로운 Surface Hub OS 업데이트를 해제 했습니다.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [비즈니스용 Windows 참가자 프로그램 시작하기](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)