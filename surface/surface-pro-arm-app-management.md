---
title: Surface Pro X 배포, 관리 및 서비스
description: 이 문서에서는 Surface Pro X의 배포, 관리 및 서비스에 대한 주요 고려 사항에 대한 개요를 제공합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/15/2021
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 30f7cd7d861b6497cd536aeb0ea348b6946a2674
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271362"
---
# <span data-ttu-id="58718-103">Surface Pro X 배포, 관리 및 서비스</span><span class="sxs-lookup"><span data-stu-id="58718-103">Deploying, managing, and servicing Surface Pro X</span></span>

## <span data-ttu-id="58718-104">소개</span><span class="sxs-lookup"><span data-stu-id="58718-104">Introduction</span></span>

<span data-ttu-id="58718-105">고성능 상용 요구 사항을 처리하도록 제작된 Surface Pro X는 동급에서 가장 강력한 프로세서인 Microsoft SQ1 및 Microsoft SQ1 ARM 칩셋을 통합하여 새로운 지평을 마련했습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-105">Built to handle high performance commercial requirements, Surface Pro X breaks new ground by incorporating the most powerful processors in its class, the Microsoft SQ1 and Microsoft SQ1 ARM chipsets.</span></span>

<span data-ttu-id="58718-106">3GHz CPU와 2.1 테라플롭 GPU로 구동되는 Surface Pro X는 완전한 Windows 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-106">Powered by a 3GHz CPU and a 2.1 teraflop GPU, Surface Pro X provides a full Windows experience.</span></span> <span data-ttu-id="58718-107">15시간의 배터리 사용 시간이 내장된 기가비트 LTE와 터치, 펜, 태블릿 및 노트북의 다양성으로 금융, 법률 및 의료 분야의 모바일 일선 근로자 및 전문가 또는 연장된 배터리 사용 시간 및 지속적인 연결 기능을 요구하는 모든 역할에 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="58718-107">Its 15-hour battery life built-in Gigabit LTE and the versatility of touch, pen, tablet, and laptop make it ideally suited for mobile first-line workers and professionals across the financial, legal, and medical fields or any role demanding extended battery life and continuous connectivity capabilities.</span></span>

<span data-ttu-id="58718-108">Surface Pro X는 Microsoft 365, Intune 및 Windows Autopilot과 함께 사용될 때 최고의 성능을 발휘하며, 최신 클라우드 기반 환경을 위해 거의 독점적으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-108">Surface Pro X is designed almost exclusively for a modern, cloud-based environment and works best when paired with Microsoft 365, Intune and Windows Autopilot.</span></span> <span data-ttu-id="58718-109">이 문서에서는 어떻게 Surface Pro X를 배포, 관리 및 서비스하는지 설명하고 이를 위한 주요 고려 사항을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-109">This article highlights what that looks like and outlines key considerations for deploying, managing, and servicing Surface Pro X.</span></span>

## <span data-ttu-id="58718-110">Surface Pro X 배포</span><span class="sxs-lookup"><span data-stu-id="58718-110">Deploying Surface Pro X</span></span>

<span data-ttu-id="58718-111">최상의 환경을 위해 Microsoft 클라우드 솔루션 공급자의 도움을 받아 Windows Autopilot을 사용하여 Surface Pro X를 프로비저닝하거나 Autopilot 배포 프로필 밀 관련 기능을 사용하여 자체 프로비저닝합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-111">For the best experience, deploy Surface Pro X using Windows Autopilot either with the assistance of a Microsoft Cloud Solution Provider or self-provisioned using Autopilot deployment profiles and related features.</span></span> <span data-ttu-id="58718-112">자세한 내용은 다음을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="58718-112">For more information, refer to:</span></span>

- [<span data-ttu-id="58718-113">Windows Autopilot 및 Surface 디바이스</span><span class="sxs-lookup"><span data-stu-id="58718-113">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md)
- [<span data-ttu-id="58718-114">Windows Autopilot 개요</span><span class="sxs-lookup"><span data-stu-id="58718-114">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)

<span data-ttu-id="58718-115">Autopilot 배포에는 몇 가지 장점이 있습니다. Office Pro Plus의 사전 설치를 포함하도록 제로 터치 배포를 위해 간소화된 공장 프로비저닝 운영 체제를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-115">Autopilot deployment has several advantages: It allows you to use the factory provisioned operating system, streamlined for zero-touch deployment, to include pre-installation of Office Pro Plus.</span></span>

