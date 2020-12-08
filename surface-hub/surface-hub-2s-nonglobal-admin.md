---
title: Surface Hub 2S에서 전역이 아닌 관리자 계정 구성
description: 이 문서에서는 Surface Hub 2S를 관리하도록 전역이 아닌 관리자 계정을 구성하는 방법을 설명합니다.
keywords: Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 647a7bf53e5ca8dc52ddec21ec8393cc574ee95a
ms.sourcegitcommit: 16cc2e8d9dfc5d6e061e0b5b6ddfcf35547643f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "11196822"
---
# <span data-ttu-id="6e5bb-104">Surface Hub 2S에서 전역이 아닌 관리자 계정 구성</span><span class="sxs-lookup"><span data-stu-id="6e5bb-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="6e5bb-105">Surface Hub 2S를 Azure AD 도메인에 가입할 때 Surface Hub 2S에서 설정 앱 관리 권한을 제한하는 전역이 아닌 관리자 계정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="6e5bb-106">이렇게 하면 Surface Hub 2S에 대한 관리자 권한의 범위를 지정하고 잠재적으로 원치 않는 관리자가 전체 Azure AD 도메인에 액세스하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access an entire Azure AD domain.</span></span> <span data-ttu-id="6e5bb-107">시작하기 전에 Surface Hub 2S가 Azure AD에 가입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="6e5bb-108">그렇지 않은 경우 Surface Hub 2S를 초기화하고 처음 OOBE(첫 실행) 설치 프로그램을 완료하고 Azure AD에 가입하는 옵션을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <span data-ttu-id="6e5bb-109">요약</span><span class="sxs-lookup"><span data-stu-id="6e5bb-109">Summary</span></span> 

<span data-ttu-id="6e5bb-110">전역이 아닌 관리자 계정을 만드는 프로세스에는 다음 단계가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="6e5bb-111">Microsoft Intune에서 Surface Hub 2S를 관리하기 위해 지정된 관리자가 포함된 보안 그룹을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="6e5bb-112">PowerShell을 사용하여 Azure AD 그룹 SID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="6e5bb-113">Azure AD 그룹 SID를 포함하는 XML 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="6e5bb-114">전역 관리자가 아닌 관리자 보안 그룹에서 관리할 Surface Hub 2S 장치를 포함하는 보안 그룹을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="6e5bb-115">Surface Hub 2S 장치를 포함하는 보안 그룹을 대상으로 하는 사용자 지정 구성 프로필을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <span data-ttu-id="6e5bb-116">Azure AD 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="6e5bb-116">Create Azure AD security groups</span></span>

<span data-ttu-id="6e5bb-117">먼저 관리자 계정을 포함하는 보안 그룹을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="6e5bb-118">그런 다음 Surface Hub 디바이스에 대한 다른 보안 그룹을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-118">Then create another security group for Surface Hub devices.</span></span>  

### <span data-ttu-id="6e5bb-119">관리자 계정에 대한 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="6e5bb-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="6e5bb-120">[Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)관리 센터를 통해 Intune에 로그인하고 그룹 새 그룹 > 그룹 **Groups**  >  **New Group** 유형에서 보안을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6e5bb-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="6e5bb-121">Surface **Hub** 로컬 관리자와 같은 그룹 이름을 입력한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6e5bb-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![허브 관리자용 보안 그룹 만들기](images/sh-create-sec-group.png)

