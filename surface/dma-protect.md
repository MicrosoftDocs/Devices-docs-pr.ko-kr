---
title: Surface DMA 보호
description: 이 문서에서는 호환되는 Surface 디바이스의 DMA 보호에 대해 설명
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/14/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.openlocfilehash: af5187a2b110804a2dff82291f1d5f912ac61a7b
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270623"
---
# <span data-ttu-id="a4cf6-103">Surface 디바이스의 DMA 보호</span><span class="sxs-lookup"><span data-stu-id="a4cf6-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="a4cf6-104">DMA(직접 메모리 액세스) 보호는 이동식 SSD 또는 외부 저장 장치 사용과 관련된 잠재적인 보안 취약성을 완화하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="a4cf6-105">새로운 Surface 디바이스는 기본적으로 DMA 보호를 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="a4cf6-106">여기에는 Surface Pro 7+가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-106">These include Surface Pro 7+.</span></span> <span data-ttu-id="a4cf6-107">Surface Pro 7, Surface Laptop 3 및 Surface Pro X.  장치에서 DMA 보호 기능이 존재할지 확인하려면 아래\*\*\*\* 그림과 같이 시스템  >  \*\* 정보(시작 \*\*msinfo32.exe)를 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-107">Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![DMA 보호를 사용하도록 설정한 경우를 보여주는 시스템 정보](images/systeminfodma.png)

<span data-ttu-id="a4cf6-109">Surface 이동식 SSD가 변조된 경우 장치가 전원을 끄게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-109">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="a4cf6-110">그러면 UEFI가 메모리를 지우고 잔류 데이터를 지우게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cf6-110">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>
