---
title: Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성
description: 이 문서에는 개인 설정 큰 화면 터치 및 펜 컴퓨터를 사용할 때 최상의 환경을 보장하기 위한 권장 사항이 포함되어 있습니다.
keywords: Surface Hub, Windows 10, 데스크톱, 설치, 구성
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 7accbe3d905af3b295f92c002eecd5d77356672d
ms.sourcegitcommit: e126b8ac66a781ebe42cdd677af3fe6a2eb5e72c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203565"
---
# Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성

Windows 10 Pro 또는 Enterprise로 마이그레이션하는 설치 프로세스를 완료한 후 다음 단계를 수행하여 Surface Hub 2에서 앱 및 설정을 구성할 수 있습니다. 이러한 단계는 개인 설정 큰 화면 터치 및 펜 컴퓨터를 사용할 때 최상의 환경을 보장하는 데 권장됩니다.

이러한 단계를 수행할 때 유선 또는 무선 키보드와 마우스를 사용하는 것이 유용할 수 있습니다.

## 시스템 설정 구성

1. 디바이스에서 로컬 관리자 권한이 있는 계정으로 로그인합니다.  

    - Azure AD 가입 장치에서 Azure AD 가입을 수행하는 사용자가 로컬 관리자 그룹에 자동으로 추가됩니다. Azure AD 전역 관리자 및 Azure AD 장치 관리자도 로컬 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> </a> 관리자입니다. 
    
    - 명령 프롬프트에 **net localgroup 관리자를** 입력하여 로컬 관리자 권한이 있는 계정을 나열할 수 있습니다.
    
2. 이름(예: **username-SHub-Desktop)을**사용하여 디바이스 이름을 변경합니다.

3. 시작 **설정**계정을 선택하여 설정을  >  **Settings**  >  **Accounts**  >  **동기화하고** 동기화 설정을 **끄면** 됩니다. 

    - 여기에 사용된 설정은 최상의 큰 화면 터치 환경을 사용하도록 설정되어 있으므로 다른 디바이스를 동기화하지 않을 수 있습니다.
    
4. 디바이스를 다시 시작합니다.

## 터치 키보드 및 터치 패드 사용

1. 작업 표시줄을 탭하고 누르거나 마우스 **Show touch keyboard button** 오른쪽 단추를 클릭한 다음 터치 키보드 단추 표시 및 터치 패드 단추 **표시를 선택합니다.** 

    - 터치 키보드는 직접 사용자 입력에 유용하며, 가상 터치 패드는 정확한 선택, 화면 팁 마우스 오른쪽 단추 누르기 또는 마우스 오른쪽 단추로 누르기 대신 사용할 수 있습니다. 
    
    - 다음 예제를 참조하세요.

      ![터치 설정](images/touch.png)

2. 터치 키보드를 QWERTY 및 부동 키보드로 구성합니다.

    1. 작업 **표시줄에서 키보드** 아이콘을 선택하여 터치 키보드를 표시하십시오.
    
    2. 터치 키보드의 왼쪽 위 모서리에 있는 키보드 아이콘을 선택하여 키보드 설정을 니다.
    
    3. QWERTY를 사용하도록 설정하려면 위쪽 행의 마지막 키보드 유형 옆에 있는 마지막 옵션을 선택하고 부동 기능을 사용하도록 설정하려면 두 번째 행의 마지막 옵션을 선택합니다. 이 큰 화면에서 매우 유용합니다. 다음 예를 참조하세요.

       ![키보드 설정](images/kbd.png)
 
3. 소프트 키보드 설정을 구성합니다.

    1. 터치 **키보드에서** 설정 아이콘을 선택하거나 입력 설정을 검색하여 **니다.**
    
       ![소프트 키보드 설정](images/sh2-softkeyboard.png)

    1. 맞춤법, 입력 및 터치 키보드에서 모든 옵션을 사용하도록 설정할 수 있습니다.


다음 예제에서는 옵션을 탐색하고 선택하는 데 유용한 트랙 패드를 보여 제공합니다. 화면 키보드를 사용하여 Microsoft Store를 검색합니다.

![트랙 패드 사용](images/store.png)

## 키보드 Bluetooth 마우스 구성(선택 사항)

장치를 기본 Windows 장치로 사용하는 경우 키보드와 마우스를 연결하거나 입력 또는 정밀도 작업을 위해 자주 사용합니다.

