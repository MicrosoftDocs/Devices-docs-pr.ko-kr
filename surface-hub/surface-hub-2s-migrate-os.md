---
title: Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션
description: 이 문서에서는 Surface Hub 2의 Windows 10 Team에서 Windows 10 Pro 또는 Windows 10 Enterprise로 마이그레이션하는 과정을 설명 합니다.
keywords: Surface Hub 데스크톱, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/29/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0c6a52d1023377f51ae6a63879e54b86db16cb9a
ms.sourcegitcommit: 35f64110ce8e0c0b019b02023d746f648f554c1c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2020
ms.locfileid: "11088632"
---
# <span data-ttu-id="75a80-104">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="75a80-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

## <span data-ttu-id="75a80-105">소개</span><span class="sxs-lookup"><span data-stu-id="75a80-105">Introduction</span></span>

<span data-ttu-id="75a80-106">Surface Hub 2S는 회의실 환경에서 쉽게 공동 작업을 할 수 있도록 디자인 된 windows 10 팀 (windows 10의 사용자 지정 버전)을 사용 하 여 사전 설치 되어 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-106">Surface Hub 2S comes pre-installed with Windows 10 Team, a customized edition of Windows 10 designed to facilitate easy collaboration in meeting room environments.</span></span> <span data-ttu-id="75a80-107">이제 다른 PC와 마찬가지로 Surface Hub 2S를 사용 하기 위해 Windows 10 Pro 또는 Enterprise를 실행 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="75a80-108">일반 업그레이드 또는 마이그레이션과 달리이 프로세스는이 페이지에 설명 된 대로 규범적 절차를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described on this page.</span></span> <span data-ttu-id="75a80-109">계속 하기 전에 [솔루션 구성 요소](#solution-components) 및 [마이그레이션 및 설치 워크플로](#migration-and-installation-workflow-summary) 를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-109">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before proceeding.</span></span>