3. <span data-ttu-id="6e5bb-123">그룹을 열고 구성원을 **선택한** **Add members** 다음 구성원 추가를 선택하여 Surface Hub 2S에서 전역 관리자가 아닌 관리자로 지정하고자 하는 관리자 계정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="6e5bb-124">Intune에서 그룹을 만드는 데 대한 자세한 내용은 사용자 및 장치를 구성할 그룹 [추가를 참조합니다.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="6e5bb-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <span data-ttu-id="6e5bb-125">Surface Hub 2S 장치에 대한 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="6e5bb-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="6e5bb-126">이전 절차를 반복하여 허브 장치에 대한 별도의 보안 그룹을 만드시다. 예를 들어 **Surface Hub 디바이스를 예로 들 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6e5bb-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![허브 장치에 대한 보안 그룹 만들기](images/sh-create-sec-group-devices.png) 

## <span data-ttu-id="6e5bb-128">PowerShell을 사용하여 Azure AD 그룹 SID 얻기</span><span class="sxs-lookup"><span data-stu-id="6e5bb-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="6e5bb-129">관리자 권한(관리자**권한으로**실행)으로 PowerShell을 시작하고 시스템이 PowerShell 스크립트를 실행하도록 구성되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="6e5bb-130">자세한 내용은 실행 정책 [정보를 참조합니다.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)</span><span class="sxs-lookup"><span data-stu-id="6e5bb-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="6e5bb-131">[Azure PowerShell 모듈을 설치합니다.](https://docs.microsoft.com/powershell/azure/install-az-ps)</span><span class="sxs-lookup"><span data-stu-id="6e5bb-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="6e5bb-132">Azure AD 테넌트에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="6e5bb-133">테넌트에 로그인하면 다음 commandlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="6e5bb-134">"Azure AD 그룹의 개체 ID를 입력하세요."라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="6e5bb-135">Intune에서 다음 그림과 같이 앞에서 만든 그룹을 선택하고 개체 ID를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![보안 그룹의 개체 ID 복사](images/sh-objectid.png)

6. <span data-ttu-id="6e5bb-137">다음 commandlet을 실행하여 보안 그룹의 SID를 얻게 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="6e5bb-138">PowerShell 명령let에 개체 ID를 붙여넣고 **Enter를**누를 수 있으며 **Azure AD 그룹 SID를** 텍스트 편집기로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <span data-ttu-id="6e5bb-139">Azure AD 그룹 SID를 포함하는 XML 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="6e5bb-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="6e5bb-140">다음을 텍스트 편집기로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="6e5bb-141">자리 보기 SID(S-1-12-1로 시작)를 **Azure AD 그룹 SID로** 바꾸고 파일을 XML로 저장합니다. 예를 들어 \*\*aad-local-admin.xml. \*\*</span><span class="sxs-lookup"><span data-stu-id="6e5bb-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <span data-ttu-id="6e5bb-142">사용자 지정 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="6e5bb-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="6e5bb-143">끝점 관리자에서 **장치**구성  >  **프로필 만들기**  >  **프로필을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6e5bb-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="6e5bb-144">플랫폼에서 **Windows 10 이상을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6e5bb-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="6e5bb-145">프로필에서 **사용자**지정을 선택한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6e5bb-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="6e5bb-146">이름과 설명을 추가하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6e5bb-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="6e5bb-147">구성 **설정**  >  **OMA-URI 설정에서**추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6e5bb-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="6e5bb-148">행 추가 창에서 이름을 추가하고     **OMA-URI 아래에**다음 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="6e5bb-149">데이터 형식에서 **문자열 XML을** 선택하고 이전 단계에서 만든 XML 파일을 열려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![로컬 관리자 xml 구성 파일 업로드](images/sh-local-admin-config.png)

7. <span data-ttu-id="6e5bb-151">**Save**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-151">Click **Save**.</span></span>
8. <span data-ttu-id="6e5bb-152">그룹 **선택을 클릭하여** 앞서 [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) 만든 보안 그룹(Surface Hub 장치)을**포함합니다.**</span><span class="sxs-lookup"><span data-stu-id="6e5bb-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="6e5bb-153">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-153">Click **Next.**</span></span>
9. <span data-ttu-id="6e5bb-154">적용 가능성 규칙에 따라 원하는 경우 규칙을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="6e5bb-155">그렇지 않으면 **다음을** 선택하고 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6e5bb-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="6e5bb-156">OMA-URI 문자열을 사용하는 사용자 지정 구성 프로필에 대한 자세한 내용은 [Intune에서 Windows 10](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)장치에 대한 사용자 지정 설정 사용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <span data-ttu-id="6e5bb-157">Surface Hub 2S를 관리하는 전역이 아닌 관리자</span><span class="sxs-lookup"><span data-stu-id="6e5bb-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="6e5bb-158">**이제 Surface Hub 로컬 관리자** 보안 그룹의 구성원이 Surface Hub 2S의 설정 앱에 로그인하고 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e5bb-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>
