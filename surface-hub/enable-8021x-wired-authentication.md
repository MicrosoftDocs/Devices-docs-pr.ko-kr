---
title: 802.1x 유선 인증 사용
description: Surface Hub 디바이스에 802.1x 유선 인증 MDM 정책이 활성화되었습니다.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836252"
---
# <span data-ttu-id="f9ef9-103">802.1 x 유선 인증 사용</span><span class="sxs-lookup"><span data-stu-id="f9ef9-103">Enable 802.1x wired authentication</span></span>

<span data-ttu-id="f9ef9-104">[Windows 10 2017년 11월 14일 업데이트](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954)(빌드 15063.726)는 Surface Hub 디바이스에서 802.1x 유선 인증 MDM 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-104">The [November 14, 2017 update to Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (build 15063.726) enables 802.1x wired authentication MDM policies on Surface Hub devices.</span></span> <span data-ttu-id="f9ef9-105">이 기능은 조직이 [IEEE 802.1x 인증 프로토콜](http://www.ieee802.org/1/pages/802.1x-2010.html)을 사용해 표준화된 유선 네트워크 인증을 적용할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-105">The feature allows organizations to enforce standardized wired network authentication using the [IEEE 802.1x authentication protocol](http://www.ieee802.org/1/pages/802.1x-2010.html).</span></span> <span data-ttu-id="f9ef9-106">이미 MDM을 통해 WLAN 프로필을 사용하는 무선 인증에 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-106">This is already available for wireless authentication using WLAN profiles via MDM.</span></span> <span data-ttu-id="f9ef9-107">이 항목에서는 Surface Hub를 유선 인증에서 사용하도록 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-107">This topic explains how to  configure a Surface Hub for use with wired authentication.</span></span> 

<span data-ttu-id="f9ef9-108">Surface Hub에서 802.1x 유선 인증 적용 및 구현은 MDM [OMA-URI 정의](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings)를 통해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-108">Enforcement and enablement of 802.1x wired authentication on Surface Hub can be done through MDM [OMA-URI definition](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings).</span></span> 

<span data-ttu-id="f9ef9-109">설정할 기본 구성은 **LanProfile** 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-109">The primary configuration to set is the **LanProfile** policy.</span></span> <span data-ttu-id="f9ef9-110">선택한 인증 방법에 따라 사용자 또는 컴퓨터 인증서(예: 사용자/디바이스 인증서의 경우 [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) 또는 디바이스 인증서의 경우 [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp))를 추가하기 위해 **EapUserData** 정책이나 MDM 정책 등 다른 정책이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-110">Depending on the authentication method selected, other policies may be required, either the **EapUserData** policy or through MDM policies for adding user or machine certificates (such as [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) for user/device certificates or [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) for device certificates).</span></span> 

## <span data-ttu-id="f9ef9-111">LanProfile 정책 요소</span><span class="sxs-lookup"><span data-stu-id="f9ef9-111">LanProfile policy element</span></span>

<span data-ttu-id="f9ef9-112">지원되는 802.1x 인증 방법 중 하나를 사용하여 Surface Hub를 구성하려면 다음 OMA URI를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-112">To configure Surface Hub to use one of the supported 802.1x authentication methods, utilize the following OMA-URI.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

<span data-ttu-id="f9ef9-113">이 OMA URI 노드는 XML의 텍스트 문자열을 매개 변수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-113">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="f9ef9-114">매개 변수로 제공되는 XML은 [802.1X 스키마](https://msdn.microsoft.com/library/cc233003.aspx)의 요소를 포함하여 [유선 LAN 프로필 스키마](https://msdn.microsoft.com/library/cc233002.aspx)를 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-114">The XML provided as a parameter should conform to the [Wired LAN Profile Schema](https://msdn.microsoft.com/library/cc233002.aspx) including elements from the [802.1X schema](https://msdn.microsoft.com/library/cc233003.aspx).</span></span> 

<span data-ttu-id="f9ef9-115">대부분의 경우, 관리자 또는 사용자가 다음 NETSH 명령을 사용하여 이미 802.1X용 네트워크에서 구성된 기존 PC로부터 LanProfile XML을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-115">In most instances, an administrator or user can export the LanProfile XML from an existing PC that is already configured on the network for 802.1X using this following NETSH command.</span></span> 

```
netsh lan export profile folder=.
```

<span data-ttu-id="f9ef9-116">이 명령을 사용하면 다음 출력이 반환되고 현재 디렉터리에 **Ethernet.xml**이라는 파일이 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-116">Running this command will give the following output and place a file titled **Ethernet.xml** in the current directory.</span></span> 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <span data-ttu-id="f9ef9-117">EapUserData 정책 요소</span><span class="sxs-lookup"><span data-stu-id="f9ef9-117">EapUserData policy element</span></span>

<span data-ttu-id="f9ef9-118">선택한 인증 방법이 인증서가 아니라 사용자 이름 및 암호를 요구하는 경우 **EapUserData** 요소를 사용하여 네트워크를 인증하는 데 사용할 디바이스에 대한 자격 증명을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-118">If your selected authentication method requires a username and password as opposed to a certificate, you can use the **EapUserData** element to specify credentials for the device to use to authenticate to the network.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

<span data-ttu-id="f9ef9-119">이 OMA URI 노드는 XML의 텍스트 문자열을 매개 변수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-119">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="f9ef9-120">매개 변수로 제공된 XML은 [PEAP MS-CHAPv2 사용자 속성 예시](https://msdn.microsoft.com/library/windows/desktop/bb891979)를 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-120">The XML provided as a parameter should conform to the [PEAP MS-CHAPv2 User Properties example](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span></span> <span data-ttu-id="f9ef9-121">예시에서 모든 *test* 및 *ias-domain*을 사용자의 정보로 교체해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-121">In the example, you will need to replace all instances of *test* and *ias-domain* with your information.</span></span>



## <span data-ttu-id="f9ef9-122">인증서 추가</span><span class="sxs-lookup"><span data-stu-id="f9ef9-122">Adding certificates</span></span>

<span data-ttu-id="f9ef9-123">선택한 인증 방법이 인증서 기반 인 경우에는 [프로비저닝 패키지를 만들거나](provisioning-packages-for-surface-hub.md), [MDM을 활용](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)하거나, 설정 (**설정**  >  **업데이트 및 보안**  >  **인증서**)에서 인증서를 가져와 적절 한 인증서 저장소의 Surface Hub 장치에 해당 인증서를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ef9-123">If your selected authentication method is certificate-based, you will need to [create a provisioning package](provisioning-packages-for-surface-hub.md), [utilize MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp), or import a certificate from settings (**Settings** > **Update and Security** > **Certificates**) to deploy those certificates to your Surface Hub device in the appropriate Certificate Store.</span></span> <span data-ttu-id="f9ef9-124">인증서를 추가할 때 각 PFX가 인증서를 하나만 포함해야 합니다(PFX는 여러 인증서를 포함할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="f9ef9-124">When adding certificates, each PFX must contain only one certificate (a PFX cannot have multiple certificates).</span></span>