> [!NOTE]
> <span data-ttu-id="75a80-110">Windows 10 Pro 또는 Enterprise를 설치 하는 경우 기존 Windows 10 팀 라이선스와 별도로 새로운 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-110">When you install Windows 10 Pro or Enterprise, you will need a new licence separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="75a80-111">별도의 PC 및 다운로드 가능한 도구-- **SURFACE UEFI 구성자** 를 사용 하 여 Windows 10 팀에서 마이그레이션을 시작 하 고 Surface Hub 2S에 적용 하는 새 UEFI 설정을 포함 하는 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-111">You start the migration from Windows 10 Team using a separate PC and downloadable tool -- **Surface UEFI Configurator** --  to create a package containing a new UEFI setting that you apply to Surface Hub 2S.</span></span>  <span data-ttu-id="75a80-112">Surface UEFI Configurator는 엔터프라이즈 환경에서 Surface 장치에 대 한 펌웨어 설정을 중앙에서 관리할 수 있도록 디자인 된 Surface X관리 모드 (SEMM)로 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-112">Surface UEFI Configurator functions as an interface into Surface Enterprise Management Mode (SEMM), designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="75a80-113">SEMM에 대해 자세히 알아보려면 [Microsoft Surface Enterprise 관리 모드 설명서](https://docs.microsoft.com/surface/surface-enterprise-management-mode)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75a80-113">To learn more about SEMM, see [Microsoft Surface Enterprise Management Mode documentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 

## <span data-ttu-id="75a80-114">솔루션 구성 요소</span><span class="sxs-lookup"><span data-stu-id="75a80-114">Solution Components</span></span>

- <span data-ttu-id="75a80-115">Windows 10 Team 운영 체제를 실행 하는 Surface Hub 2S 장치</span><span class="sxs-lookup"><span data-stu-id="75a80-115">Surface Hub 2S device running Windows 10 Team operating system</span></span>
- <span data-ttu-id="75a80-116">Windows 10을 실행 하는 별도의 장치</span><span class="sxs-lookup"><span data-stu-id="75a80-116">Separate device running Windows 10</span></span>
- <span data-ttu-id="75a80-117">SEMM 패키지를 만들기 위한 Surface UEFI 구성자 도구</span><span class="sxs-lookup"><span data-stu-id="75a80-117">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="75a80-118">Windows 10 Pro 또는 엔터프라이즈 OS 이미지, 버전 1903 이상</span><span class="sxs-lookup"><span data-stu-id="75a80-118">Windows 10 Pro or Enterprise OS image, version 1903 or greater</span></span>
- <span data-ttu-id="75a80-119">저장 용량이 16GB 인 2 개의 USB 드라이브, FAT32 형식</span><span class="sxs-lookup"><span data-stu-id="75a80-119">Two USB drives with 16GB of storage, FAT32 format</span></span>
- <span data-ttu-id="75a80-120">Surface Hub 2, Windows Installer의 Windows 10 Pro 및 Enterprise 용 드라이버 및 펌웨어. MSI 파일</span><span class="sxs-lookup"><span data-stu-id="75a80-120">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2, Windows Installer .MSI file</span></span>
- <span data-ttu-id="75a80-121">인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="75a80-121">Internet connection</span></span>
- <span data-ttu-id="75a80-122">이미징 솔루션 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="75a80-122">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="75a80-123">마이그레이션 및 설치 워크플로 요약</span><span class="sxs-lookup"><span data-stu-id="75a80-123">Migration and installation workflow summary</span></span>

| <span data-ttu-id="75a80-124">단계</span><span class="sxs-lookup"><span data-stu-id="75a80-124">Step</span></span>  | <span data-ttu-id="75a80-125">작업</span><span class="sxs-lookup"><span data-stu-id="75a80-125">Action</span></span>                                                                                                 | <span data-ttu-id="75a80-126">요약</span><span class="sxs-lookup"><span data-stu-id="75a80-126">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="75a80-127">raid-1</span><span class="sxs-lookup"><span data-stu-id="75a80-127">1</span></span> | [<span data-ttu-id="75a80-128">Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="75a80-128">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="75a80-129">UEFI 버전이 694.2938.768.0 이상 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-129">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="75a80-130">2</span><span class="sxs-lookup"><span data-stu-id="75a80-130">2</span></span> | [<span data-ttu-id="75a80-131">Surface UEFI 구성자 및 Surface Hub 2 드라이버 및 펌웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="75a80-131">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="75a80-132">[IT에 대 한 표면 도구](https://www.microsoft.com/download/details.aspx?id=46703) 페이지에서 다운로드 단추를 선택 하 고 Surface UEFI 구성자를 선택 하 여 다운로드 **합니다. MSI 파일** 을 만들고 별도의 PC에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-132">Select the Download button on the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page, select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC.</span></span> <span data-ttu-id="75a80-133">[Surface Hub 2에서 Windows 10 Pro 및 Enterprise 용 드라이버 및 펌웨어를 다운로드 합니다. MSI 파일](https://www.microsoft.com/download/details.aspx?id=101974) 을 만들고 5 단계에서 사용할 수 있도록 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-133">Download [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) and save it for use in Step 5.</span></span> |
| <span data-ttu-id="75a80-134">3-4</span><span class="sxs-lookup"><span data-stu-id="75a80-134">3</span></span> | [<span data-ttu-id="75a80-135">SEMM 인증서 준비</span><span class="sxs-lookup"><span data-stu-id="75a80-135">Prepare SEMM certificate</span></span>](#prepare-semm-certificate)                                                                          | <span data-ttu-id="75a80-136">Surface UEFI 구성자 실행에 필요한 인증서를 준비 하거나 현재 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-136">Prepare required certificate for running Surface UEFI Configurator or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="75a80-137">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="75a80-137">4</span></span> | [<span data-ttu-id="75a80-138">SEMM 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="75a80-138">Create SEMM package</span></span>](#create-semm-package)                                                                               | <span data-ttu-id="75a80-139">Surface Hub 2S에 적용할 필수 구성 파일을 포함 하는 USB 드라이브에 SEMM 패키지를 만들기 위해 서피스 UEFI 구성자을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-139">Launch Surface UEFI Configurator to create a SEMM package on a USB drive which will contain the required configuration files to apply on Surface Hub 2S.</span></span> <span data-ttu-id="75a80-140">PC의 폴더에이 SEMM 패키지 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-140">Copy these SEMM package  files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="75a80-141">5mb</span><span class="sxs-lookup"><span data-stu-id="75a80-141">5</span></span> | [<span data-ttu-id="75a80-142">Surface Hub 2의 windows 10 Pro 및 Enterprise 용 Windows 10 이미지, SEMM 패키지, 드라이버 및 펌웨어를 포함 하는 USB 플래시 드라이브 준비</span><span class="sxs-lookup"><span data-stu-id="75a80-142">Prepare USB flash drive containing Windows 10 image, SEMM package, and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="75a80-143">Windows 10 이미지를 포함 하는 단일 USB 드라이브 (이 예에서는 **Bootme** )를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-143">Create a single USB drive (named **BOOTME** in this example) containing a Windows 10 image.</span></span> <span data-ttu-id="75a80-144">Surface Hub 2 (단계 2) 및 SEMM 패키지 파일 (4 단계)에 Windows 10 Pro 및 Enterprise 용 드라이버와 펌웨어를 **추가 합니다.**</span><span class="sxs-lookup"><span data-stu-id="75a80-144">Add your Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (Step 2) and SEMM package files (Step 4) to the **BOOTME** drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="75a80-145">26</span><span class="sxs-lookup"><span data-stu-id="75a80-145">6</span></span> | [<span data-ttu-id="75a80-146">OS 마이그레이션을 사용 하도록 Surface Hub 2S에서 UEFI 업데이트</span><span class="sxs-lookup"><span data-stu-id="75a80-146">Update UEFI on Surface Hub 2S to enable OS migration</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="75a80-147">**Bootme** 드라이브를 사용 하 여 UEFI 메뉴로 부팅 Surface Hub 2S를 사용해 서, semm 패키지를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-147">Use the **BOOTME** drive to boot Surface Hub 2S to the UEFI menu and install SEMM package.</span></span>|
| <span data-ttu-id="75a80-148">7</span><span class="sxs-lookup"><span data-stu-id="75a80-148">7</span></span> | [<span data-ttu-id="75a80-149">Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-149">Install Windows 10 Pro or Enterprise version 1903 or later</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="75a80-150">**Bootme** 드라이브를 사용 하 여 **Windows 10 Pro 또는 Enterprise** 버전 1903 이상을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-150">Use the **BOOTME** drive to Install **Windows 10 Pro or Enterprise** version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="75a80-151">20cm(8</span><span class="sxs-lookup"><span data-stu-id="75a80-151">8</span></span> | [<span data-ttu-id="75a80-152">Surface Hub 2에 Windows 10 Pro 및 Enterprise 용 드라이버 및 펌웨어 설치</span><span class="sxs-lookup"><span data-stu-id="75a80-152">Install Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="75a80-153">장치에 최신 업데이트와 드라이버가 모두 있는지 확인 하려면 [Surface Hub 2에 Windows 10 Pro 및 Enterprise 용 드라이버와 펌웨어를 설치 합니다. MSI 파일](https://www.microsoft.com/download/details.aspx?id=101974)</span><span class="sxs-lookup"><span data-stu-id="75a80-153">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974)</span></span>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="75a80-154">되었는지</span><span class="sxs-lookup"><span data-stu-id="75a80-154">9</span></span> | [<span data-ttu-id="75a80-155">Surface Hub 2S을 개인 생산성 장치로 완전히 구성</span><span class="sxs-lookup"><span data-stu-id="75a80-155">Fully configure Surface Hub 2S as a personal productivity device</span></span>](#next-steps)                                        |  <span data-ttu-id="75a80-156">추천 설정 및 응용 프로그램 집합을 사용 하 여 Surface Hub 2S의 사용을 개인 생산성 장치로 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-156">Enable the set of recommended settings and applications to optimize use of Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="75a80-157">Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="75a80-157">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="75a80-158">Surface Hub를 Windows 10 Team에서 Windows 10 데스크톱으로 마이그레이션하기 전에 필요한 최소 UEFI 버전은 **694.2938.768.0**입니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-158">The minimum UEFI version required prior to migrating the Surface Hub from Windows 10 Team to Windows 10 Desktop is **694.2938.768.0**.</span></span>
 
**<span data-ttu-id="75a80-159">시스템에서 현재 UEFI 버전을 확인 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-159">To verify the current UEFI version on your system:</span></span>**

1. <span data-ttu-id="75a80-160">Surface Hub 2S 홈 화면에서 **시작** 을 선택 하 고 **SurfaceApp** (**모든 앱**  >  **화면**)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-160">On Surface Hub 2S home screen, select **Start** and open the **SurfaceApp** (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="75a80-161">장치에서 현재 버전의 UEFI를 포함 하 여 Surface Hub에 대 한 정보를 표시 하려면 **화면** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-161">Select **Your Surface** to display information about the Surface Hub, including the current version of the UEFI on the device.</span></span> <span data-ttu-id="75a80-162">UEFI 버전이 아래와 같이 **694.2938.768.0** 이거나 이후 버전인 경우 OS 마이그레이션을 사용 하도록 설정 하기 위해 UEFI는 semm 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-162">If the UEFI version is **694.2938.768.0** or later as shown below, the UEFI is eligible for you to create the SEMM package to enable OS migration.</span></span>

    ![Surface 앱을 열고 서피스 선택 &](images/shm-fig1.png)
 
3. <span data-ttu-id="75a80-164">UEFI 버전이 버전 **694.2938.768.0**보다 이전인 경우 Windows Update를 사용 하 여 현재 버전을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-164">If the UEFI version is earlier than version **694.2938.768.0**, you will need to obtain a current version using Windows Update.</span></span>

**<span data-ttu-id="75a80-165">Windows Update에서 UEFI를 업데이트 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-165">To update UEFI from Windows Update:</span></span>**

1. <span data-ttu-id="75a80-166">Surface Hub 2S에서 **관리자로**로그인 하 고, **모든 앱**  >  **설정** >  **업데이트 및 보안**  >  **Windows** 로 이동한 다음 모든 업데이트를 업데이트 하 고 설치 하 고, 장치를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-166">On your Surface Hub 2S, sign in as an **Admin**, go to **All apps** > **Settings**> **Update and Security** > **Windows Update** and install all updates, then restart the device.</span></span> <span data-ttu-id="75a80-167">Surface 앱을 사용 하 여 UEFI 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-167">Verify the UEFI version using the Surface App.</span></span> <span data-ttu-id="75a80-168">참고: 사용자 이름 또는 관리자 암호를 모르는 경우에는 장치를 재설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-168">Note: If you do not know your username or admin password, you will need to reset the device.</span></span> <span data-ttu-id="75a80-169">자세한 내용은 [Surface Hub 2S 다시 설정 및 복구](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75a80-169">To learn more, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

2. <span data-ttu-id="75a80-170">UEFI 버전이 **694.2938.768.0** 이상에 도달할 때까지이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-170">Repeat these steps until the UEFI version is **694.2938.768.0** or later.</span></span>

3. <span data-ttu-id="75a80-171">여러 번 시도 했지만 여전히 업데이트 된 UEFI가 표시 되지 않으면 **업데이트 기록을** 확인 하 고 실패 한 펌웨어 설치의 모든 인스턴스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-171">If you still do not see the updated UEFI after multiple attempts, check **Update History** and look for any instances of failed firmware installations.</span></span> <span data-ttu-id="75a80-172">장치를 다시 설정 해야 할 수 있습니다 (**설정**  >  **업데이트 & 보안**  >  **재설정 장치**).</span><span class="sxs-lookup"><span data-stu-id="75a80-172">You may need to reset your device (**Settings** > **Update & security** > **Reset device**).</span></span>

### <span data-ttu-id="75a80-173">Surface UEFI 구성자 및 Surface Hub 2 드라이버 및 펌웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="75a80-173">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="75a80-174">별도의 PC에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-174">On a separate PC:</span></span>

- <span data-ttu-id="75a80-175">Microsoft [SURFACE UEFI 구성자](https://www.microsoft.com/download/details.aspx?id=46703) 를 서피스 도구에서 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-175">Download Microsoft [Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703) from Surface Tools for IT.</span></span> <span data-ttu-id="75a80-176">Surface UEFI Configurator는 Surface Hub 2S에서 실행할 수 없으며, Windows 10 팀이 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-176">Surface UEFI Configurator cannot be run on Surface Hub 2S, while Windows 10 Team is installed.</span></span>

- <span data-ttu-id="75a80-177">[Surface Hub 2 드라이버 및 펌웨어 Windows Installer를 다운로드 합니다. MSI 파일](https://www.microsoft.com/download/details.aspx?id=101974) 을 설치 하 여 새 운영 체제를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-177">Download [Surface Hub 2 Drivers and Firmware Windows Installer .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) to be applied when installing the new operating system.</span></span>

### <span data-ttu-id="75a80-178">SEMM 인증서 준비</span><span class="sxs-lookup"><span data-stu-id="75a80-178">Prepare SEMM certificate</span></span>

<span data-ttu-id="75a80-179">Surface UEFI 구성자을 처음 사용 하는 경우 인증서를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-179">If this is your first time using Surface UEFI Configurator, you’ll need to prepare a certificate.</span></span> <span data-ttu-id="75a80-180">이 인증서는 디바이스를 SEMM에 등록 한 후 승인 된 인증서로 만든 패키지만 UEFI 설정을 수정 하는 데 사용할 수 있도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-180">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify UEFI settings.</span></span> <span data-ttu-id="75a80-181">인증서를 획득 하는 방법은 조직의 규모 또는 복잡도에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-181">How you acquire a certificate may vary depending on the size or complexity of your organization:</span></span>

- <span data-ttu-id="75a80-182">대규모 엔터프라이즈 조직은 일반적으로 표준 보안 관례에 따라 인증서를 생성 하는 고유한 인증서 인프라를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-182">Large enterprise organizations typically maintain their own certificate infrastructure to generate certificates per standard security practices.</span></span>

- <span data-ttu-id="75a80-183">중간 규모 기업과 다른 업체는 타사 공급자 로부터 인증서를 획득 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-183">Medium-sized businesses and others may choose to obtain a certificate from third party providers.</span></span> <span data-ttu-id="75a80-184">이는 IT 전문 지식 또는 전담 IT 보안 팀이 없는 조직에 게 권장 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-184">This is the recommended option for organizations without sufficient IT expertise or dedicated IT security team.</span></span>

- <span data-ttu-id="75a80-185">또는 다음 설명서에 따라 PowerShell 스크립트를 사용 하 여 자체 서명 된 인증서를 생성할 수 있습니다 ( [Surface Enterprise 관리 모드 인증서 요구 사항](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)).</span><span class="sxs-lookup"><span data-stu-id="75a80-185">Alternatively, you can generate a self-signed certificate with a PowerShell script per the following documentation: [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="75a80-186">또는 PowerShell을 사용 하 여 다음 설명서에 따라 고유한 인증서를 만들 수 있습니다: [New-new-selfsignedcertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span><span class="sxs-lookup"><span data-stu-id="75a80-186">Or use PowerShell to create your own certificate per the following documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span></span>

<span data-ttu-id="75a80-187">UEFI 설정을 적용할 수 있으려면 Surface UEFI 구성자 도구를 사용 하 여 만든 SEMM 패키지를 인증서로 보호 하 여 구성 파일의 서명을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-187">The SEMM package created by using the Surface UEFI Configurator tool must be secured with a certificate to verify the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="75a80-188">자세히 알아보려면 [Surface Enterprise 관리 모드](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75a80-188">To learn more, see [Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.</span></span>
 
 
### <span data-ttu-id="75a80-189">SEMM 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="75a80-189">Create SEMM package</span></span>

1. <span data-ttu-id="75a80-190">이전에 다운로드 한 **SURFACE UEFI 구성자** 도구를 별도의 PC에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-190">Install the **Surface UEFI Configurator** tool downloaded earlier to a separate PC.</span></span> 
2. <span data-ttu-id="75a80-191">**SURFACE UEFI 구성자** 를 열고 **시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-191">Open **Surface UEFI Configurator** and select **Start**.</span></span>

   ![Surface UEFI 구성자 열기](images/shm-fig2.png)
   
3. <span data-ttu-id="75a80-193">**Surface 장치** 를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-193">Select **Surface Devices** and then select **Next**.</span></span>

   ![Surface 장치 선택](images/shm-fig3.png)
  
4. <span data-ttu-id="75a80-195">**구성 패키지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-195">Select **Configuration Package**.</span></span>

   ![구성 패키지 선택](images/shm-fig4.png)
  
5. <span data-ttu-id="75a80-197">**인증서 보호**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-197">Select **Certificate Protection**.</span></span>

   ![인증서 보호 선택](images/shm-fig5.png)

6. <span data-ttu-id="75a80-199">인증서 .pfx 파일을 추가 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-199">You will be prompted to add your certificate .pfx file.</span></span>

   ![인증서를 추가 하 라는 메시지가 표시 됩니다.](images/shm-fig6.png)
   
7. <span data-ttu-id="75a80-201">**인증서 암호** 를 입력 하 고 **확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-201">Enter your **Certificate password** and select **OK**.</span></span>

   ![인증서 암호를 입력 하 고 확인을 선택 합니다.](images/shm-fig7.png)

8. <span data-ttu-id="75a80-203">**암호 보호** 를 선택 하 여 Surface UEFI에 암호를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-203">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="75a80-204">UEFI로 부팅할 때마다이 암호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-204">This password will be required whenever you boot to UEFI.</span></span> <span data-ttu-id="75a80-205">Surface Hub 2S에서 사용 하 게 될 UEFI 암호를 설정 하는 것 **이 좋습니다** .</span><span class="sxs-lookup"><span data-stu-id="75a80-205">It is **strongly recommended** to set a UEFI password you will use on Surface Hub 2S.</span></span>

   ![비밀 번호 보호 클릭](images/shm-fig8.png)
   
9. <span data-ttu-id="75a80-207">**UEFI 암호** 를 설정 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-207">Set a **UEFI password** and select **OK**.</span></span>

 > [!IMPORTANT]
   > <span data-ttu-id="75a80-208">Surface Hub 관리를 담당 하는 조직의 IT 관리자가 액세스할 수 있는 안전한 위치에 암호를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-208">Save the password in a secure location accessible to IT admins in your organization responsible for managing Surface Hubs.</span></span> <span data-ttu-id="75a80-209">암호가 손실 되 면 복구 프로세스가 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-209">If the password is lost, there is no recovery process.</span></span> 

   ![UEFI 암호 입력](images/shm-fig9.png)

10. <span data-ttu-id="75a80-211">**Surface Hub 2S** 를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-211">Select **Surface Hub 2S** and then select **Next**.</span></span>

   ![Surface Hub 2S 선택](images/shm-fig10.png)
   
11. <span data-ttu-id="75a80-213">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-213">Select **Next**.</span></span>

    ![다음 선택](images/shm-fig10a.png)

12. <span data-ttu-id="75a80-215">Windows 10 Pro 또는 Enterprise 설치를 허용 하려면 **Os마이그레이션이 enableon을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="75a80-215">To allow installation of Windows 10 Pro or Enterprise, select **EnableOsMigration.**</span></span>

    ![OS 마이그레이션 사용 선택](images/shm-fig11.png)
    
13. <span data-ttu-id="75a80-217">**Enableosmigration** **On** 으로 설정 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-217">Set **EnableOSMigration** to **On** and select **Next**.</span></span>

    ![On으로 OS 마이그레이션 사용 설정](images/shm-fig12.png)

> [!NOTE]
> <span data-ttu-id="75a80-219">SEMM 패키지를 적용 한 후에는 모든 UEFI 설정이 장치에서 UEFI 메뉴에 회색으로 표시 (잠김)로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-219">After you apply a SEMM package, all UEFI settings will display as grayed out (locked) in the UEFI menu on the device.</span></span> <span data-ttu-id="75a80-220">이 값에는 PXE 부팅에 대 한 IPv6 같은 다른 설정의 기본값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-220">This includes default values for other settings such as IPv6 for PXE Boot.</span></span> <span data-ttu-id="75a80-221">UEFI 설정을 수정 하려면 다른 SEMM 패키지를 적용 하거나 h m m m a m m m m에서 장치를 등록 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-221">To modify UEFI settings, you will need to apply another SEMM package or unenroll the device from SEMM.</span></span>

#### <span data-ttu-id="75a80-222">USB 드라이브에 SEMM 패키지 저장</span><span class="sxs-lookup"><span data-stu-id="75a80-222">Save SEMM package to USB drive</span></span>

1. <span data-ttu-id="75a80-223">PC에 USB 드라이브를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-223">Connect a USB Drive to your PC.</span></span> <span data-ttu-id="75a80-224">**Hub 2S** 를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-224">Choose **Hub 2S** and then select **Next**.</span></span>

   ![USB 선택](images/shm-fig13.png)
   
2. <span data-ttu-id="75a80-226">**빌드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-226">Select **Build**.</span></span>

   ![빌드 선택](images/shm-fig14.png)

3. <span data-ttu-id="75a80-228">이 페이지의 스크린샷을 캡처한 다음 **End (종료**)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-228">Capture a screenshot of this page and then select **End**.</span></span> <span data-ttu-id="75a80-229">이제 SEMM 패키지 **Dfciupdate. dfi** 및 인증서의 손도장 (thumbprint)의 마지막 두 문자인 semm 지문이 있는 텍스트 파일이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-229">Your SEMM package is now ready and contains the SEMM package **DfciUpdate.dfi** and a text file with the SEMM thumbprint (the last two characters of the certificate’s thumbprint).</span></span>

   ![종료 선택](images/shm-fig15.png)
   
4. <span data-ttu-id="75a80-231">Surface Hub 2S에 패키지를 적용할 때 SEMM을 활성화 하는 데 필요한 인증서 손도장의 마지막 2 문자를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-231">Save the certificate thumbprint’s last 2 characters, which is required to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="75a80-232">Windows 10 이미지, SEMM 패키지 및 Surface Hub 2 드라이버 및 펌웨어를 포함 하는 USB 플래시 드라이브 준비</span><span class="sxs-lookup"><span data-stu-id="75a80-232">Prepare USB flash drive containing Windows 10 image, SEMM package, and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="75a80-233">다음 옵션 중 하나를 사용 하 여 Windows 10 Pro 또는 엔터프라이즈 이미지 (버전 1903 이상)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-233">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) using one of the following options:</span></span>

- <span data-ttu-id="75a80-234">현재 이미징 솔루션.</span><span class="sxs-lookup"><span data-stu-id="75a80-234">Your current imaging solution.</span></span>

- <span data-ttu-id="75a80-235">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) 를 사용 하면 현재 windows 10 업데이트, Office, 선택한 다른 앱, 필요한 드라이버와 펌웨어를 모두 포함할 수 있는 부팅 가능 Windows 10 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-235">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) lets you create a bootable Windows 10 image which can include all of the current Windows 10 updates, Office, other apps of your choice, as well as the required drivers and firmware.</span></span> 

- <span data-ttu-id="75a80-236">Windows 10 Pro 또는 엔터프라이즈 이미지가 설치 된 USB 플래시 드라이브  [와 Surface Hub 2에 windows 10 pro 및 enterprise 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치한 후</span><span class="sxs-lookup"><span data-stu-id="75a80-236">USB flash drive with Windows 10 Pro or Enterprise image, followed by installing  [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
<span data-ttu-id="75a80-237">이 절차에서는 설치 미디어에서 USB 플래시 드라이브를 만든 다음 Surface Hub 2에서 Windows 10 Pro 및 Enterprise 용 SEMM 패키지 파일 및 드라이버와 펌웨어를 추가 하는 방법에 대해 설명 합니다. MSI 파일.</span><span class="sxs-lookup"><span data-stu-id="75a80-237">This procedure describes creating a USB flash drive from installation media and then adding the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file.</span></span> <span data-ttu-id="75a80-238">다른 배포 방법을 사용 하는 경우 [OS 마이그레이션을 사용 하도록 Surface Hub 2S에서 UEFI를 업데이트 하](#update-uefi-on-surface-hub-2s-to-enable-os-migration)여 다음 섹션으로 진행 하세요.</span><span class="sxs-lookup"><span data-stu-id="75a80-238">If you’re using other deployment methods, proceed to the following section: [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="75a80-239">설치한 후에는 Windows 10 Pro 또는 Windows 10 Enterprise에 대 한 유효한 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-239">Once installed, you will need a valid license for Windows 10 Pro or Windows 10 Enterprise.</span></span>

1. <span data-ttu-id="75a80-240">Windows 10 Pro 설치를 만들려면 **미디어 만들기** 도구 사용에 대 한 [windows 10 다운로드](https://www.microsoft.com/software-download/windows10) 페이지의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-240">To create a Windows 10 Pro installation, follow the instructions on the [Download Windows 10](https://www.microsoft.com/software-download/windows10) page for using the **Media Creation** tool.</span></span> <span data-ttu-id="75a80-241">Windows 10 Enterprise를 다운로드 하려면 [Microsoft 볼륨 라이선스 서비스 센터로](https://www.microsoft.com/licensing/servicecenter/default.aspx)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-241">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center.](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

2. <span data-ttu-id="75a80-242">새 **USB 저장소** 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-242">Insert a new **USB storage** drive.</span></span> <span data-ttu-id="75a80-243">**미디어 만들기** 도구를 시작 하 고 **설치 미디어 만들기** 를 선택한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-243">Launch the **Media Creation** tool, select **Create installation media** and then select **Next**.</span></span>

   ![설치 미디어 만들기](images/shm-fig16.png)
   
3. <span data-ttu-id="75a80-245">언어, Windows 10 및 64 비트 (x64)를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-245">Select language, Windows 10, and 64-bit (x64) and then select **Next**.</span></span>

   ![언어, Windows 10, 64 비트 & 선택 하 고 다음을 선택 합니다.](images/shm-fig17.png)
   
4. <span data-ttu-id="75a80-247">**USB 플래시 드라이브** 를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-247">Select **USB flash drive** and select **Next**.</span></span>

   ![USB 플래시 드라이브를 선택 하 고 다음을 선택 합니다.](images/shm-fig18.png)
   
5. <span data-ttu-id="75a80-249">다운로드가 완료 되 면 **마침을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-249">When the download completes, select **Finish**.</span></span>

   ![마침을 선택 합니다.](images/shm-fig19.png)
   
6. <span data-ttu-id="75a80-251">Windows 10 Pro 및 Enterprise 용 SEMM 패키지 파일과 드라이버 및 펌웨어를 Surface Hub 2 ()에 복사 합니다. MSI 파일)을 Windows 10 이미지를 포함 하는 USB 플래시 드라이브 (**Bootme**)의 루트로</span><span class="sxs-lookup"><span data-stu-id="75a80-251">Copy the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (.MSI file) to the ROOT of the USB flash drive (**BOOTME**) containing your Windows 10 image.</span></span> <span data-ttu-id="75a80-252">부팅 ME USB 드라이브에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-252">BOOTME USB drive contains:</span></span>

    - <span data-ttu-id="75a80-253">Windows 10 부팅 가능 이미지</span><span class="sxs-lookup"><span data-stu-id="75a80-253">Your Windows 10 bootable image</span></span>
    - <span data-ttu-id="75a80-254">SEMM 패키지 파일 (USB 드라이브의 루트에 복사 됨)</span><span class="sxs-lookup"><span data-stu-id="75a80-254">SEMM package files (copied to the root of the USB drive)</span></span>
        - <span data-ttu-id="75a80-255">DfciUpdate. dfi</span><span class="sxs-lookup"><span data-stu-id="75a80-255">DfciUpdate.dfi</span></span>
        - <span data-ttu-id="75a80-256">SEMM 지문이 있는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-256">Text file with the SEMM thumbprint.</span></span> <span data-ttu-id="75a80-257">(이 예에서는 SurfaceUEFI_2020Aug25_1058.txt.</span><span class="sxs-lookup"><span data-stu-id="75a80-257">(In this example: SurfaceUEFI_2020Aug25_1058.txt.</span></span> <span data-ttu-id="75a80-258">자동 생성 날짜 타임 스탬프는 Surface UEFI Configurator를 사용 하 여 파일을 만든 날짜에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-258">The auto-generated date timestamp corresponds to the date that you created the file using Surface UEFI Configurator.)</span></span>
    - <span data-ttu-id="75a80-259">Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)의 Windows 10 Pro 및 Enterprise 용 드라이버 및 펌웨어</span><span class="sxs-lookup"><span data-stu-id="75a80-259">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)</span></span>

### <span data-ttu-id="75a80-260">OS 마이그레이션을 사용 하도록 Surface Hub 2S에서 UEFI 업데이트</span><span class="sxs-lookup"><span data-stu-id="75a80-260">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="75a80-261">**Bootme** 드라이브를 USB-A Surface Hub 2S의 포트에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-261">Insert your **BOOTME** drive into the USB-A port on the Surface Hub 2S.</span></span>

2. <span data-ttu-id="75a80-262">UEFI로 부팅 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-262">To boot into UEFI:</span></span>

   1. <span data-ttu-id="75a80-263">Surface Hub 2S의 첫 번째 전원 끄기 (종료).</span><span class="sxs-lookup"><span data-stu-id="75a80-263">First power off (shutdown) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="75a80-264">**볼륨 +** 를 길게 누른 다음 **전원** 단추를 눌렀다가 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-264">Press and hold **Volume +** and then press and release the **Power** button.</span></span>
   1. <span data-ttu-id="75a80-265">UEFI 메뉴가 나타날 때까지 지주 **볼륨 +** 를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-265">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![UEFI 메뉴가 나타날 때까지 holdling 볼륨을 유지 합니다.](images/shm-fig20.png)
      
3. <span data-ttu-id="75a80-267">장치가 다시 시작 되 면 앞에서 만든 UEFI 암호 (해당 하는 경우)를 입력 합니다 (권장).</span><span class="sxs-lookup"><span data-stu-id="75a80-267">When the device restarts, enter the UEFI password you created earlier, if applicable (strongly recommended).</span></span>

   ![장치가 다시 시작 되 면 UEFI paassword를 입력 합니다.](images/shm-fig22.png)
   
4. <span data-ttu-id="75a80-269">UEFI 메뉴에서 **Management**  >  **USB에서 관리 설치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-269">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![USB에서 설치 & 관리를 선택 합니다.](images/shm-fig21.png)
   
5. <span data-ttu-id="75a80-271">아래와 같이 **지금 다시 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-271">Select **Restart now**, as shown below.</span></span> <span data-ttu-id="75a80-272">장치가 재부팅 되 고 화면 가운데에 흰색 4 사각형 로고가 표시 되 고 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-272">The device will reboot and display the white 4-square logo in the middle of screen and then it will shut down.</span></span>

   ![지금 다시 시작 선택](images/shm-fig25.png)
   
6. <span data-ttu-id="75a80-274">전원 단추를 눌렀다가 놓으면 빨간색 화면에 Surface Enterprise 관리 모드를 활성화 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-274">Press and release the power button, a red screen will display prompting you to activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="75a80-275">두 문자 **인증서 손도장**( **UEFI 설정 암호** )을 입력 한 다음 **확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-275">Enter your two-character **certificate thumbprint**, your **UEFI settings password** and then select **OK**.</span></span>

   ![2 문자 인증서 지문 입력](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="75a80-277">장치에서 SEMM을 활성화 하면 새 UEFI 설정 **Enableosmigration** 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-277">Once you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="75a80-278">더 이상 Windows 10 팀에 액세스할 수 없으며 다음 단계로 진행 하 여 Windows 10 Pro 또는 Windows 10 Enterprise를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-278">You will no longer be able to access Windows 10 Team and must proceed to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

8. <span data-ttu-id="75a80-279">장치가 재부팅 되 고 화면 가운데에 흰색 4 사각형 로고가 표시 된 다음 다시 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-279">The device will reboot, display the white 4-square logo in the middle of the screen, and then again it will shut down</span></span>

### <span data-ttu-id="75a80-280">Windows 10 Pro 또는 Enterprise 설치</span><span class="sxs-lookup"><span data-stu-id="75a80-280">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="75a80-281">부팅 가능 Windows 10 Pro 또는 엔터프라이즈 드라이브가 Surface Hub 2 USB-A 포트에 없으면 지금 삽입 한 다음 전원 단추를 눌렀다가 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-281">If your bootable Windows 10 Pro or Enterprise drive is not already in the Surface Hub 2 USB-A port, insert it now and then press and release the power button.</span></span>

2. <span data-ttu-id="75a80-282">장치가 시작 되 면 화면 가운데에 흰색 4 정사각형이 표시 되 고 흰색 4 사각형 로고 아래에 회전 원이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-282">The device will start, you will see the white 4-square in the middle of the screen, and then you will see a spinning circle below the white four-square logo.</span></span>

3. <span data-ttu-id="75a80-283">장치가 USB 드라이브로 자동으로 부팅 되지 않으면 장치 전원을 끈 다음 (전원 코드를 뽑고 다시 연결).</span><span class="sxs-lookup"><span data-stu-id="75a80-283">If the device does not automatically boot to the USB drive, power off the device (unplug the power cord and plug it back in).</span></span> <span data-ttu-id="75a80-284">전원 코드를 다시 연결한 후에는 화면이 화면 가운데에 있는 흰색 4 개 정사각형 로고까지 몇 초 후에 장치가 부팅 되거나 전원 단추를 눌렀다가 놓아 장치를 다시 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-284">After plugging the power cord back in, the device should boot after a few seconds to the white 4-square logo in the middle of screen, or you can press and release the power button to turn the device back on.</span></span> <span data-ttu-id="75a80-285">화면 가운데에 4 사각형 로고가 표시 되 면 즉시 4도 흰색 사각형 로고 아래에 회전 하는 원이 나타날 때까지 볼륨 작게 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-285">Immediately after you see the 4-square logo in the middle of the screen, press and hold the volume down button until you see the spinning circle below the white four-square logo.</span></span>
 
   ![USB에서 Windows 10으로 부팅](images/shm-fig26.png)
   
4. <span data-ttu-id="75a80-287">OOBE (로그 아웃) 설정이 실행 되 면 지침에 따라 Windows 10 Pro 또는 Enterprise (버전 1903 이상)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-287">When the out of box experience (OOBE) setup launches, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="75a80-288">Surface Hub 2 드라이버 및 펌웨어 설치</span><span class="sxs-lookup"><span data-stu-id="75a80-288">Install Surface Hub 2 drivers and firmware</span></span>

 - <span data-ttu-id="75a80-289">장치에 최신 업데이트와 드라이버가 모두 있는지 확인 하려면 [Surface Hub 2에 Windows 10 Pro 및 Enterprise 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-289">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
### <span data-ttu-id="75a80-290">다음 단계</span><span class="sxs-lookup"><span data-stu-id="75a80-290">Next steps</span></span>

<span data-ttu-id="75a80-291">Surface Hub 2S을 개인 생산성 장치로 완전히 구성 하려면 [Surface hub 2에서 Windows 10 Pro 또는 Enterprise 구성을](surface-hub-2-post-install.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75a80-291">To fully configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="75a80-292">이 문서에 설명 된 단계를 수행 하 여 Surface Hub 2 용 Windows 10 Pro 또는 Enterprise로 장치를 마이그레이션하는 데 실패 한 경우 [Surface Hub 지원](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="75a80-292">If following the steps outlined in this document is unsuccessful in migrating your device to Windows 10 Pro or Enterprise for Surface Hub 2, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

### <span data-ttu-id="75a80-293">Windows 10 팀으로 롤백</span><span class="sxs-lookup"><span data-stu-id="75a80-293">Rolling back to Windows 10 Team</span></span>

<span data-ttu-id="75a80-294">장치를 Windows 10 팀으로 복원 하려는 경우 [Surface Hub 2S 다시 설정 및 복구](surface-hub-2s-recover-reset.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75a80-294">If you would Like to restore your device to Windows 10 Team, refer to [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md)</span></span>

## <span data-ttu-id="75a80-295">버전 기록</span><span class="sxs-lookup"><span data-stu-id="75a80-295">Version history</span></span>

| <span data-ttu-id="75a80-296">버전</span><span class="sxs-lookup"><span data-stu-id="75a80-296">Version</span></span> | <span data-ttu-id="75a80-297">Date</span><span class="sxs-lookup"><span data-stu-id="75a80-297">Date</span></span>               | <span data-ttu-id="75a80-298">설명</span><span class="sxs-lookup"><span data-stu-id="75a80-298">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="75a80-299">variant.</span><span class="sxs-lookup"><span data-stu-id="75a80-299">v.</span></span> <span data-ttu-id="75a80-300">1.2</span><span class="sxs-lookup"><span data-stu-id="75a80-300">1.2</span></span>  | <span data-ttu-id="75a80-301">2020 년 9 월 29 일</span><span class="sxs-lookup"><span data-stu-id="75a80-301">September 29, 2020</span></span> | <span data-ttu-id="75a80-302">사용성 피드백에 대 한 기타 업데이트.</span><span class="sxs-lookup"><span data-stu-id="75a80-302">Miscellaneous updates per usability feedback.</span></span>                                                        |
| <span data-ttu-id="75a80-303">variant.</span><span class="sxs-lookup"><span data-stu-id="75a80-303">v.</span></span> <span data-ttu-id="75a80-304">1.1</span><span class="sxs-lookup"><span data-stu-id="75a80-304">1.1</span></span>  | <span data-ttu-id="75a80-305">2020 년 9 월 15 일</span><span class="sxs-lookup"><span data-stu-id="75a80-305">September 15, 2020</span></span> | <span data-ttu-id="75a80-306">새 OS 설치에 대 한 추가 정보를 소개 하 고 도입 된 라이선스 요구 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a80-306">Placed additional note in the Introduction clarifying licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="75a80-307">variant.</span><span class="sxs-lookup"><span data-stu-id="75a80-307">v.</span></span> <span data-ttu-id="75a80-308">1.0</span><span class="sxs-lookup"><span data-stu-id="75a80-308">1.0</span></span>  | <span data-ttu-id="75a80-309">2020 년 9 월 1 일</span><span class="sxs-lookup"><span data-stu-id="75a80-309">September 1, 2020</span></span>  | <span data-ttu-id="75a80-310">새 문서.</span><span class="sxs-lookup"><span data-stu-id="75a80-310">New article.</span></span>                                                                                           |