Surface Hub 디바이스가 PC에 가까운 경우 테두리 없이 마우스를 사용하여 Surface Hub와 PC 간에 원활하게 이동할 <a href="https://aka.ms/mm" target="_blank"> </a> 수 있습니다. 자세한 내용은 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> 가비지에서 Microsoft 다운로드: 테두리 없는 마우스를 참조하세요. </a>

## 작업 표시줄 레이아웃의 예

아래 단계를 완료하여 Windows 10 Professional 또는 Enterprise용 Surface Hub 2를 설정/구성한 후, 각 응용 프로그램의 빠른 원터치 시작을 위해 가장 많이 사용되는 응용 프로그램을 작업 표시줄에 고정하는 것이 좋습니다. 다음은 작업 표시줄이 어떻게 표시될 수 있는지의 예입니다.

 ![작업 표시줄 레이아웃](images/taskblyt.png)
### 설치된 앱 업데이트

설치된 모든 스토어 앱을 업데이트합니다.

1. Microsoft Store 앱을 열고 오른쪽 위 모서리에서 더 많은 타원 보기를 선택합니다. **See more**
2. 다운로드 **및 업데이트를 선택합니다.**
3. 업데이트 **다운로드 선택**

### 모든 Windows 업데이트 검색 및 설치
Windows 10 Professional 또는 Windows 10 Enterprise로 마이그레이션한 후 설치할 수 있는 서비스 및 기능 업데이트가 있을 수 있습니다. 

- Go to **Settings**  >  **Update & Security** > and then select Check for **updates.**
- 업데이트가 있는 경우 업데이트를 설치하고 다시 시작한 다음 다음 알림이 표시될 때까지 프로세스를 반복합니다.

> [!div class="mx-imgBorder"]
> ![Windows 업데이트 '최신 정보' 알림](images/wustatus.png)


## 비즈니스용 OneDrive

비즈니스용 OneDrive를 사용하여 모든 작업 장치 간에 도구, 로그 및 기타 파일을 쉽게 <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> </a> 공유할 수 있습니다.

- OneDrive를 사용하면 랩톱, Surface Hub 데스크톱 및 Intune에서 관리하는 모바일 장치 간에 작업 파일을 공유할 수 있습니다. 모든 장치에서 파일을 편집할 수 있으며 모든 네트워크 연결 장치가 변경 내용으로 업데이트됩니다.

- Surface Hub SSD(128GB)의 크기를 고려하여 Surface Hub 데스크톱 디바이스에서 OneDrive를 구성하는 경우 기본 구성은 파일을 온라인으로 유지하고 파일을 사용할 때 다운로드하는 것입니다.

필요한 경우만 파일을 다운로드하도록 OneDrive를 **Files On-Demand** 구성하려면 필요한 경우 파일 관리 설정을 설정하여 공간을 절약하고 파일을 다운로드합니다. **Save space and download files as you use them** 자세한 내용은 Windows에서 쿼리 및 필요한 파일 제공 <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> 상태 설정을 참조하세요. </a>

![OneDrive 설정](images/onedrive.png)

> [!NOTE]
> 이러한 단계를 반복하여 개인 OneDrive를 구성할 수도 있지만 드라이브 공간을 절약하고 필요할 때만 파일을 다운로드해야 합니다.

## SharePoint 및 Teams

SharePoint 및 Teams 채널 파일은 OneDrive 동기화 엔진을 사용하여 랩톱 및 Surface Hub와 같은 데스크톱 장치와 로컬로 동기화할 수도 있습니다.

OneDrive 동기화 앱을 사용하여 내부 회사 파일을 로컬 드라이브에 동기화하려면

1. SharePoint 사이트로 이동하여 로컬 장치에서 보거나 편집하는 데 관심이 있는 파일의 최상위 문서 디렉터리로 이동합니다.

2. SharePoint 리본 **메뉴** 위쪽의 동기화 단추를 선택합니다.

3. 팝업에서 **Open** 열기에서 이 사이트가 **Microsoft OneDrive를 열려고 합니다.**

4. 작업 표시줄 오른쪽 아래에 있는 OneDrive 아이콘을 선택하여 SharePoint 파일이 로컬 드라이브와 동기화하고 있는지 확인해야 합니다.

