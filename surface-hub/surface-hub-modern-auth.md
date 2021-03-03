---
title: Surface Hub의 최신 인증
description: 이 페이지에서는 레거시 기본 인증과 달리 Surface Hub에서 최신 인증을 사용하는 방법을 설명하고 있습니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 1674b7abd74a666e2ab1040f66d9ea548ab3c201
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385166"
---
# <a name="modern-authentication-on-surface-hub"></a>Surface Hub의 최신 인증

Windows 10 Team 2020 Update는 일부 시나리오에서 허브 장치 계정의 최신 인증에 대한 지원을 추가합니다. 2020 업데이트를 설치한 후 장치 계정이 Azure Active Directory를 통해 인증하고 계정의 사서함이 Exchange Online에서 호스팅되는 경우 레거시 기본 인증에서 마이그레이션하여 향상된 최신 보안 기능을 사용할 수 있습니다. 2020 업데이트를 통해 Surface Hub는 장치 계정을 Exchange Online과 동기화할 때 EWS(Exchange 웹 서비스) 프로토콜 및 ADAL(Active Directory 인증 라이브러리) 기반 인증을 지원합니다.

새 클라우드 기반 계정의 경우 Surface Hub는 최신 인증을 사용하여 Exchange Online에 연결하기 위해 단순히 형식을 사용하여 장치 계정을 만드는 [것 이상으로](mailto:alias@contoso.com)추가 구성을 요구하지 alias@contoso.com. 최신 인증에 지원되지 않는 레거시 형식인 Contoso\alias를 사용하지 않습니다. 자세한 내용은 Surface Hub 2S 디바이스 계정 [만들기를 참조하세요.](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

> [!NOTE]
> Surface Hub는 사내 계정에 대한 최신 인증을 지원하지 않습니다. 계정을 클라우드에 만들어야 합니다.