<span data-ttu-id="58718-116">최신 관리, 보안 및 생산성 솔루션을 이미 사용하는 조직은 Surface Pro X의 고유한 성능 기능의 이점을 잘 활용할 수 있는 위치에 있습니다. 현대화된 비즈니스 앱, Microsoft Store(UWP) 앱 또는 원격 데스크톱 솔루션을 사용하는 고객 또한 혜택을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-116">Organizations already using modern management, security, and productivity solutions are well positioned to take advantage of the unique performance features in Surface Pro X. Customers using modernized line of business apps, Microsoft store (UWP) apps, or remote desktop solutions also stand to benefit.</span></span>

## <span data-ttu-id="58718-117">이미지 기반 배포 고려 사항</span><span class="sxs-lookup"><span data-stu-id="58718-117">Image-based deployment considerations</span></span>

<span data-ttu-id="58718-118">Microsoft Deployment Toolkit(MDT) 및 Microsoft Endpoint Configuration Manager(이전의 System Center Configuration Manager)는 현재 운영 체제 배포를 위해 Surface Pro X를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-118">Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager (formerly System Center Configuration Manager) currently do not support Surface Pro X for operating system deployment.</span></span> <span data-ttu-id="58718-119">이미지 기반 배포에 의존하는 고객은 Surface Pro 7+을 고려하는 동시에 최신 배포 솔루션으로 전환할 적절한 시기를 계속 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-119">Customers relying on image-based deployment should consider Surface Pro 7+ while they continue to evaluate the right time to transition to modern deployment solutions.</span></span> 

## <span data-ttu-id="58718-120">Surface Pro X 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="58718-120">Managing Surface Pro X devices</span></span>

### <span data-ttu-id="58718-121">Intune</span><span class="sxs-lookup"><span data-stu-id="58718-121">Intune</span></span>

<span data-ttu-id="58718-122">Microsoft Enterprise Mobility + Security의 구성 요소인 Intune은 ID 및 액세스 제어를 위해 Azure Active Directory와 통합되며 등록된 Surface Pro X 디바이스의 세부적인 관리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-122">A component of Microsoft Enterprise Mobility + Security, Intune integrates with Azure Active Directory for identity and access control and provides granular management of enrolled Surface Pro X devices.</span></span> <span data-ttu-id="58718-123">Intune 모바일 디바이스 관리(MDM) 정책에는 Windows 그룹 정책과 같은 이전 온-프레미스 도구에 비해 여러 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-123">Intune mobile device management (MDM) policies have a number of advantages over older on-premises tools such as Windows Group Policy.</span></span> <span data-ttu-id="58718-124">여기에는 더 빠른 디바이스 로그인 시간과 클라우드에서 전체 디바이스 관리를 가능하게 하는 보다 간소화된 정책 카탈로그가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58718-124">This includes faster device login times and a more streamlined catalog of policies enabling full device management from the cloud.</span></span> <span data-ttu-id="58718-125">예를 들어 eSIM 프로필을 사용하여 LTE를 관리하여 데이터 요금제를 구성하고 활성화 코드를 여러 디바이스에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-125">For example, you can manage LTE using eSIM profiles to configure data plans and deploy activation codes to multiple devices.</span></span><br> 

