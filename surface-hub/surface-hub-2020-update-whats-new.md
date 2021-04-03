---
title: Windows 10 Team 2020 업데이트의 새로운 기능
description: Surface Hub 운영 체제, Windows 10 Team 2020 업데이트의 최신 업데이트에 대한 새로운 소식을 확인해보십시오.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 14e08cf099ac441f7b2b3b76366406868ac6c056
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470426"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Windows 10 Team 2020 업데이트의 새로운 기능

Windows 10 Team 2020 Update는 최신 Windows 10 기능과 함께 장치 배포 및 관리성을 대대적으로 개선합니다.

##  <a name="deployment-and-manageability"></a>배포 및 관리 가능성

- **클라우드 장치 계정에 대한 최신 인증**. Surface Hub는 Exchange에 연결할 수 있도록 EWS(Exchange 웹 서비스) 및 ADAL(Active Directory 인증 라이브러리) 기반 인증을 지원하므로 고객은 기본 인증을 더 사용하지 않습니다. 자세한 내용은 [Surface Hub의 최신 인증을 참조합니다.](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth)
- MDM(모바일 장치 관리) 정책 설정이 **20개 이상 새로 추가 및 업데이트되었습니다.**  이러한 정책 설정을 통해 IT 관리자는 Microsoft Store의 앱 업데이트, 인프라를 통해 Miracast와 같은 무선 투영 설정, 네트워크 설정(예: 서비스 품질 및 802.1x 유선 인증) 및 새로운 개인 정보/GDPR 관련 설정을 비롯한 여러 장치 설정을 더 개선할 수 있습니다. 새 CSP(구성 서비스 공급자)에는 다음이 포함됩니다. 

  - [Accounts CSP](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) 
  - [Firewall-CSP](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) 
  - [RemoteWipe CSP](https://docs.microsoft.com/windows/client-management/mdm/remotewipe-csp) 
  - [Wifi-CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp) 
  - [Wirednetwork-CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) 

자세한 내용은 다음을 참조합니다. 
- [Microsoft Surface Hub에서 지원되는 CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [MDM 공급자를 사용하여 Surface Hub 관리](manage-settings-with-mdm-for-surface-hub.md)


##  <a name="azure-active-directory-joined-devices"></a>Azure Active Directory 가입 장치

- **Azure AD 가입 장치에 대한 SSO(Single Sign-On)입니다.** 사용자가 Microsoft 365 자격 증명을 사용하여 "내 모임 및 파일"에 로그인하면 브라우저의 Microsoft 365 환경을 포함하여 사용자 자격 증명이 앱에서 앱으로 원활하게 진행됩니다.
- Azure AD 가입 장치에 대한 **CA(조건부 액세스)입니다.**       IT 관리자는 Azure AD에 가입된 Surface Hub에 장치 수준 보안 정책을 배포하여 회사 보안 및 규정 준수 요구 사항에 따라 조직 리소스에 대한 액세스를 제어할 수 있습니다.
- Azure AD 가입 장치에 대한 전역이 아닌 **관리자에 대한 지원**. 고객은 관리자 계층 구조 내에서 더 세부적인 관리자 집합을 선택해 Surface Hub를 관리할 수 있습니다. 자세한 내용은 Surface Hub에서 전역이 아닌 관리자 [계정 구성을 참조하세요.](surface-hub-2s-nonglobal-admin.md)


## <a name="browser-and-pen"></a>브라우저 및 펜

- **새 Microsoft Edge에 대한 지원.** 최적의 호환성 성능, 보안 및 개인 정보 보호를 위해 Microsoft Edge가 다시 구성됩니다. 자세한 내용은 Surface Hub에서 새 Microsoft Edge 설치 및 [구성을 참조합니다.](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)
- **Surface Hub 2S의**이중 펜 Inking   사용자는 두 개의 Surface Hub 2 펜을 사용하여 Surface Hub 2S에서 화이트보드를 화이트보드하고 공동 작업할 수 있습니다. 이중 펜식 자동 작성을 사용하도록 설정하는 데 필요한 펌웨어 업데이트는 후속 업데이트와 함께 릴리스됩니다.

## <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams는 기본적으로 설치됩니다.**        Microsoft Teams는 MDM을 통해 변경하거나 설정 앱을 사용하여 Surface Hub에서 직접 구성할 수 있는 새 Surface Hub 디바이스에서 기본 모임, 통화 및 공동 작업 앱으로 포함되어 있습니다. 자세한 내용은 [Microsoft Teams 배포를 참조합니다.](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub)
- **Microsoft Teams와의**근접 가입 지원.  근접 조인을 사용하면 사용자가 랩톱/휴대폰을 사용하여 가까운 Surface Hub에서 예약된 Microsoft Teams 통화를 하게 되거나 진행 중 모임을 가까운 Surface Hub로 원활하게 전환할 수 있습니다. Windows 10 Team 2020 Update에는 근접 연결 구성을 위한 MDM(모바일 장치 관리) 지원이 추가되었습니다. 자세한 내용은 다음을 참조합니다. 

  - [Microsoft Teams 블로그](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833). 
  - [Surface Hub에서 Microsoft Teams 설정 관리](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **Microsoft Teams와의 조정된 모임 지원.** Surface Hub 및 Microsoft Teams 룸 장치를 특징으로 하는 회의실 또는 두 Surface Hub 디바이스가 있는 공간에서 조정된 모임을 통해 사용자는 Microsoft Teams 모임 중에 두 디바이스를 쉽게 활용할 수 있습니다. 한 번의 탭으로 사용자는 한 디바이스에서 비디오 피드를 표시하고 다른 디바이스의 디지털 화이트보드 또는 콘텐츠를 표시하여 한 디바이스에서 모임에 참가하고 화면 공간을 최대화할 수 있습니다. Windows 10 Team 2020 Update에는 협정 모임을 구성하기 위한 MDM(모바일 장치 관리) 지원이 추가되었습니다. 이 기능은 Microsoft Teams를 통해 Microsoft Teams 업데이트로 Store.To 자세한 내용은 [Set up Coordinated Meetings with Microsoft Teams Rooms and Surface Hub을](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings)참조하세요.

## <a name="security"></a>Security

- **FIDO2 보안**     키를 사용하는 암호 없는 로그인     FIDO2 보안 키를 사용하여 고객은 사용자 이름과 암호를 입력하지 않고도 Surface Hub에 쉽고 빠르게 로그인할 수 있습니다. SSO(Single Sign-On)와 결합된 이 기능은 모임 중에 파일, 앱 및 웹 사이트에 대해 빠르고 원활한 인증을 제공합니다. 자세한 내용은 Surface Hub에서 암호 없는 로그인 [구성을 참조하세요.](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate)
- **Microsoft Authenticator를**사용한 암호 없는 로그인 개선  Azure AD를 사용하는 조직의 경우 사용자는 사용자 이름과 암호를 입력하지 않고도 Microsoft Authenticator 앱을 사용하여 로그인할 수 있습니다. 또한 사용자는 UPN(사용자 계정 이름) 외에 Azure AD에서 기본 설정 전자 메일 별칭을 사용하여 로그인할 수 있습니다. 자세한 내용은 [Microsoft Authenticator로 Surface Hub에 로그인을 참조합니다.](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app)


## <a name="learn-more"></a>자세히 알아보기

- [Windows 10 Team 출시 업데이트](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [Windows 10 Team 2020 업데이트 설치](surface-hub-2020-update.md)  
 