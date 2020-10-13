---
title: 비즈니스용 Microsoft 스토어 또는 Microsoft Store (Surface)를 사용 하 여 Surface 앱 배포
description: Microsoft Store for Business 또는 교육용 Microsoft Store를 사용 하 여 Surface 앱을 추가 하 고 다운로드 하는 방법과 PowerShell 및 MDT를 사용 하 여 Surface 앱을 설치 하는 방법을 알아보세요.
keywords: surface app, app, 배포, 사용자 지정
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 811feff1f0643ab0ba5d624c5f7d561ba5b0cd4d
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114716"
---
# 비즈니스를 위한 Microsoft 스토어 및 교육용 Surface 앱 배포

**적용 대상**

- Surface 랩톱 이동
- Surface Pro 7
- Surface 노트북 3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- LTE를 사용 하 여 Surface Go
- Surface Book 2
- Surface Pro LTE Advanced(모델 1807)
- Surface Pro(모델 1796)
- Surface 노트북
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface 3
- Surface Pro 3


Surface app은 다음과 같이 다양 한 Surface 관련 설정 및 옵션을 제어 하는 간단한 Microsoft 스토어 앱입니다. 

* Surface 디바이스에서 Windows 단추를 사용하거나 사용하지 않도록 설정 

* Surface 펜의 감도 조정 

* Surface 펜 단추 동작을 사용자 지정 

* Surface 오디오의 향상된 기능을 사용하거나 사용하지 않도록 설정 

* 장치에 대 한 지원 문서 및 정보에 대 한 빠른 액세스

Windows 업데이트를 사용 하는 고객은 일반적으로 자동 업데이트의 일부로 Surface 앱을 받습니다. 그러나 조직에서 Surface 장치에 배포할 이미지를 준비 하는 경우 각 개별 장치의 사용자가 Microsoft Store 또는 비즈니스용 Microsoft Store에서 앱을 다운로드 하 고 설치 하도록 요구 하는 대신 Surface Hub와 같은 이전에 서피스 허브를 포함 하는 것이 좋습니다. 

> [!NOTE]
> 이 문서는 Surface Pro X에는 적용 되지 않습니다. 자세한 내용은 [Surface Pro X 배포, 관리 및 서비스](surface-pro-arm-app-management.md) 를 참조 하세요.

## Surface app 개요

