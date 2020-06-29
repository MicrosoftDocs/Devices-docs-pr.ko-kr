---
title: Surface 장치에 대한 모범 사례 전원 설정
description: 이 항목에서는 최적의 전원 설정을 유지 관리 하기 위한 모범 사례 권장 사항과 Surface에서 전원 관리 환경을 간소화 하는 방법에 대해 설명 합니다. 이 문서는 Surface Pro 7, Surface Pro X 및 Surface 노트북 3을 비롯 하 여 현재 지원 되는 모든 표면 장치에 적용 됩니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2019
ms.openlocfilehash: 73a74dc05a5a6929fa6360e04aac5d342b9c06a8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834660"
---
# Surface 장치에 대한 모범 사례 전원 설정

Surface device는 작업 부하에 최적화 된 효율적인 환경을 제공 하기 위해 모바일 장치 에너지 소비량의 최신 발전을 활용 하도록 디자인 되었습니다. 사용자가 수행 하는 작업에 따라 서피스는 개별 하드웨어 구성 요소에 대 한 전력 흐름을 동적으로 미세 조정 하 여, S0ix (저전원 유휴 상태)로 반환 하기 전에 들어오는 전자 메일 또는 네트워크 트래픽과 같은 백그라운드 작업을 일시적으로 시스템 구성 요소를 처리 합니다.

## IT 관리자를 위한 권장 사항 요약

조직의 Surface 디바이스에서 Surface power 최적화 기능을 완전히 활용할 수 있도록 하려면 다음을 수행 합니다.

-  Windows Update 또는 Surface Driver 및 펌웨어 MSI에서 최신 드라이버와 펌웨어를 설치 합니다. 이렇게 하면 기본적으로 분산 전원 관리 (라고도 함 power profile)가 만들어지고 최적의 전원 설정을 구성 합니다.  자세한 내용은 [Surface driver 및 펌웨어 업데이트 관리 및 배포](manage-surface-driver-and-firmware-updates.md)를 참조 하세요.
- 사용자 지정 전원 프로필을 만들거나 기본 UI (**시스템**  >  **전원 & 절전 모드**)에서 표시 되지 않는 고급 전원 설정을 조정 하지 않도록 합니다.
- 네트워크를 통해 디바이스의 전원 프로필을 관리 해야 하는 경우 (예: 고도로 관리 되는 조직), powercfg command 도구를 사용 하 여 Surface 디바이스의 공장 이미지에서 전원 관리를 내보낸 다음 Surface 디바이스의 프로비저닝 패키지로 가져옵니다. 

    >[!NOTE]
    >동일한 유형의 Surface 장치에서 전원 계획만 내보낼 수 있습니다.  예를 들어 Surface 노트북에서 전원 관리를 내보내고 Surface Pro에서 가져올 수는 없습니다.  자세한 내용은 [전원 설정 구성을](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings)참조 하세요.

- 기존 전원 관리 정책 설정에서 Surface 디바이스를 제외 합니다. 

## Background

Surface에서 전원 관리를 구현 하는 방법은 일련의 절전 상태를 통해 전원을 점진적으로 감소 시키고 끄는 이전 OS 표준과 크게 다릅니다. 예를 들어 S1, S2, S3 등으로 순환 합니다.

대신, Surface에는 레거시 절전 모드 및 에너지 소비량 기능을 사용 하는 사용자 지정 전원 프로필로 이미지를 저장 하 여 최신 대기 기능 및 동적 미세 조정과 함께 제공 됩니다. 이 사용자 지정 전원 프로필은 Surface Serial Hub 드라이버와 시스템 집계 모듈 (SAM)을 통해 구현 됩니다. SAM 칩은 Surface device power-정책 소유자 역할을 하며, 알고리즘을 사용 하 여 최적의 전원 요구 사항을 계산 합니다. Windows 파워 관리자와 함께 작동 하 여 하드웨어 구성 요소가 작동 하는 데 필요한 정확한 전력이 할당 되거나 제한 됩니다. 이 문서는 Surface Pro 7, Surface Pro X 및 Surface 노트북 3을 비롯 하 여 현재 지원 되는 모든 표면 장치에 적용 됩니다.

## Surface에서 사용자 지정 전원 프로필 활용