5. 파일을 온라인으로 유지하고 파일을 사용할 때만 다운로드할 수 있는 구성이 설정되어 있는지 확인

    1. 파일 탐색기를 니다.
    
    2. SharePoint 이름을 찾아 마우스 오른쪽 단추로 클릭합니다. 예: **Contoso \<SharePoint Document Folder Name\> \ **.
    
    3. 공간을 **비우기 선택합니다.**
    
    4. 상태 열에는 파일 및 폴더의 상태가 표시됩니다. 자세한 내용은 OneDrive 동기화 클라이언트를 사용하여 SharePoint 파일 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> 동기화를 </a> 참조하세요.
    
6. Teams 채널 파일은 버전 기록 및 로컬 데스크톱 장치와 동기화를 포함하여 모든 동일한 SharePoint 문서 기능을 사용하여 SharePoint 사이트에 저장됩니다. Teams 채널 파일을 동기화하려면

    1. 관심 있는 Teams 채널로 이동하고 맨 위에 있는 파일 **탭을** 선택합니다. 그런 다음 **동기화를 선택합니다.** 파일이 동기화를 시작하고 Desktop \ Contoso \ 의 파일 **탐색기에서 \<name of the Teams Channel\> 표시됩니다. **
    
    2. SharePoint 사이트를 동기화하는 데 사용한 절차와 동일한 절차를 사용하여 파일을 클라우드에 보관하고 사용할 때만 다운로드하고, Teams 채널 이름의 파일 탐색기를 탭하고 누르거나 마우스 오른쪽 단추로 클릭한 다음 공간을 비우는 방법을 **선택합니다.**

## Surface Hub 펜 설정

**Surface Hub Bluetooth 페어링**

펜을 페어링하여 펜 펌웨어를 최신으로 유지하고, 펜 바로 가기를 설정하고, Bluetooth 장치 설정 페이지 또는 Surface 앱에서 배터리 충전 정보를 얻습니다.

1. 설정 **시작**  >  **디바이스를**  >  **선택합니다.**

2. Select **Add Bluetooth or other device.**

3. 를 **Bluetooth.**

4. 펜 tail 단추를 제거하고 흔들어 배터리 연결을 끊습니다.

5. 캡을 다시 넣고 페어링 LED가 깜박일 때까지 대문자 누를 수 있습니다.

6. Surface Hub Bluetooth **Surface Hub 2 펜을 선택합니다.**

7. 페어링 작업을 완료합니다. 

8. 페어링이 실패하면 펜을 다시 페어링할 수 있습니다. 그래도 문제가 해결되지 않는 경우 펜이 화이트보드 응용 프로그램에서 작동하는지 확인하여 배터리가 충전되어 있는지 테스트할 수 있습니다. 그렇지 않은 경우 배터리를 교체한 다음 펜을 다시 페어링해 하려고 합니다. 필요한 경우 장치를 다시 시작한 다음 다시 시도하십시오.

**펜 바로 가기 설정** Surface Hub 펜에는 "tail click"이라고도 하는 바로 가기 단추가 있습니다. 바로 가기를 구성하려면 앞에서 설명한 대로 펜을 먼저 페어링해야 합니다.

1. 펜을 검색하고 Windows ink & **펜을 선택합니다.**

2. 페이지 아래쪽에서 다음과 같이 대화 상자를 여는 펜 바로 가기를 선택합니다.

   ![펜 바로 가기](images/sh2-pen-shortcuts.png)

## 카메라 구성

디바이스의 위쪽 또는 어느 쪽에나 카메라를 탑재할 수 있습니다. 카트 대신 데스크톱 독립 실행형으로 허브를 사용하거나 허브와 가까운 위치에 카메라 각도를 최적화하기 위해 카메라를 탑재합니다. 카메라가 자동 회전하지 않습니다. 따라서 카메라를 수동으로 회전하려면 2mm 16진수 키가 필요합니다. 

카메라를 사이드 마운트하고 카메라를 수동으로 회전하는 방법에 대한 자세한 내용은 Surface Hub 2S 카메라 렌즈 방향을 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> </a> 참조하세요.

## Windows Hello 구성

Windows 10 Enterprise를 실행하는 Surface Hub 2S를 사용하면 Win32 데스크톱 응용 프로그램과 생체 인식 Windows Hello 옵션의 전체 제품군을 사용할 수 있습니다. Surface Hub 2 지문 판독기 액세서리를 장치의 모든 USB-C 포트에 연결할 수 있습니다. 

