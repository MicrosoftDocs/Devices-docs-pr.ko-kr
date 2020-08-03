---
title: 화면 전원을 켤 때 절전 모드 해제를 사용 하는 방법
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: Surface 장치에서 절전 모드 해제 기능을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 설명 합니다.
keywords: 업데이트, 배포, 드라이버, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903021"
---
# Surface 장치에서 절전 모드 해제

배터리를 절약 하기 위해 화면 장치를 책상 밖으로 끄거나 최대 절전 모드로 설정 하 여 켤 수 있습니다. 이러한 디바이스의 관리 효율성을 높이기 위해 절전 모드 해제 기능을 사용 하면 전원에 다시 연결 되었을 때 호환 가능한 표면 장치가 자동으로 시작 됩니다. 전원을 켤 때 절전 모드를 사용 하려면 Surface UEFI 구성자 또는 UEFI 관리자를 통해 Surface MM (Surface Enterprise Management Mode)를 사용 해야 합니다.

Wake on 전원은 다음 장치에서 사용할 수 있는 기능입니다.

- Surface Book 3
- Surface Pro 7
- Surface 노트북 3
- Surface Pro X 

## 개요 및 전제 조건

Surface UEFI 구성자를 사용 하 여 대상 장치에 배포 하기 위해 Windows Installer. msi 패키지에 저장 되는 개별 UEFI 설정을 구성할 수 있습니다. 

> [!NOTE]
> 이 문서에서는 사용자가 SEMM 사용을 잘 알고 있다고 가정 합니다. 자세한 내용은 [Surface Enterprise 관리 모드 (SEMM)](surface-enterprise-management-mode.md) 설명서를 참조 하세요.

## 절전 모드 해제 기능을 사용 하도록 설정 하려면

1.  [SURFACE UEFI 구성자](https://www.microsoft.com/download/confirmation.aspx?id=46703)의 최신 버전을 다운로드 합니다.
2.  Surface device에 관리자로 로그인 하 고, **SURFACE UEFI Configurator**를 열고, **surface Devices**를 선택한 후 **다음**을 선택 합니다.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Surface 장치를 선택 하 고 다음을 선택 합니다.":::
3.  **시작** 을 선택 하 고 **구성 패키지** 에서 **만들기**를 선택 합니다.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="구성 패키지 만들기를 선택 합니다.":::
4.  **인증서 보호** 를 선택 하 고 인증서 pfx 파일을 추가 합니다. 비밀 번호를 입력 한 후 **다음**을 선택 합니다. 적절 하 게 **암호 보호**를 추가 하 고 **다음**을 선택 합니다.
5.  **대상으로 지정할 표면 유형 선택** 페이지에서 대상 장치를 적절 하 게 선택 합니다. 예를 들어 **Surface Pro 7**이 있습니다.
6.  **고급 기능** 페이지에서 **절전 모드 해제** 를 선택 하 고 켜기 ( **on**)로 설정 합니다. **다음**을 선택합니다.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="전원을 켠 후 절전 모드 해제를 선택 합니다."::: 
7.  **성공** 페이지에서 **종료**를 선택 합니다. 장치에 대 한 설정을 처음 제공 하는 경우 인증서 손도장의 마지막 두 문자를 제공 하 라는 메시지가 표시 됩니다. 
8.  .Msi 패키지를 저장 합니다. 

## MSI 패키지 적용 

Microsoft 끝점 구성 관리자와 같은 소프트웨어 배포 도구를 사용 하 여 네트워크를 통해 장치에 MSI 패키지를 적용할 수 있습니다. 이 절차에는 로컬 컴퓨터에 패키지를 설치 하는 단계가 포함 되어 있습니다. 

1.  관리자 권한 명령 프롬프트를 열고 .msi 파일의 전체 경로를 입력 하 여 .msi 패키지를 실행 합니다. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  **경고** 대화 상자에서 **확인** 또는 필요에 따라 Bitlocker 사용 안 함을 선택 합니다.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="확인 또는 필요에 따라 Bitlocker 사용 안 함을 선택 합니다.":::
3.  시작 페이지에서 **다음** 을 선택 하 여 패키지를 실행 하 고 새로 구성 된 UEFI 설정을 적용 합니다.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="시작 페이지에서 다음을 선택 합니다.":::
4.  장치를 다시 시작 합니다. 

이제 Wake on 전원이 구성 되었습니다. 설정을 테스트 하려면 장치를 끄고 전원 케이블을 뽑은 다음 전원을 다시 연결 합니다. 장치가 자동으로 시작 됩니다. 

## 추가 정보

자세한 내용은 다음 문서를 참조 하세요. 

- [Surface Enterprise 관리 모드](surface-enterprise-management-mode.md)
- [Surface 장치에 대 한 Wake on LAN](wake-on-lan-for-surface-devices.md)

그래도 문제가 해결되지 않을 경우 [Microsoft 커뮤니티](https://answers.microsoft.com/)를 참조 하세요.