<span data-ttu-id="58718-126">Intune을 사용하는 방법에 대한 자세한 내용은 [Intune 설명서](https://docs.microsoft.com/intune/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58718-126">For more information about using Intune, refer to the [Intune documentation](https://docs.microsoft.com/intune/).</span></span>

### <span data-ttu-id="58718-127">공동 관리</span><span class="sxs-lookup"><span data-stu-id="58718-127">Co-management</span></span>

<span data-ttu-id="58718-128">Autopilot에 배포하면 Surface Pro X 디바이스를 Azure AD 또는 Active Directory(하이브리드 Azure AD 가입)에 등록하여 Intune으로 디바이스를 관리하거나 32비트 x86 ConfigMgr 클라이언트를 설치하는 Endpoint Configuration Manager로 공동 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-128">Once deployed in Autopilot, you can join Surface Pro X devices to Azure AD or Active Directory (Hybrid Azure AD Join) where you will be able to manage the devices with Intune or co-manage them with Endpoint Configuration Manager, which will install the 32-bit x86 ConfigMgr client.</span></span>

### <span data-ttu-id="58718-129">타사 MDM 솔루션</span><span class="sxs-lookup"><span data-stu-id="58718-129">Third party MDM solutions</span></span>

<span data-ttu-id="58718-130">타사 MDM 도구를 사용하여 Surface Pro X 디바이스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-130">You may be able to use third-party MDM tools to manage Surface Pro X devices.</span></span> <span data-ttu-id="58718-131">자세한 내용은 MDM 공급자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="58718-131">For details, contact your MDM provider.</span></span>

### <span data-ttu-id="58718-132">바이러스 백신 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="58718-132">Antivirus software</span></span>

<span data-ttu-id="58718-133">Windows Defender는 Windows 10 디바이스의 지원되는 수명 동안 ARM 기반 PC에서 Windows 10을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58718-133">Windows Defender will help protect Windows 10 on ARM-based PCs for the supported lifetime of the Windows 10 device.</span></span> 

<span data-ttu-id="58718-134">일부 타사 바이러스 백신 소프트웨어는 ARM 기반 프로세서에서 실행되는 Windows 10 PC에 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-134">Some third-party antivirus software cannot be installed on a Windows 10 PC running on an ARM-based processor.</span></span> <span data-ttu-id="58718-135">ARM 기반 PC에서의 AV 앱 준비를 위해 타사 바이러스 백신 소프트웨어 공급자와의 협업이 계속되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-135">Collaboration with third-party antivirus software providers is continuing for AV app readiness on ARM-based PCs.</span></span> <span data-ttu-id="58718-136">바이러스 백신 소프트웨어 공급자에게 문의하여 앱을 사용할 수 있는 시기를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="58718-136">Contact your antivirus software provider to understand when their apps will be available.</span></span>

## <span data-ttu-id="58718-137">Surface Pro X 서비스</span><span class="sxs-lookup"><span data-stu-id="58718-137">Servicing Surface Pro X</span></span>

<span data-ttu-id="58718-138">Surface Pro X는 Windows 10 버전 2004와 함께 제공되며 Windows 10 버전 1903 이상을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-138">Surface Pro X ships with Windows 10 version 2004 and supports Windows 10, version 1903 and later.</span></span> <span data-ttu-id="58718-139">ARM 기반 디바이스로서 최신 드라이버 및 펌웨어를 유지 관리하기 위한 특정 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-139">As an ARM-based device, it has specific requirements for maintaining the latest drivers and firmware.</span></span> 

<span data-ttu-id="58718-140">Surface Pro X는 Windows 업데이트를 사용하여 가정 사용자와 소규모 비즈니스 사용자 모두가 드라이버와 펌웨어를 최신 상태로 유지하는 프로세스를 간소화하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-140">Surface Pro X was designed to use Windows Update to simplify the process of keeping drivers and firmware up to date for both home users and small business users.</span></span> <span data-ttu-id="58718-141">기본 설정을 사용하여 자동 업데이트를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-141">Use the default settings to receive Automatic updates.</span></span>  <span data-ttu-id="58718-142">확인하려면:</span><span class="sxs-lookup"><span data-stu-id="58718-142">To verify:</span></span>

1. <span data-ttu-id="58718-143">**시작** > **설정 > 업데이트 및 보안 > Windows 업데이트** > **고급 옵션**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-143">Go to **Start** > **Settings > Update & Security > Windows Update** > **Advanced Options.**</span></span>
2. <span data-ttu-id="58718-144">**업데이트 설치 방법 선택**에서 **자동(권장)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-144">Under **Choose how updates are installed,** select **Automatic (recommended)**.</span></span>

### <span data-ttu-id="58718-145">상용 고객을 위한 권장 사항</span><span class="sxs-lookup"><span data-stu-id="58718-145">Recommendations for commercial customers</span></span>

- <span data-ttu-id="58718-146">최신 드라이버 및 펌웨어를 유지 관리하기 위해 Windows 업데이트 또는 비즈니스용 Windows 업데이트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-146">Use Windows Update or Windows Update for Business for maintaining the latest drivers and firmware.</span></span> <span data-ttu-id="58718-147">자세한 내용은 [비즈니스용 Windows 업데이트를 사용하여 업데이트 배포](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58718-147">For more information, see [Deploy Updates using Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb).</span></span>
- <span data-ttu-id="58718-148">Surface 장치에서 업데이트 배포 및 관리에 대한 자세한 내용은 [ Surface 드라이버 및 펌웨어 업데이트 관리 및 배포 ](manage-surface-driver-and-firmware-updates.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="58718-148">For more information about deploying and managing updates on Surface devices, see [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span>
- <span data-ttu-id="58718-149">Windows Server Update Services(WSUS)는 Surface Pro X에 드라이버와 펌웨어를 제공하는 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-149">Note that Windows Server Update Services (WSUS) does not support the ability to deliver drivers and firmware to Surface Pro X.</span></span>

## <span data-ttu-id="58718-150">Surface Pro X에서 앱 실행</span><span class="sxs-lookup"><span data-stu-id="58718-150">Running apps on Surface Pro X</span></span>

<span data-ttu-id="58718-151">대부분의 앱은 제한된 예외가 있는 ARM 기반 Windows 10 PC에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58718-151">Most apps run on ARM-based Windows 10 PCs with limited exclusions.</span></span>

### <span data-ttu-id="58718-152">지원되는 앱</span><span class="sxs-lookup"><span data-stu-id="58718-152">Supported apps</span></span>

- <span data-ttu-id="58718-153">대부분의 x86 Win32 앱은 Surface Pro X에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58718-153">Most x86 Win32 apps run on Surface Pro X.</span></span>
- <span data-ttu-id="58718-154">네이티브 ARM64 및 Microsoft Store UWP 앱은 배터리 사용 시간을 최적화하면서 ARM 기반 프로세서의 최대 기본 속도를 활용하는 탁월한 사용자 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-154">Native ARM64 and Microsoft Store UWP apps provide an excellent user experience utilizing the full native speed of the ARM-based processor while optimizing battery life.</span></span>
- <span data-ttu-id="58718-155">ARM 기반 프로세서에서 실행되는 Windows 10 PC용으로 설계된 드라이버를 사용하는 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="58718-155">Apps that use drivers designed for a Windows 10 PC running on an ARM-based processor.</span></span>

> [!NOTE]
> <span data-ttu-id="58718-156">Windows 참가자 프로그램을 통해 미리 보기에서 64 비트 에뮬레이션을 사용하면 Surface Pro X에서 64 비트(x64) 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-156">With 64-bit emulation coming soon in Preview via the Windows Insider program, you'll be able to run 64-bit (x64) apps on Surface Pro X.</span></span>

### <span data-ttu-id="58718-157">FastTrack App Assure</span><span class="sxs-lookup"><span data-stu-id="58718-157">FastTrack App Assure</span></span> 

<span data-ttu-id="58718-158">App Assure 프로그램은 LOB, ISV 및 ARM 기반 Windoes 10을 대상으로하는 Microsoft 자사 앱을 사용하는 상용 고객에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="58718-158">The App Assure program is available to commercial customers for their LOB, ISV and Microsoft first-party apps targeting Windows 10 on ARM.</span></span> <span data-ttu-id="58718-159">상용 고객이 ARM에서 Windows 10을 사용할 때 앱 호환성 문제가 발생하는 경우, Microsoft는 추가 비용없이 문제를 해결하고 앱 수정을 지원하기 위하여 개발자 리소스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-159">If commercial customers encounter an app compatibility issue using Windows 10 on ARM, Microsoft will provide developer resources to troubleshoot and assist with app remediations, at no additional cost.</span></span> <span data-ttu-id="58718-160">자세히 알아보려면 [aka.ms/AppAssure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="58718-160">To learn more,visit [aka.ms/AppAssure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure).</span></span>

<span data-ttu-id="58718-161">Surface Pro X에서 앱을 실행하는 방법에 대한 자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="58718-161">For more information about running apps on Surface Pro X, refer to:</span></span>

- [<span data-ttu-id="58718-162">Windows 10 ARM 기반 PC 지원 FAQ</span><span class="sxs-lookup"><span data-stu-id="58718-162">Windows 10 ARM-based PCs Support FAQ</span></span>](https://support.microsoft.com/help/4521606)
- [<span data-ttu-id="58718-163">ARM의 Windows 10 설명서</span><span class="sxs-lookup"><span data-stu-id="58718-163">Windows 10 on ARM documentation</span></span>](https://docs.microsoft.com/windows/arm)

## <span data-ttu-id="58718-164">가상 데스크톱(VDI)</span><span class="sxs-lookup"><span data-stu-id="58718-164">Virtual Desktops (VDI)</span></span>

<span data-ttu-id="58718-165">Windows Virtual Desktop을 사용하면 모든 위치에서 모든 컴퓨팅 디바이스 또는 플랫폼에서 Windows 데스크톱, 애플리케이션 및 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-165">Windows Virtual Desktop enables access to Windows desktops,applications, and data on any computing device or platform, from any location.</span></span> <span data-ttu-id="58718-166">자세한 내용은 [Windows Virtual Desktop 사이트](https://aka.ms/wvd)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="58718-166">To learn more, refer to the [Windows Virtual Desktop site](https://aka.ms/wvd).</span></span> 

## <span data-ttu-id="58718-167">Surface Pro X로 브라우징</span><span class="sxs-lookup"><span data-stu-id="58718-167">Browsing with Surface Pro X</span></span>

<span data-ttu-id="58718-168">인기 있는 브라우저가 Surface Pro X에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58718-168">Popular browsers run on Surface Pro X:</span></span>

- <span data-ttu-id="58718-169">기본 제공 Edge, Firefox, Chrome, Internet Explorer 모두 Surface Pro X에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58718-169">In-box Edge, Firefox, Chrome, and Internet Explorer all run on Surface Pro X.</span></span>
- <span data-ttu-id="58718-170">Chromium 기반 Firefox 및 Microsoft Edge가 기본적으로 실행되므로 ARM 기반 프로세서의 Windows 10 PC에서 향상된 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-170">Firefox and Microsoft Edge based on Chromium run natively and therefore have enhanced performance on a Windows 10 PC on an ARM-based processor.</span></span>

## <span data-ttu-id="58718-171">Microsoft Office 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="58718-171">Installing and using Microsoft Office</span></span>

- <span data-ttu-id="58718-172">ARM 기반 프로세서의 Windows 10 PC에서 최상의 환경을 위해 Office 365를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="58718-172">Use Office 365 for the best experience on a Windows 10 PC on an ARM-based processor.</span></span>
- <span data-ttu-id="58718-173">Office 365 “간편 실행”은 ARM 기반 프로세서의 Windows 10 PC에서 실행되도록 최적화된 Outlook, Word, Excel, PowerPoint를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-173">Office 365 "click-to-run" installs Outlook, Word, Excel, and PowerPoint, optimized to run on a Windows 10 PC on an ARM-based processor.</span></span>
- <span data-ttu-id="58718-174">Microsoft Teams는 Surface Pro X에서 잘 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58718-174">Microsoft Teams runs great on Surface Pro X.</span></span>
- <span data-ttu-id="58718-175">Office 2019와 같은 Office의 "영구 버전"의 경우 32비트 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-175">For "perpetual versions" of Office such as Office 2019, install the 32-bit version.</span></span>

## <span data-ttu-id="58718-176">VPN</span><span class="sxs-lookup"><span data-stu-id="58718-176">VPN</span></span>

<span data-ttu-id="58718-177">특정 타사 VPN이 ARM 기반 프로세서에서 Windows 10 PC를 지원하는지 확인하려면 VPN 공급자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="58718-177">To confirm if a specific third-party VPN supports a Windows 10 PC on an ARM-based processor, contact the VPN provider.</span></span>

## <span data-ttu-id="58718-178">기능 요약</span><span class="sxs-lookup"><span data-stu-id="58718-178">Feature summary</span></span>

<span data-ttu-id="58718-179">다음 표는 ARM 기반 Windows 10이 설치된 Surface Pro X에서 선별된 주요 기능의 가용성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="58718-179">The following tables show the availability of selected key features on Surface Pro X with Windows 10 on ARM.</span></span>


**<span data-ttu-id="58718-180">배포</span><span class="sxs-lookup"><span data-stu-id="58718-180">Deployment</span></span>**

| <span data-ttu-id="58718-181">기능</span><span class="sxs-lookup"><span data-stu-id="58718-181">Feature</span></span>                                                           | <span data-ttu-id="58718-182">예/아니오</span><span class="sxs-lookup"><span data-stu-id="58718-182">Y/N</span></span> | <span data-ttu-id="58718-183">참고</span><span class="sxs-lookup"><span data-stu-id="58718-183">Notes</span></span>                                                                                                                             |
| ----------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="58718-184">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="58718-184">Windows Autopilot</span></span>                                                 | <span data-ttu-id="58718-185">예</span><span class="sxs-lookup"><span data-stu-id="58718-185">Yes</span></span> |                                                                                                                                   |
| <span data-ttu-id="58718-186">네트워크 부팅 지원(PXE)</span><span class="sxs-lookup"><span data-stu-id="58718-186">Support for Network Boot (PXE)</span></span>                                    | <span data-ttu-id="58718-187">아니오</span><span class="sxs-lookup"><span data-stu-id="58718-187">No</span></span>  |                                                                                                                                   |
| <span data-ttu-id="58718-188">Windows 구성 디자이너</span><span class="sxs-lookup"><span data-stu-id="58718-188">Windows Configuration Designer</span></span>                                    | <span data-ttu-id="58718-189">아니오</span><span class="sxs-lookup"><span data-stu-id="58718-189">No</span></span>  | <span data-ttu-id="58718-190">Surface Pro X에 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-190">Not recommended for Surface Pro X.</span></span>                                                                                                |
| <span data-ttu-id="58718-191">WinPE</span><span class="sxs-lookup"><span data-stu-id="58718-191">WinPE</span></span>                                                             | <span data-ttu-id="58718-192">예</span><span class="sxs-lookup"><span data-stu-id="58718-192">Yes</span></span> | <span data-ttu-id="58718-193">Surface Pro X에 권장하지 않습니다. Microsoft는 Surface Pro X에서 WinPE를 지원하기 위해 필수 .ISO 및 드라이버를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-193">Not recommended for Surface Pro X. Microsoft does not provide the necessary .ISO and drivers to support WinPE with Surface Pro X.</span></span> |
| <span data-ttu-id="58718-194">Endpoint Configuration Manager: 운영 체제 배포(OSD)</span><span class="sxs-lookup"><span data-stu-id="58718-194">Endpoint Configuration Manager: Operating System Deployment (OSD)</span></span> | <span data-ttu-id="58718-195">아니오</span><span class="sxs-lookup"><span data-stu-id="58718-195">No</span></span>  | <span data-ttu-id="58718-196">Surface Pro X에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-196">Not supported on Surface Pro X.</span></span>                                                                                                   |
| <span data-ttu-id="58718-197">MDT</span><span class="sxs-lookup"><span data-stu-id="58718-197">MDT</span></span>                                                               | <span data-ttu-id="58718-198">아니오</span><span class="sxs-lookup"><span data-stu-id="58718-198">No</span></span>  | <span data-ttu-id="58718-199">Surface Pro X에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-199">Not supported on Surface Pro X.</span></span>                                                                                                   |

 
 
 **<span data-ttu-id="58718-200">Management</span><span class="sxs-lookup"><span data-stu-id="58718-200">Management</span></span>**
 

| <span data-ttu-id="58718-201">기능</span><span class="sxs-lookup"><span data-stu-id="58718-201">Feature</span></span>                                       | <span data-ttu-id="58718-202">예/아니오</span><span class="sxs-lookup"><span data-stu-id="58718-202">Y/N</span></span>     | <span data-ttu-id="58718-203">참고</span><span class="sxs-lookup"><span data-stu-id="58718-203">Notes</span></span>                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="58718-204">Intune</span><span class="sxs-lookup"><span data-stu-id="58718-204">Intune</span></span>                                        | <span data-ttu-id="58718-205">예</span><span class="sxs-lookup"><span data-stu-id="58718-205">Yes</span></span>     | <span data-ttu-id="58718-206">eSIM 프로필이 제공되는 LTE를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-206">Manage LTE with eSIM profiles.</span></span>                                                        |
| <span data-ttu-id="58718-207">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="58718-207">Windows Autopilot</span></span>                             | <span data-ttu-id="58718-208">예</span><span class="sxs-lookup"><span data-stu-id="58718-208">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="58718-209">Azure AD(공동 관리)</span><span class="sxs-lookup"><span data-stu-id="58718-209">Azure AD (co-management)</span></span>                      | <span data-ttu-id="58718-210">예</span><span class="sxs-lookup"><span data-stu-id="58718-210">Yes</span></span>     | <span data-ttu-id="58718-211">Surface Pro X를 Azure AD 또는 Active Directory(하이브리드 Azure AD 가입)에 가입시키는 기능.</span><span class="sxs-lookup"><span data-stu-id="58718-211">Ability to join Surface Pro X to Azure AD or Active Directory (Hybrid Azure AD Join).</span></span> |
| <span data-ttu-id="58718-212">Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="58718-212">Endpoint Configuration Manager</span></span>                | <span data-ttu-id="58718-213">예</span><span class="sxs-lookup"><span data-stu-id="58718-213">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="58718-214">AC 복원 시 전원 켜기</span><span class="sxs-lookup"><span data-stu-id="58718-214">Power on When AC Restore</span></span>                      | <span data-ttu-id="58718-215">예</span><span class="sxs-lookup"><span data-stu-id="58718-215">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="58718-216">비즈니스용 Surface 진단 도구 키트(SDT)</span><span class="sxs-lookup"><span data-stu-id="58718-216">Surface Diagnostic Toolkit (SDT) for Business</span></span> | <span data-ttu-id="58718-217">예</span><span class="sxs-lookup"><span data-stu-id="58718-217">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="58718-218">Surface 자산 태그 도구</span><span class="sxs-lookup"><span data-stu-id="58718-218">Surface Asset Tag tool</span></span>                        | <span data-ttu-id="58718-219">예</span><span class="sxs-lookup"><span data-stu-id="58718-219">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="58718-220">Surface 엔터프라이즈 관리 모드(SEMM)</span><span class="sxs-lookup"><span data-stu-id="58718-220">Surface Enterprise management Mode (SEMM)</span></span>     | <span data-ttu-id="58718-221">부분</span><span class="sxs-lookup"><span data-stu-id="58718-221">Partial</span></span> | <span data-ttu-id="58718-222">펌웨어 수준에서 Surface Pro X에서 하드웨어를 비활성화할 수 있는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-222">No option to disable hardware on Surface Pro X at the firmware level.</span></span>                 |
| <span data-ttu-id="58718-223">Surface UEFI 구성기</span><span class="sxs-lookup"><span data-stu-id="58718-223">Surface UEFI Configurator</span></span>                     | <span data-ttu-id="58718-224">아니오</span><span class="sxs-lookup"><span data-stu-id="58718-224">No</span></span>      | <span data-ttu-id="58718-225">하드웨어를 비활성화하는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-225">No option to disable hardware.</span></span> <span data-ttu-id="58718-226">펌웨어 수준에서 Surface Pro X에서.</span><span class="sxs-lookup"><span data-stu-id="58718-226">on Surface Pro X at the firmware level.</span></span>                |
| <span data-ttu-id="58718-227">Surface UEFI 관리자</span><span class="sxs-lookup"><span data-stu-id="58718-227">Surface UEFI Manager</span></span>                          | <span data-ttu-id="58718-228">부분</span><span class="sxs-lookup"><span data-stu-id="58718-228">Partial</span></span> | <span data-ttu-id="58718-229">펌웨어 수준에서 Surface Pro X에서 하드웨어를 비활성화할 수 있는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-229">No option to disable hardware on Surface Pro X at the firmware level.</span></span>                 |

 

**<span data-ttu-id="58718-230">보안</span><span class="sxs-lookup"><span data-stu-id="58718-230">Security</span></span>**
 

 <span data-ttu-id="58718-231">기능</span><span class="sxs-lookup"><span data-stu-id="58718-231">Feature</span></span>                                       | <span data-ttu-id="58718-232">예/아니오</span><span class="sxs-lookup"><span data-stu-id="58718-232">Y/N</span></span>     | <span data-ttu-id="58718-233">참고</span><span class="sxs-lookup"><span data-stu-id="58718-233">Notes</span></span>                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="58718-234">BitLocker</span><span class="sxs-lookup"><span data-stu-id="58718-234">BitLocker</span></span>                                     | <span data-ttu-id="58718-235">예</span><span class="sxs-lookup"><span data-stu-id="58718-235">Yes</span></span>     |                                                       |
| <span data-ttu-id="58718-236">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="58718-236">Windows Defender</span></span>                              | <span data-ttu-id="58718-237">예</span><span class="sxs-lookup"><span data-stu-id="58718-237">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="58718-238">타사 바이러스 백신에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="58718-238">Support for third-party antivirus</span></span>             | <span data-ttu-id="58718-239">메모 참고</span><span class="sxs-lookup"><span data-stu-id="58718-239">See note</span></span>| <span data-ttu-id="58718-240">일부 타사 바이러스 백신 소프트웨어는 ARM 기반 프로세서에서 실행되는 Windows 10 PC에 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-240">Some third-party antivirus software cannot be installed on a Windows 10 PC running on an ARM-based processor.</span></span> <span data-ttu-id="58718-241">ARM 기반 PC에서의 AV 앱 준비를 위해 타사 바이러스 백신 소프트웨어 공급자와의 협업이 계속되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-241">Collaboration with third-party antivirus software providers is continuing for AV app readiness on ARM-based PCs.</span></span> <span data-ttu-id="58718-242">바이러스 백신 소프트웨어 공급자에게 문의하여 앱을 사용할 수 있는 시기를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="58718-242">Contact your antivirus software provider to understand when their apps will be available.</span></span> |
| <span data-ttu-id="58718-243">보안 부팅</span><span class="sxs-lookup"><span data-stu-id="58718-243">Secure Boot</span></span>               | <span data-ttu-id="58718-244">예</span><span class="sxs-lookup"><span data-stu-id="58718-244">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="58718-245">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="58718-245">Windows Information Protection</span></span>                      | <span data-ttu-id="58718-246">예</span><span class="sxs-lookup"><span data-stu-id="58718-246">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="58718-247">Surface 데이터 지우개(SDE)</span><span class="sxs-lookup"><span data-stu-id="58718-247">Surface Data Eraser (SDE)</span></span>     | <span data-ttu-id="58718-248">예</span><span class="sxs-lookup"><span data-stu-id="58718-248">Yes</span></span>     |                                                                                       |




## <span data-ttu-id="58718-249">FAQ</span><span class="sxs-lookup"><span data-stu-id="58718-249">FAQ</span></span>

### <span data-ttu-id="58718-250">MDT 또는 Endpoint Configuration Manager로 Surface Pro X를 배포할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="58718-250">Can I deploy Surface Pro X with MDT or Endpoint Configuration Manager?</span></span>

<span data-ttu-id="58718-251">MDT(Microsoft 배포 도구 키트) 및 Microsoft Endpoint Configuration Manager는 현재 운영 체제 배포를 위해 Surface Pro X를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-251">The Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager  currently do not support Surface Pro X for operating system deployment.</span></span> <span data-ttu-id="58718-252">이미지 기반 배포에 의존하는 고객은 Surface Pro 7+을 고려하는 동시에 클라우드로 전환할 적절한 시기를 계속 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-252">Customers relying on image-based deployment should consider Surface Pro 7+ while they continue to evaluate the right time to transition to the cloud.</span></span>

### <span data-ttu-id="58718-253">Surface Pro X를 배포하는 방법은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="58718-253">How can I deploy Surface Pro X?</span></span>

<span data-ttu-id="58718-254">Windows Autopilot을 사용하여 Surface Pro X를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="58718-254">Deploy Surface Pro X using Windows Autopilot.</span></span>

### <span data-ttu-id="58718-255">BMR을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="58718-255">Is a BMR available?</span></span>

<span data-ttu-id="58718-256">예, [Surface 복구 이미지 다운로드](https://support.microsoft.com/surfacerecoveryimage)를 참조하세요..</span><span class="sxs-lookup"><span data-stu-id="58718-256">Yes, refer to [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage).</span></span>

### <span data-ttu-id="58718-257">Surface Pro X를 관리하려면 Intune이 필요합니까?</span><span class="sxs-lookup"><span data-stu-id="58718-257">Is Intune required to manage Surface Pro X?</span></span>

<span data-ttu-id="58718-258">Intune을 사용하는 것이 좋지만 꼭 그래야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="58718-258">Intune is recommended but not required.</span></span> <span data-ttu-id="58718-259">Autopilot에 배포하면 Surface Pro X 디바이스를 Azure AD 또는 Active Directory(하이브리드 Azure AD 가입)에 등록하여 Intune으로 디바이스를 관리하거나 32비트 x86 ConfigMgr 클라이언트를 설치하는 Endpoint Configuration Manager로 공동 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58718-259">Once deployed in Autopilot, you can join Surface Pro X devices to Azure AD or Active Directory (Hybrid Azure AD Join) where you will be able to manage the devices with Intune or co-manage them with Endpoint Configuration Manager, which will install the 32-bit x86 ConfigMgr client.</span></span>