Surface 디바이스의 전원 옵션으로 이동 하면 단일 전원 계획을 사용할 수 있는 것으로 표시 됩니다. 이는 사용자 지정 전원 프로필입니다. 고급 전원 설정으로 이동 하면 Windows 10을 실행 하는 일반 PC와 비교 하 여 훨씬 더 많은 전원 옵션의 하위 집합을 볼 수 있습니다. 일반 장치와 달리 Surface에는 이러한 전원 옵션을 관리 하는 펌웨어와 사용자 지정 구성 요소가 있습니다.


## 최신 대기 모드

Algorithmically 임베디드 사용자 지정 전원 프로필을 사용 하면 smartphone의 일반적인 인스턴트 온/인스턴트 끄기 기능에 대 한 낮은 전원 상태를 유지 하 여 Surface에 대 한 최신 대기 연결을 사용할 수 있습니다. 가장 깊은 런타임 유휴 플랫폼 상태 (DRIPS) 라고도 하는 S0ix는 Surface 디바이스의 기본 전원 모드입니다. 최신 대기 모드는 두 가지입니다.

- **연결 된 대기 상태** 전자 메일, 메시지, 클라우드 동기화 데이터, 연결 된 대기 시간에 대 한 최신 배달의 기본 모드는 Wi-fi를 유지 하 고 네트워크 연결을 유지 합니다.

- **연결이 끊긴 상태** 연장 배터리 수명의 선택 모드, 연결이 끊긴 후에는 Wi-fi, Bluetooth, 관련 네트워크 연결을 해제 하 여 동일한 즉각적인 경험을 제공 하 고 전력을 절약 합니다.

최신 대기 상태에 대해 자세히 알아보려면 [Microsoft 하드웨어 개발자 센터](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)를 참조 하세요.

## Surface에서 전원 관리 환경을 간소화 하는 방법 

Surface는 사용자가 전원 관리 환경을 최적화 하는 데 도움이 되도록 다음과 같은 기능을 통합 합니다.

