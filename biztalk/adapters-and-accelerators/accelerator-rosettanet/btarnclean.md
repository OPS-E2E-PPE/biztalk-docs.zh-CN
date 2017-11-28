---
title: "BtarnClean |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26397001014dd1e4d6ad7139e040892c71e22754
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="btarnclean"></a><span data-ttu-id="a9745-102">BtarnClean</span><span class="sxs-lookup"><span data-stu-id="a9745-102">BtarnClean</span></span>
<span data-ttu-id="a9745-103">BtarnClean 实用程序用于清理[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]项目关闭计算机。</span><span class="sxs-lookup"><span data-stu-id="a9745-103">You use the BtarnClean utility to clean [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] artifacts off a computer.</span></span> <span data-ttu-id="a9745-104">此过程包括以下操作：</span><span class="sxs-lookup"><span data-stu-id="a9745-104">This includes the following actions:</span></span>  
  
-   <span data-ttu-id="a9745-105">停止并取消所有登记[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]业务流程</span><span class="sxs-lookup"><span data-stu-id="a9745-105">Stopping and unenlisting all the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] orchestrations</span></span>  
  
-   <span data-ttu-id="a9745-106">停止和删除所有关联的端口</span><span class="sxs-lookup"><span data-stu-id="a9745-106">Stopping and deleting all the associated ports</span></span>  
  
-   <span data-ttu-id="a9745-107">取消所有部署[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]。Solutions.BTARN.* 程序集</span><span class="sxs-lookup"><span data-stu-id="a9745-107">Undeploying all the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.BTARN.* assemblies</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="a9745-108">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="a9745-108">Location in SDK</span></span>  
 <span data-ttu-id="a9745-109">\<*驱动器*> files\ Microsoft BizTalk\<版本 > RosettaNet\SDK 快捷键</span><span class="sxs-lookup"><span data-stu-id="a9745-109">\<*drive*>\Program Files\ Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK</span></span>  
  
## <a name="running-btarnclean"></a><span data-ttu-id="a9745-110">运行 BtarnClean</span><span class="sxs-lookup"><span data-stu-id="a9745-110">Running BtarnClean</span></span>  
  
#### <a name="to-run-btarnclean"></a><span data-ttu-id="a9745-111">运行 BtarnClean</span><span class="sxs-lookup"><span data-stu-id="a9745-111">To run BtarnClean</span></span>  
  
1.  <span data-ttu-id="a9745-112">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="a9745-112">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="a9745-113">将移动到\<*驱动器*> \ 程序 Files\Microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK\\。</span><span class="sxs-lookup"><span data-stu-id="a9745-113">Move to \<*drive*>\ Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\\.</span></span>  
  
3.  <span data-ttu-id="a9745-114">在命令提示符处，键入**BtarnClean**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="a9745-114">At the command prompt, type **BtarnClean**, and then press ENTER.</span></span>  
  
     <span data-ttu-id="a9745-115">该实用工具会提示你确认是否要继续。</span><span class="sxs-lookup"><span data-stu-id="a9745-115">The utility prompts you to verify that you want to continue.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9745-116">注释</span><span class="sxs-lookup"><span data-stu-id="a9745-116">Remarks</span></span>  
 <span data-ttu-id="a9745-117">如果运行 BtarnClean 实用工具的计算机上具有依赖于其他项目的 BizTalk 项目，则 BtarnClean 将指示无法删除该项目。</span><span class="sxs-lookup"><span data-stu-id="a9745-117">If you run the BtarnClean utility on a computer that has a BizTalk artifact that depends on other artifacts, BtarnClean will indicate that it cannot remove the artifact.</span></span> <span data-ttu-id="a9745-118">该实用工具会将该项目留在原处，然后继续删除其他项目。</span><span class="sxs-lookup"><span data-stu-id="a9745-118">The utility will leave that artifact in place and continue to remove other artifacts.</span></span> <span data-ttu-id="a9745-119">你可以先删除依赖项目，然后再次运行该实用工具。</span><span class="sxs-lookup"><span data-stu-id="a9745-119">You can remove dependencies, and then run the utility again.</span></span>  
  
 <span data-ttu-id="a9745-120">如果运行 BtarnClean 实用工具的计算机是多计算机部署的组成部分，则删除这些项目将影响该部署中的其余服务器。</span><span class="sxs-lookup"><span data-stu-id="a9745-120">If you run the BtarnClean utility on a computer that is part of a multi-computer deployment, removing the artifacts will affect the rest of the servers in that deployment.</span></span>  
  
 <span data-ttu-id="a9745-121">在开发人员创建的多个流程存在的情况下运行 BtarnClean 实用工具时，该实用工具将不会删除仍在使用的流程。</span><span class="sxs-lookup"><span data-stu-id="a9745-121">If you run the BtarnClean utility when multiple processes created by developers exist, the utility will not remove processes that are still in use.</span></span>  
  
 <span data-ttu-id="a9745-122">如果用户的项目使用的是主接收位置，则 BtarnClean 实用工具将不会删除该接收位置。</span><span class="sxs-lookup"><span data-stu-id="a9745-122">The BtarnClean utility will not remove a primary receive location if a user's artifact uses that receive location.</span></span> <span data-ttu-id="a9745-123">在这种情况下，你必须删除接收端口。</span><span class="sxs-lookup"><span data-stu-id="a9745-123">If this is the case, you must delete the receive port.</span></span>  
  
 <span data-ttu-id="a9745-124">如果要在运行该实用工具后取消对 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 的配置，请从 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 文件夹运行 Configuration.exe /u。</span><span class="sxs-lookup"><span data-stu-id="a9745-124">If you want to unconfigure [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] after running the utility, run Configuration.exe /u from the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9745-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9745-125">See Also</span></span>  
 [<span data-ttu-id="a9745-126">实用程序</span><span class="sxs-lookup"><span data-stu-id="a9745-126">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)