Surface 앱은 [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)에서 무료로 다운로드할 수 있습니다. Microsoft Store에서 앱을 다운로드 하 고 설치할 수 있지만, 조직에서 Microsoft Store for Business를 사용 하는 경우에는 스토어의 재고에 추가 하 고 Windows 배포 프로세스의 일부로 앱을 포함 해야 합니다. 이 문서 전체에서 이러한 프로세스에 대해 설명 합니다. 비즈니스용 Microsoft 스토어에 대 한 자세한 내용은 Windows TechCenter의 [비즈니스용 Microsoft 스토어](https://docs.microsoft.com/microsoft-store/) 를 참조 하세요. 

## 비즈니스용 Microsoft Store 계정에 Surface 앱 추가 

사용자가 회사의 Microsoft Store 비즈니스 계정에서 앱을 설치 하거나 배포 하기 전에 먼저 원하는 앱을 사용 하 고 비즈니스 사용자에 게 라이선스를 부여 해야 합니다. 

1. 아직 수행 하지 않은 경우 [비즈니스용 Microsoft 스토어 계정을](https://www.microsoft.com/business-store)만듭니다. 

2. 포털에 로그온 합니다. 

3. 오프 라인 라이선스 사용: 그림 1에 나와 있는 것 처럼 **관리->스토어 설정을**클릭 하 고 **스토어의 사용자 쇼핑에 오프 라인 라이선스가 있는 앱 표시** 확인란을 선택 합니다. 비즈니스용 Microsoft Store 앱 라이선스 모델에 대 한 자세한 내용은 [Microsoft Store 비즈니스 에디션 및 교육용 앱](https://docs.microsoft.com/microsoft-store/)을 참조 하세요.

   > [!div class="mx-imgBorder"]
   > ![오프 라인 라이선스 앱 표시 확인란](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *그림 1. 앱을 오프 라인으로 사용할 수 있도록 설정*

4. 이 절차를 따라 비즈니스용 Microsoft Store 계정에 Surface 앱을 추가 합니다.

    * **상점** 메뉴를 클릭 합니다.
    
    * 검색 상자에 **Surface app**을 입력 한 다음 검색 아이콘을 클릭 합니다.
    
    * Surface 앱이 검색 결과에 표시 되 면 앱의 아이콘을 클릭 합니다.
    
    * 그림 2와 같이 선택 ( **온라인** 또는 **오프 라인**)이 표시 됩니다.
    
      > [!div class="mx-imgBorder"]
      > ![오프 라인 라이선스 모드를 선택 하 고 앱을 인벤토리에서 추가 합니다.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *그림 2. 오프 라인 라이선스 모드를 선택 하 고 앱을 인벤토리에서 추가 합니다.*
    
    * 오프 **라인** 을 클릭 하 여 오프 라인 라이선스 모드를 선택 합니다.
    
    * **앱 다운로드** 를 클릭 하 여 Microsoft Store 비즈니스 에디션 인벤토리에 앱을 추가 합니다. 그림 3에 표시 된 대로, 관리 도구를 사용 하 여 앱을 배포 하거나 개인 저장소의 회사 재고 페이지에서 다운로드할 수 있다는 메시지를 표시 하는 대화 상자가 표시 됩니다.
    
      > [!div class="mx-imgBorder"]
      > ![오프 라인에서 사용이 허가 된 앱 승인 창 ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *그림 3. 오프 라인에서 사용이 허가 된 앱 승인*
      
    * **확인**을 클릭합니다.

## Microsoft Store 비즈니스 에디션 계정에서 Surface 앱 다운로드
오프 라인 모드에서 Microsoft 비즈니스용 스토어 계정에 앱을 추가한 후에는 앱을 배포 공유에 대 한 .Appxbundle로 다운로드 하 고 추가할 수 있습니다.

1. Microsoft Store for Business 계정에 로그온 https://businessstore.microsoft.com 합니다.

2. **관리->앱 & 소프트웨어**를 클릭 합니다. 이 문서의 [비즈니스용 Microsoft Store 계정에 surface App 추가](#add-surface-app-to-a-microsoft-store-for-business-account) 섹션에 추가한 surface 앱을 포함 하 여 회사의 모든 앱 목록이 표시 됩니다.

3. **작업**에서 줄임표 (**...**)를 클릭 한 다음 Surface app의 **오프 라인 사용을 위해 다운로드** 를 클릭 합니다.

4. 그림 4와 같이 선택한 앱에 대해 사용할 수 있는 선택 항목에서 원하는 **플랫폼** 및 **아키텍처** 옵션을 선택 합니다.

    > [!div class="mx-imgBorder"]
    > ![.Appxbundle 패키지의 예](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *그림 4. 앱에 대 한 .Appxbundle 패키지 다운로드*
    
5. **다운로드**를 클릭 합니다. .Appxbundle 패키지가 다운로드 됩니다. 다운로드 한 파일의 경로를 확인 하 고이 문서의 뒷부분에 나와 있어야 합니다.

6. **인코딩된 라이선스** 또는 **인코딩되지 않은 라이선스** 옵션 중 하나를 클릭 합니다. 인코딩된 라이선스 옵션은 Microsoft 끝점 구성 관리자와 같은 관리 도구와 함께 사용 하거나 Windows 구성 디자이너를 사용 하 여 배포 패키지를 만드는 경우 사용할 수 있습니다. Microsoft 배포 도구 키트 (MDT)를 포함 하 여 이미징을 기반으로 하는 DISM (배포 이미지 서비스 및 관리) 또는 배포 솔루션을 사용 하는 경우 인코딩되지 않음 라이선스 옵션을 선택 합니다.

7. **생성** 을 클릭 하 여 앱에 대 한 라이선스를 생성 하 고 다운로드 합니다. 이 문서의 뒷부분에 필요한 경우 라이선스 파일의 경로를 기록해 두어야 합니다.

>[!NOTE]
>Surface 앱과 같이 오프 라인으로 사용할 앱을 다운로드 하면 **필수 프레임 워크로**표시 된 페이지 아래쪽에 섹션을 볼 수 있습니다. 대상 컴퓨터에서 앱을 실행 하기 위해 설치 된 프레임 워크를 사용 해야 하므로 아키텍처 (x86 또는 x64)에 대해 필요한 각 프레임 워크에 대해 다운로드 프로세스를 반복 하 고이 문서의 뒷부분에 설명 된 Windows 배포의 일부로이를 포함 해야 할 수도 있습니다.

그림 5는 Surface 앱에 대 한 필수 프레임 워크를 보여 줍니다.

> [!div class="mx-imgBorder"]
> ![Surface 앱에 대 한 필수 프레임 워크](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*그림 5. Surface 앱에 대 한 필수 프레임 워크*

>[!NOTE]
>앱이 업데이트 되 면 Surface app 및 필수 프레임 워크의 버전 번호가 변경 됩니다. Microsoft Store for Business의 Surface app 및 각 프레임 워크의 최신 버전을 확인 하세요. 비즈니스를 위해 Microsoft Store에서 제공 하는 Surface app 및 추천 프레임 워크 버전을 항상 사용 합니다. 오래 된 프레임 워크 나 올바르지 않은 버전을 사용 하면 오류 또는 응용 프로그램 충돌이 발생할 수 있습니다.

Surface 앱에 대 한 필수 프레임 워크를 다운로드 하려면 다음 단계를 따르세요.

1. **140.00 _1423816**. 0 _X64__8wekyb3d8bbwe에서 **다운로드** 단추를 클릭 합니다. 이는 140.00 _1423816 _x64__8wekyb3d8bbwe를 다운로드 합니다. 지정 된 폴더에 Appx 파일을 추가할 수 있습니다.

2. **MICROSOFT net.tcp. 1.1 _1.1 23406.0 _x64__8wekyb3d8bbwe**에서 **다운로드** 단추를 클릭 합니다. 이렇게 하면 23406.1. t e t. t e t. t e.

>[!NOTE]
>Surface 장치에 각 프레임 워크의 64 비트 (x64) 버전만 필요 합니다. Surface 디바이스는 기본 64 비트 UEFI 장치 이며 32 비트 프레임 워크를 필요로 하는 32 비트 (x86) 버전의 Windows와 호환 되지 않습니다. 

## PowerShell을 사용 하 여 컴퓨터에 Surface 앱 설치
다음 절차는 Surface 앱을 컴퓨터에 프로 비전 하 고 나중에 컴퓨터에서 만든 모든 사용자 계정에서 사용할 수 있도록 합니다.

1. 이 문서의 [Microsoft Store 비즈니스 계정에서 surface 앱을 다운로드 하는 방법](#download-surface-app-from-a-microsoft-store-for-business-account) 섹션에 설명 된 절차를 사용 하 여 Surface app .appxbundle 및 라이선스 파일을 다운로드 합니다. 

2. 관리자 권한 PowerShell 세션을 시작합니다.

    >[!NOTE]
    >관리자로 PowerShell을 실행 하지 않는 경우에는 앱을 설치 하는 데 필요한 권한이 세션에 없습니다.
    
3. 관리자 권한 PowerShell 세션에서 다음 명령을 복사한 다음 붙여넣습니다.

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    `<DownloadPath>`비즈니스용 Microsoft Store 계정에서 .appxbundle 및 라이선스 파일을 다운로드 한 폴더는 어디에 위치 합니다.

    예를 들어 파일을 c:\Temp로 다운로드 한 경우 실행 하는 명령은 다음과 같습니다.
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. 이제 Surface 앱을 현재 Windows 컴퓨터에서 사용할 수 있습니다. 

   Surface 앱이 프로 비전 된 컴퓨터에서 작동 하기 전에이 문서의 앞부분에서 설명한 프레임 워크를 프로 비전 해야 합니다. 이러한 프레임 워크를 프로 비전 하려면 Surface 앱을 프로 비전 하는 데 사용 되는 관리자 권한 PowerShell 세션에서 다음 절차를 사용 합니다.

5. 관리자 권한 PowerShell 세션에서 다음 명령을 복사한 다음 붙여넣습니다.

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. 관리자 권한 PowerShell 세션에서 다음 명령을 복사한 다음 붙여넣습니다.

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## MDT를 사용 하 여 Surface 앱 설치
다음 절차에서는 배포 시에 MDT를 사용 하 여 Surface 앱의 설치를 자동화 합니다. 응용 프로그램은 배포 중 MDT에서 자동으로 프로비전되어 기존 이미지로 이 프로세스를 사용할 수 있습니다. 이 프로세스는 surface 장치에 대 한 Windows 배포 과정에서 Windows 이미지의 교차 플랫폼 호환성을 줄이지 않기 때문에 surface 앱을 배포 하는 데 권장 되는 절차입니다.

1. [이 문서의 앞부분에서](#download-surface-app-from-a-microsoft-store-for-business-account)설명한 절차를 사용 하 여 Surface app .appxbundle 및 라이선스 파일을 다운로드 합니다. 

2. MDT 배포 워크 벤치에서 새 응용 프로그램 마법사를 사용 하 여 다운로드 한 파일을 **원본 파일과 함께 새 응용 프로그램**으로 가져옵니다.

3. 새 응용 프로그램 마법사의 **명령 세부 정보** 페이지에서 다음의 기본 **작업 디렉터리** 를 지정 하 고 **명령** 에 대해 다음과 같이 해당 .appxbundle의 파일 이름을 지정 합니다.

   * 명령을
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * 작업 디렉토리:%DEPLOYROOT%\Applications\SurfaceApp

대상 컴퓨터에서 Surface app이 작동 하려면이 문서의 앞에서 설명한 프레임 워크도 필요 합니다. Surface 앱에 필요한 프레임 워크를 MDT로 가져오고이를 종속성으로 구성 하려면 다음 절차를 사용 합니다.

1. 이 문서의 앞부분에서 설명한 절차를 사용 하 여 프레임 워크 파일을 다운로드 합니다. 각 프레임 워크를 별도의 폴더에 저장 합니다.

2. MDT 배포 워크 벤치에서 새 응용 프로그램 마법사를 사용 하 여 다운로드 한 파일을 **원본 파일과 함께 새 응용 프로그램**으로 가져옵니다.

3. **명령 세부 정보** 페이지에서 **명령** 필드와 기본 작업 디렉터리에 다운로드 한 각 응용 프로그램의 파일 이름을 입력 합니다.

프레임 워크를 Surface app의 종속성으로 구성 하려면 다음 프로세스를 사용 합니다.

1. MDT 배포 워크 벤치에서 Surface 앱의 속성을 엽니다.

2. **종속성** 탭을 클릭 한 다음 **추가**를 클릭 합니다.

3. 새 응용 프로그램 마법사에서 입력 한 이름을 사용 하 여 각 프레임 워크에 대 한 확인란을 선택 합니다.

가져온 후에는 Windows 배포 마법사의 **응용 프로그램** 단계에서 Surface 앱을 선택할 수 있습니다. 다음 프로세스에 따라 배포 작업 순서에서 응용 프로그램을 지정하여 응용 프로그램을 자동으로 설치할 수도 있습니다.

1. MDT Deployment Workbench에서 배포 작업 순서를 엽니다.

2. 배포의 **State Restore**(상태 복원) 섹션에서 새로운 **Install Application**(응용 프로그램 설치) 작업을 추가합니다.

3. **단일 응용 프로그램 설치** 를 선택 하 고 **Surface 앱** 을 **설치할 응용 프로그램**으로 지정 합니다.

Windows 배포에 앱을 포함 하는 방법에 대 한 자세한 내용은 [Microsoft 배포 도구 키트를 사용 하 여 windows 10 배포](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)를 참조 하세요.