- [단일 전원 계획](#singular-power-plan)

- [간단한 전원 설정 사용자 인터페이스](#simplified-power-settings-user-interface)

- [Windows 성능 전원 슬라이더](#windows-performance-power-slider)

### 단일 전원 계획

Surface는 사용자 지정 전원 관리를 만들거나 수동으로 전원 설정을 구성할 필요가 없도록 하는 효율적인 power management 환경을 위해 디자인 되었습니다. Microsoft는 표준 Windows 빌드에서 여러 전원 계획을 대체 하는 단일 전원 관리 (분산)를 제공 하 여 사용자 환경을 간소화 합니다.

### 간단한 전원 설정 사용자 인터페이스

Surface는 모범 사례 전원 설정 권장 사항으로 accord에서 간소화 된 UI를 제공 합니다. 일반적으로 기본 사용자 인터페이스에 표시 되는 설정만 조정 하 고 고급 전원 설정 또는 그룹 정책 설정은 구성 하지 않는 것이 좋습니다. 최대 밝기 수준을 피하는 동시에 기본 화면 및 절전 모드 시간 제한을 사용 하는 것은 사용자가 배터리 수명을 연장 하는 가장 효과적인 방법입니다.

![그림 1. 간단한 전원 & 절전 모드 설정](images/powerintrofig1.png)

그림 1. 간단한 전원 및 절전 모드 설정

### Windows 성능 전원 슬라이더

Windows 10 빌드 1709 이상을 실행 하는 Surface 장치에는 필요한 경우 배터리 수명에 대 한 우선 순위를 지정 하거나 필요한 경우 성능을 유지 하는 데 사용할 수 있는 파워 슬라이더가 포함 됩니다. 배터리 아이콘을 클릭 하 여 작업 표시줄에서 power slider에 액세스할 수 있습니다. 배터리 수명 (배터리 절약 모드) 또는 슬라이드 오른쪽으로 이동 하 여 더 빠른 성능을 유지 합니다.

![그림 2. 파워 슬라이더](images/powerintrofig2a.png)

그림 2. 파워 슬라이더

Power slider는 다음 표에 설명 된 네 가지 상태를 사용 합니다.

| 슬라이더 모드| 설명 |
|---|---|
| 배터리 절약 모드| 시스템의 전원이 꺼져 있는 상태에서 전원이 절약 되 고 배터리 수명이 연장 됩니다. 배터리 절약 모드가 켜져 있으면 일부 Windows 기능을 사용할 수 없거나, 제한 되거나, 다르게 동작할 수 있습니다. 화면 밝기도 줄입니다. 배터리 절약 모드는 배터리 전원 (DC)을 사용 하는 경우에만 사용할 수 있습니다. 자세히 알아보려면 [배터리 절약](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)을 참조 하세요.|
| 권장 사항 | 이전 버전의 Windows에서 기본 설정 보다 더 긴 배터리 수명으로 제공 됩니다. |
| 향상 된 성능 | 기본 슬라이더 모드로 작동 하는 배터리 수명 보다 성능이 약간 우위에 있습니다. |
| 최상의 성능 | 배터리 전력 소모에 관계 없이 최대 성능과 응답성이 필요한 작업 부하에 대 한 성능에 우위를 사용 합니다.|

전원 슬라이더 모드는 다음 표에 표시 된 특정 하드웨어 구성 요소를 직접 제어 합니다.

| 구성 요소 | 슬라이더 기능 |
|---|---|
| Intel Speed Shift (CPU 에너지 레지스터) 및 에너지 성능 기본 설정 힌트입니다. | 최적의 성능과 전원을 위해 가장 적합 한 작동 주파수와 전압을 선택 합니다. PERFEPP (에너지 성능) 기본 설정은 CPU에 대 한 전역 전원 효율성 힌트입니다. |
| 팬 속도 (RPM)| 해당 되는 경우 배터리 절약 모드에서 팬을 유지 하는 등의 조건 변화에 맞게 조정 합니다.|
| 프로세서 패키지 전력 제한 (PL1/PL2).| CPU가 주파수를 관리 하 여 PL1 (안정 된 상태) 및 터보 (PL2) 작업 부하에 대해 실행 중인 평균 전력 제한을 수용 하도록 요구 합니다.|
| 프로세서 터보 주파수 제한 (IA 터보 제한). | 프로세서 코어를 정격 작동 주파수 보다 더 빠르거나 느리게 실행할 수 있도록 하는 프로세서 및 그래픽 성능을 조정 합니다.                                                |

>[!NOTE]
>Power slider는 제어판/전원 옵션, 그룹 정책 또는 관련 방법으로 구성 되어 있는 운영 체제 전원 설정과 완전히 독립적입니다.

자세히 알아보려면 다음을 참조 하세요.

-   [Windows 성능 전원 슬라이더 사용자 지정](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [배터리 절약.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## 배터리 수명 연장 모범 사례


| 모범 사례 | 이동: | 다음 단계 |
|---|---|---|                                                                                                                                    
| Surface 장치가 최신 상태 인지 확인| Windows 업데이트 | 작업 표시줄 검색 상자에 **Windows Update** 를 입력 하 고 **업데이트 확인**을 선택 합니다. |
| 수행 중인 작업에 가장 적합 한 전원 설정 선택 | 파워 슬라이더 | 작업 표시줄에서 배터리 아이콘을 선택한 다음 **최적의 성능**, **배터리 수명 주기**또는 그 사이의 위치 중 하나를 선택 합니다.|
| 배터리 잔량이 낮을 때 절약 | 배터리 절약 모드 | 작업 표시줄에서 배터리 아이콘을 선택 하 고 **배터리 설정을**클릭 합니다. 배터리가 **아래로 떨어지면 배터리 절약 모드를 자동으로 설정을** 선택한 다음 슬라이더를 오른쪽으로 이동 하 여 배터리 수명을 길게 누릅니다. |
| 최적의 화면 밝기 구성 | 배터리 절약 모드 | 작업 표시줄에서 배터리 아이콘을 선택 하 고 배터리 **절약 모드에서 화면 밝기 낮추기** **를 클릭 합니다**. |
| 연결 되지 않은 경우에는 전기를 절약 하세요. | 배터리 절약 모드| **다음 충전 될 때까지 배터리 절약 모드 상태 끄기를**선택 합니다.|
| 전원 설정 문제를 조사 하세요. | 전원 문제 해결사 | 작업 표시줄에서 문제 해결을 검색 하 고 **문제 해결**을 선택한 다음 **전원** 을 선택 하 고 지침을 따릅니다.|
| 앱 사용 확인 | 앱 | 앱을 닫습니다.|
| 전원 코드에서 손상 된 부분이 있는지 확인 합니다.| 전원 코드 | 마모 되거나 손상 된 경우 전원 코드를 교체 합니다.|

## 자세히 알아보기 

- [최신 대기 모드](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [Windows 성능 전원 슬라이더 사용자 지정](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [배터리 절약 모드](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [Surface 드라이버 및 펌웨어 업데이트 관리 및 배포](manage-surface-driver-and-firmware-updates.md)
