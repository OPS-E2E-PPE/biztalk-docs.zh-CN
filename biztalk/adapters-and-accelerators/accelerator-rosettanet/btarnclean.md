---
title: BtarnClean |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BtarnClean utility
- assemblies, undeploying
- BTARN, deleting artifacts
- orchestrations, unenlisting
- ports, stopping
- orchestrations, stopping
- ports, deleting
- BTARN, BtarnClean utility
ms.assetid: fbecbb88-9b18-4b4b-a286-0bfa783f2320
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c4524fd5ce633851b64fc07ea2891a389b4ef5
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752853"
---
# <a name="btarnclean"></a><span data-ttu-id="40c19-102">BtarnClean</span><span class="sxs-lookup"><span data-stu-id="40c19-102">BtarnClean</span></span>
<span data-ttu-id="40c19-103">BtarnClean 实用工具用于清除 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]项目关闭计算机。</span><span class="sxs-lookup"><span data-stu-id="40c19-103">You use the BtarnClean utility to clean Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] artifacts off a computer.</span></span> <span data-ttu-id="40c19-104">此过程包括以下操作：</span><span class="sxs-lookup"><span data-stu-id="40c19-104">This includes the following actions:</span></span>  
  
- <span data-ttu-id="40c19-105">停止和取消登记所有[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]业务流程</span><span class="sxs-lookup"><span data-stu-id="40c19-105">Stopping and unenlisting all the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] orchestrations</span></span>  
  
- <span data-ttu-id="40c19-106">停止和删除所有关联的端口</span><span class="sxs-lookup"><span data-stu-id="40c19-106">Stopping and deleting all the associated ports</span></span>  
  
- <span data-ttu-id="40c19-107">取消部署所有 Microsoft。Solutions.BTARN。\*程序集</span><span class="sxs-lookup"><span data-stu-id="40c19-107">Undeploying all the Microsoft .Solutions.BTARN.\* assemblies</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="40c19-108">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="40c19-108">Location in SDK</span></span>  
 <span data-ttu-id="40c19-109">\<*驱动器*\>\Program Files (x86) \ Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK</span><span class="sxs-lookup"><span data-stu-id="40c19-109">\<*drive*\>\Program Files (x86)\ Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  
  
## <a name="running-btarnclean"></a><span data-ttu-id="40c19-110">运行 BtarnClean</span><span class="sxs-lookup"><span data-stu-id="40c19-110">Running BtarnClean</span></span>  
  
#### <a name="to-run-btarnclean"></a><span data-ttu-id="40c19-111">运行 BtarnClean</span><span class="sxs-lookup"><span data-stu-id="40c19-111">To run BtarnClean</span></span>  
  
1.  <span data-ttu-id="40c19-112">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="40c19-112">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="40c19-113">将移动到\<*驱动器*\>\ Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。</span><span class="sxs-lookup"><span data-stu-id="40c19-113">Move to \<*drive*\>\ Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
3.  <span data-ttu-id="40c19-114">在命令提示符处，键入**BtarnClean**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="40c19-114">At the command prompt, type **BtarnClean**, and then press ENTER.</span></span>  
  
     <span data-ttu-id="40c19-115">该实用工具会提示你确认是否要继续。</span><span class="sxs-lookup"><span data-stu-id="40c19-115">The utility prompts you to verify that you want to continue.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40c19-116">备注</span><span class="sxs-lookup"><span data-stu-id="40c19-116">Remarks</span></span>  
 <span data-ttu-id="40c19-117">如果运行 BtarnClean 实用工具的计算机上具有依赖于其他项目的 BizTalk 项目，则 BtarnClean 将指示无法删除该项目。</span><span class="sxs-lookup"><span data-stu-id="40c19-117">If you run the BtarnClean utility on a computer that has a BizTalk artifact that depends on other artifacts, BtarnClean will indicate that it cannot remove the artifact.</span></span> <span data-ttu-id="40c19-118">该实用工具会将该项目留在原处，然后继续删除其他项目。</span><span class="sxs-lookup"><span data-stu-id="40c19-118">The utility will leave that artifact in place and continue to remove other artifacts.</span></span> <span data-ttu-id="40c19-119">你可以先删除依赖项目，然后再次运行该实用工具。</span><span class="sxs-lookup"><span data-stu-id="40c19-119">You can remove dependencies, and then run the utility again.</span></span>  
  
 <span data-ttu-id="40c19-120">如果运行 BtarnClean 实用工具的计算机是多计算机部署的组成部分，则删除这些项目将影响该部署中的其余服务器。</span><span class="sxs-lookup"><span data-stu-id="40c19-120">If you run the BtarnClean utility on a computer that is part of a multi-computer deployment, removing the artifacts will affect the rest of the servers in that deployment.</span></span>  
  
 <span data-ttu-id="40c19-121">在开发人员创建的多个流程存在的情况下运行 BtarnClean 实用工具时，该实用工具将不会删除仍在使用的流程。</span><span class="sxs-lookup"><span data-stu-id="40c19-121">If you run the BtarnClean utility when multiple processes created by developers exist, the utility will not remove processes that are still in use.</span></span>  
  
 <span data-ttu-id="40c19-122">如果用户的项目使用的是主接收位置，则 BtarnClean 实用工具将不会删除该接收位置。</span><span class="sxs-lookup"><span data-stu-id="40c19-122">The BtarnClean utility will not remove a primary receive location if a user's artifact uses that receive location.</span></span> <span data-ttu-id="40c19-123">在这种情况下，你必须删除接收端口。</span><span class="sxs-lookup"><span data-stu-id="40c19-123">If this is the case, you must delete the receive port.</span></span>  
  
 <span data-ttu-id="40c19-124">如果要在运行该实用工具后取消对 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 的配置，请从 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 文件夹运行 Configuration.exe /u。</span><span class="sxs-lookup"><span data-stu-id="40c19-124">If you want to unconfigure [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] after running the utility, run Configuration.exe /u from the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c19-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="40c19-125">See Also</span></span>  
 [<span data-ttu-id="40c19-126">实用工具</span><span class="sxs-lookup"><span data-stu-id="40c19-126">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