Surface Hub 2 지문 판독기를 주문하거나 기술 사양을 시청하기 위해서는 (surface-hub-2-essential-add-ons.md" target="_blank">Essential Add-ons for Windows 10 Pro and Enterprise on Surface Hub 2)를 참조합니다. </a> 

지문 판독기를 삽입한 **Start**후 시작 설정 계정 로그인 옵션을 선택하여 Windows Hello Fingerprint를 선택하여 지문을  >  **Settings**  >  **Accounts**  >  **Sign-in options**  >  **Windows Hello Fingerprint** 등록합니다.

얼굴 인식에 Windows Hello 인증 장치를 사용합니다. Surface Hub 2S 카메라는 Windows Hello 얼굴 인식을 지원하지 않습니다.

## 작업 표시줄에서 잠금 화면 바로 가기 아이콘 사용

Windows-L 바로 가기 키와 유사한 원터치 화면 잠금을 사용할 수 있는 아이콘을 작업 표시줄에 추가합니다. 

1.  바탕 화면을 탭하고 누르거나 마우스 **New**오른쪽 단추로 클릭하고 새 바로 가기  >  **Shortcut**  >  **Browse**  >  **찾아보기 데스크톱**  >  **확인 다음을**  >  **선택합니다.**

1.  내 **PC**잠금과 같은 바로 가기 이름을 입력한 다음 마름을 **선택합니다.**

1.  바탕 화면에서 새로 만든 바로 가기를 마우스 오른쪽 단추로 클릭하거나 탭하고 속성을 **선택합니다.** 바로 **가기 탭의** 대상 **Target** 필드에 다음을 입력합니다. **Rundll32.exe User32.dll,LockWorkStation**

1.  아이콘 **변경 단추를** 선택하고 아이콘을C:\Windows\System32\imageres.dll** 사용할 ** 아이콘을 선택합니다. 

    다음 예제를 참조하세요.

    ![아이콘 선택](images/lock.png)
    
1.  확인을 **선택하여** 바로 가기를 저장합니다.

1.  바로 가기를 마우스 오른쪽 단추로 클릭하거나 탭하고 작업 표시줄에 **고정을 선택합니다.**

1. 잠금 바로 가기를 작업 표시줄에 고정한 후 바탕 화면에서 삭제할 수 있습니다.

## 응용 프로그램


### Microsoft Whiteboard

Microsoft Whiteboard를 설치하려면

 - 작업 **표시줄 오른쪽** 아래에서 Windows Ink 작업 영역 아이콘을 선택하고 **화이트보드를 다운로드합니다.**
 
   ![Ink 작업 영역](images/ink.png) 

또는 Microsoft Store에서 화이트보드를 설치할 수 있습니다.

1. Microsoft Store 앱을 열고 **화이트보드를 검색합니다.**

2. 로그인하고 여러 디바이스에서 사용해주신 덕분에 **아니요를** 선택하십시오.

3. 화이트보드를 작업 표시줄에 고정합니다.

### Surface 앱

1. Microsoft Store에서 **Surface를 검색합니다.**

2. 필터에서 **사용 가능을** 모든 **장치로 설정**

3. Surface **앱을 설치합니다.** 이 앱은 나열된 첫 번째 앱입니다. 앱을 설치하려면 MSA를 스토어에 연결해야 할 수 있습니다.

4. Surface 앱을 **작업** 표시줄에 고정합니다.

### 캡처 및 스케치

1. 스케치 & **Snip** 앱을 열고 작업 표시줄에 고정합니다.

2. 오른쪽 위 모서리에서 타원을 선택한 다음 설정을 **선택합니다.**

3. 설정에서 클립보드에 **자동 복사,** 잘라 내기 **및**여러 창을 **니다(선택** 사항). **Settings**

### Microsoft Office

1. Office <a href="https://portal.office.com/account#installs" target="_blank"> 포털을 </a> 열고 원하는 응용 프로그램을 설치합니다.

2. 원하는 Office 응용 프로그램을 작업 표시줄에 고정합니다.

3. Outlook이 설치된 경우 Outlook OST를 설정하여 지난 2주 동안의 캐시만 저장해야 합니다. 이렇게 하면 디스크 사용량 및 설정 시간이 크게 줄어듭니다.

    - 파일 **File**  >  **계정 설정을 선택하고** 계정을 선택합니다.
    
    - 변경을 **선택하고** 캐시된 **Exchange** 모드를 사용할 슬라이더를 14일로 설정하십시오.

### Microsoft Teams

1. <a href="https://teams.microsoft.com/downloads" target="_blank">Microsoft Teams를 다운로드하여 </a> 설치합니다.

2. 응용 프로그램을 자동으로 시작하도록 설정을 구성합니다(선택 사항).

3. Teams를 작업 표시줄에 고정합니다.

4. 방해를 피하기 위해 디바이스에서 Teams 알림을 줄이는 것이 좋습니다(선택 사항).

   ![Teams 알림](images/teams.png)

### 앱 연결

> [!IMPORTANT]
> Windows 10 버전 2004 이상에서는 Miracast를 사용하는 무선 투영용 Connect 앱이 기본적으로 설치되지 않지만 선택적 기능으로 사용할 수 있습니다. Windows 버전 2004 이상을 설치(또는 업데이트)한 경우 이 PC 화면에 다음 설정이 표시될 수 있습니다.

![이 PC에 프로젝트](images/sh2-project.png) 


1. "이 PC에 투영" 설정 페이지에서 앱을 설치하려면 선택적 기능 추가 기능을 선택한 다음 무선 디스플레이 **Optional features**  >  **Add a feature** **앱을 설치합니다.**

2. 일부 Windows 및 Android 장치에서 확인이면 이 PC에 프로젝트할 수 **있습니다.** 다음을 선택하십시오.

    - **장치가 회사** 네트워크에 없는 경우 모든 곳에서 사용할 수 있습니다.
    - 그렇지 않은 경우 **보안 네트워크의 모든 곳에서 사용 가능을 선택하십시오.**
    
3. Under **Ask to project to this PC,** choose First time **only**.

4. **페어링을 위해 PIN 필요 아래에서**사용 **안 을 선택 합니다.**

5. 그런 다음 앱을 시작하고 작업 표시줄에 고정하기 위해 **Connect를 검색합니다.**

6. 앱을 열 수 있습니다. 앱이 열려 있는 동안 작업 표시줄에서 앱 연결 아이콘을 마우스 오른쪽 단추로 클릭하고 작업 표시줄에 **고정을 선택합니다.**

7. 그런 다음 연결 앱을 닫습니다. 앱이 한 번 이상 실행되지 않으면 이 **PC에** 대한 Project가 작동하지 않을 수 있습니다.

회사 네트워크에 없는 경우 권장되는 구성:

![가정의 설정](images/project1.png)

회사 네트워크에서 권장되는 구성:

![직장의 설정](images/project2.png)

### 사용자 휴대폰

휴대폰 **앱은** 기본적으로 Windows 10에 설치됩니다. 이 패키지가 없는 경우 Windows 스토어에서 설치할 수 있습니다.

앱을 설정하는 방법에 대한 자세한 내용은 Windows 10에서 휴대폰을 설정하고 PC와 휴대폰 간에 데이터를 동기화하는 방법을 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> </a> 참조하세요. Windows 10에서 휴대폰 앱의 일반적인 문제를 해결하는 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 방법도 </a> 참조하세요.

###  멋진 영역


**멋진 영역은** <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> GitHub의 PowerToys라는 도구 </a> 모음의 일부입니다. 디스플레이에서 고정 레이아웃("영역")을 정의한 다음 각 영역에서 실행할 앱을 선택하여 Surface Hub 2의 화면 부동산을 활용하는 좋은 방법입니다. 


[PowerToys 위키에는](https://github.com/microsoft/PowerToys/wiki) [FancyZones를](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)포함하여 각 도구를 사용 및 사용자 지정하는 방법에 대한 지침이 있습니다. 높은 수준에서 - PowerToys를 설치한 후 사용자 지정 레이아웃을 선택하거나 만든 다음 Shift 키를 아래로 놓고 키보드 키를 끌어서 실행 중인 앱을 특정 영역으로 이동할 수 있습니다. 이 Bluetooth 또는 USB 키보드와 마우스를 사용하면 도움이 되거나 화면 터치 키보드와 터치 패드를 사용할 수 있습니다.

**전원 토이 팁**
- GitHub에서 PowerToys 릴리스 업데이트에 대한 전자 메일 알림을 받으려면 페이지 위쪽의 "등록" 단추를 [클릭합니다.](https://github.com/microsoft/PowerToys/releases)
- PowerToys가 설치되면 PowerToys 설정 다운로드 업데이트를 자동으로 설정하여 Windows 알림을 받고 최신 업데이트를 다운로드 및 설치할 **수** 있습니다.
- PowerToys 설정에 액세스하려면 작업 표시줄에서 실행 중인 앱을 선택하고 메뉴가 나타날 때까지 PowerToys 아이콘을 마우스 오른쪽 단추로 클릭하거나 누르고 있습니다. **Running apps** "설정"을 선택합니다.
- PowerToys 설정 페이지의 맨 아래에서 업데이트를 자동으로 **다운로드합니다.**
- 업데이트가 릴리스된 경우 업데이트를 설치할 수 있는 옵션을 제공 하는 Windows 알림이 나타납니다.


### Edge Chromium 브라우저

새 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium 브라우저를 다운로드하여 설치합니다. </a>


### Surface Hub 하드웨어 진단 도구

<a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank">Surface Hub 하드웨어 진단 </a> 도구는 Microsoft Store에서 무료로 사용할 수 있습니다. 이 도구는 Surface Hub가 최상의 기능을 수행하는지 확인하도록 디자인됩니다. 펌웨어가 최신 버전인지와 올바르게 구성된지 확인하는 테스트가 포함되어 있습니다. 대화형 테스트를 통해 필수 기능이 예상대로 작동하고 있는지 확인할 수 있습니다. 문제가 발생하는 경우, 결과를 저장하고 Surface Hub 지원 팀과 공유할 수 있습니다. 링크를 클릭하여 Microsoft Store에서 설치한 다음 응용 프로그램을 작업 표시줄에 고정합니다.

## 추가 설정

### Pen tail select to launch Whiteboard

1. 펜을 **검색하고** **Windows & 설정을 선택합니다.**

2. 페이지 아래쪽의 펜 바로 **Pen shortcuts** 가기에서 **Select once를** **Microsoft Whiteboard로 설정** 

### 전원 관리

Surface Hub 2에서 Windows 10 Pro 또는 Enterprise를 사용하여 최상의 환경을 얻을 수 있는 몇 가지 전원 설정이 있습니다. 여기에는 화면 및 PC 시간 제한 및 기본 제공 Doppler(휴먼 현재 상태 감지), 화면 보호기 및 암호 보호와 상호 작용하는 방법, 그리고 적절한 경우 랩톱/데스크톱 사용자를 위한 그룹 정책 전원 설정을 전달하는 방법을 포함합니다.

Surface Hub 2의 Windows 10 Pro 또는 Enterprise는 터치, 마우스 및 키보드 동작과 기본 제공 Doppler(휴먼 점유 감지)를 통해 화면이 절전으로 이동하지 못하게 합니다. 기본적으로 휴먼 점유 검색은 사용하도록 설정되어 있지만, 원하는 경우 초기 마이그레이션의 일부로 Surface UEFI 구성 도구에서 장치 옵션을 전환하거나 이후 UEFI 구성 패키지를 구축 및 적용하여 사용하지 않도록 설정할 수 있습니다. 

**전원 관리: 화면 및 PC 절전 설정**

1. **Start**  >  **절전으로 시작 설정**  >  **시스템**전원  >  **& 선택합니다.**

2. 전원 모드 슬라이더를 최상의 **성능으로 설정**

3. 이동이 감지될 때 디바이스를 깨우는 Doppler 현재 상태 감지를 고려하면서 화면 및 절전 모드 값을 기본 설정에 맞게 구성합니다. 따라서 모범 사례로, **2시간** 후에 화면이 꺼지게 설정하고 4시간 후에 PC가 꺼지게 **설정하는 것이 좋습니다.**

**전원 관리: 화면 보호기**

1. 잠금 화면 **및** 잠금 화면 **열기 설정을 검색합니다.**

2. 화면 **시간 제한 설정 및** 화면 **보호기** 설정을 기본 설정으로 구성합니다. 권장되는 기본값은:

   - 화면 보호기에서 선택한 화면 보호기(없음) 또는 화면 보호기입니다.
   - 15분까지 기다립니다.
   - 다시 시작 시 로그온 화면을 표시합니다.


**전원 관리: 그룹 정책**

다음 절차를 수행하기 전에 IT 부서에 승인을 요청하여 전역 전원 관리 정책에서 Surface Hub 2S 장치를 제외합니다. 일부 전원 관리 설정은 현재 상태 검색 기능을 사용하지 않도록 설정할 수 있습니다.

1. 소프트웨어 **센터를 검색하고** 열어 습니다.

2. 옵션을 **선택합니다.**

3. 전원 관리를 **확장하고** 이 컴퓨터에 IT 부서의 전원 설정 적용 **안 을 선택합니다.**

   ![소프트웨어 설정](images/soft-cntr.png)

### 저장소 센스

Surface Hub 2에는 로컬 저장소용 128GB SSD가 있으므로 일반적인 사용 중에 저장소 저장 방법을 사용하는 것이 좋습니다.  저장소 센스를 구성하는 경우:

1.  시스템 **설정 아래에**있는 저장소 설정을 **검색합니다.**

2.  설정 **아래에서**저장소 설정 켜기 **센스를** 선택하여 저장소 설정 페이지를 **여십시오.**

3.  저장소 센스를 **켜는 경우**

4.  저장소 **센스 구성을** 선택하거나 지금 실행하고 파일을 가능한 한 많이 온라인으로 유지하도록 설정을 구성합니다(드라이브 공간 제한으로 인해).

권장 설정:

- 저장소 센스 실행 = 매일.
- 앱에서 사용하지 않는 임시 파일을 삭제합니다. 최소 14일마다(이상).
- 30일이 지난 경우 다운로드 폴더에서 파일을 삭제합니다.
- OneDrive: 30일 이상 열지 않은 경우 콘텐츠가 온라인 전용이 됩니다.

### 태블릿 모드

접근성 요구에 필요한 경우 태블릿 모드를 니다.


### 소리 설정

1. 소리 설정을 **검색하고** 이 페이지를 여십시오.

2. 오른쪽의 소리 **제어판을** 선택하고 소리 **탭을** 선택합니다.

3. 프로그램 **이벤트에서** **장치 연결** 및 장치 연결 **끊기를** 없음으로 **설정**

### 침묵 알림

1. 포커스 **도우미를 검색하고** 이 페이지를 여십시오.

2. 알람만 **선택합니다.** 이렇게 하면 일정한 알림 플라이아웃이 방지됩니다.

### 디스크 정리

1. 디스크 **정리를 검색하고** 이 앱을 니다.

2. 삭제할 **파일에서**삭제할 파일을 선택합니다. 

3. 또한 시스템 **파일 정리를 선택합니다.**

## 완료 및 확인

1. 모든 Windows 업데이트를 검색하고 설치합니다.

2. 그룹 정책을 업데이트합니다.

   1. 승강된 명령 프롬프트에 **gpupdate /force /boot /wait:0을 입력합니다.**
   
3. 디바이스를 다시 시작합니다.

4. 작업 표시줄 앱을 검증합니다.

   - 앱 연결
   - 잠금 아이콘
   - 캡처 및 스케치
   - Teams(해당되는 경우)
   - Office 앱(해당되는 경우)
   - Surface 앱
   - 화이트보드
    
5. 현재 상태 검색을 검증합니다.

   - 현재 상태 검색은 시스템 트레이에 녹색 아이콘이 됩니다.
    
6. 연결 앱을 사용하여 이 PC에 대한 투영이 활성화되어 있는지 확인합니다. 이  **PC 설정으로 Project를 구성한** 후 적어도 한 번 이상 연결 앱을 실행합니다. (이후에 Surface Hub에 프로젝트를 진행하기 위해 Connect 앱을 실행하지 않을 필요는 없습니다.)

7. 전원 및 절전 설정을 확인합니다.

    - 화면 보호기: 15분, 설정(없음), Mystify 또는 Blank 암호 요구 확인란이 선택되어 있도록 합니다.
    - 화면: **2시간 후에 끄기**
    - PC: **4시간 후에 꺼집니다.**
    
8. Windows Hello가 작동하고 있는지 확인

9. 동기화 설정이 사용하지 않도록 설정되어 있는지 확인합니다.

10. 시작 앱을 검증합니다.

> [!TIP]
> Windows 10을 설치 및 구성한 후 Surface Hub 2S는 다른 Windows 10 장치와 마찬가지로 관리할 수 있습니다.

## 관련 항목

<a href="surface-hub-2s-migrate-os.md" target="_blank"> Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션</a>
