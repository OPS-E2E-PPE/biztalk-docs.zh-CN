---
title: 准备使用 Tutorial1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4a792b2-8351-4ae8-9d7c-75420c00af03
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efedfeb184b8b0105b8622b6b3f068faffd6a906
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225205"
---
# <a name="preparing-to-use-the-tutorial"></a><span data-ttu-id="5c28e-102">准备使用本教程</span><span class="sxs-lookup"><span data-stu-id="5c28e-102">Preparing to Use the Tutorial</span></span>
<span data-ttu-id="5c28e-103">你必须执行以下操作之前使用 A4SWIFT 适配器端到端教程。</span><span class="sxs-lookup"><span data-stu-id="5c28e-103">You must do the following before using the A4SWIFT adapter end-to-end tutorial.</span></span>  
  
1.  <span data-ttu-id="5c28e-104">对于本教程，你将需要以下 SWIFT 项目：</span><span class="sxs-lookup"><span data-stu-id="5c28e-104">You will need the following SWIFT artifacts for this tutorial:</span></span>  
  
    -   <span data-ttu-id="5c28e-105">SWIFT 联盟网关 （压降） 6.1</span><span class="sxs-lookup"><span data-stu-id="5c28e-105">SWIFT Alliance Gateway (SAG) 6.1</span></span>  
  
    -   <span data-ttu-id="5c28e-106">远程访问 (RA) 6.1</span><span class="sxs-lookup"><span data-stu-id="5c28e-106">Remote Access (RA) 6.1</span></span>  
  
    -   <span data-ttu-id="5c28e-107">SWIFT WebStation 6.0</span><span class="sxs-lookup"><span data-stu-id="5c28e-107">SWIFT WebStation 6.0</span></span>  
  
    -   <span data-ttu-id="5c28e-108">SWIFTNet 链接 (SNL) 6.1</span><span class="sxs-lookup"><span data-stu-id="5c28e-108">SWIFTNet Link (SNL) 6.1</span></span>  
  
2.  <span data-ttu-id="5c28e-109">你必须配置压降： 压降，在创建 MessagePartners、 终结点和路由规则和测试压降连接，可以在其中安装适配器的计算机。</span><span class="sxs-lookup"><span data-stu-id="5c28e-109">You must configure SAG: create the MessagePartners, End Points, and Routing Rules in SAG, and test SAG connectivity on the computer where you install the adapters.</span></span> <span data-ttu-id="5c28e-110">有关信息，请参阅压降文档。</span><span class="sxs-lookup"><span data-stu-id="5c28e-110">For information, see the SAG documentation.</span></span>  
  
3.  <span data-ttu-id="5c28e-111">按照"如何为创建新主机"Microsoft BizTalk Server 帮助中的主题中列出的说明 ([http://go.microsoft.com/fwlink/?LinkId = 100422](http://go.microsoft.com/fwlink/?LinkId=100422)) 若要创建为交互适配器，一个进程内主机名为*interacthost*，，另一个进程内主机对于 FileAct 适配器，名为*fileacthost*。</span><span class="sxs-lookup"><span data-stu-id="5c28e-111">Follow the instructions listed in the topic “How to Create a New Host” in Microsoft BizTalk Server Help ([http://go.microsoft.com/fwlink/?LinkId=100422](http://go.microsoft.com/fwlink/?LinkId=100422)) to create one in-process Host for the InterAct adapter, named *interacthost*, and one in-process Host for the FileAct adapter, named *fileacthost*.</span></span> <span data-ttu-id="5c28e-112">你将创建为适配器的处理程序时使用这些主机。</span><span class="sxs-lookup"><span data-stu-id="5c28e-112">You will use these hosts while creating handlers for the adapters.</span></span>  
  
4.  <span data-ttu-id="5c28e-113">本教程中创建以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="5c28e-113">Create the following folders for the tutorial:</span></span>  
  
    -   <span data-ttu-id="5c28e-114">c:\SWIFTAdapterTutorial\Fileact\ClientLocation</span><span class="sxs-lookup"><span data-stu-id="5c28e-114">c:\SWIFTAdapterTutorial\Fileact\ClientLocation</span></span>  
  
    -   <span data-ttu-id="5c28e-115">c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime</span><span class="sxs-lookup"><span data-stu-id="5c28e-115">c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime</span></span>  
  
    -   <span data-ttu-id="5c28e-116">c:\SWIFTAdapterTutorial\Fileact\ResponseClient</span><span class="sxs-lookup"><span data-stu-id="5c28e-116">c:\SWIFTAdapterTutorial\Fileact\ResponseClient</span></span>  
  
    -   <span data-ttu-id="5c28e-117">c:\SWIFTAdapterTutorial\Fileact\ResponseServer</span><span class="sxs-lookup"><span data-stu-id="5c28e-117">c:\SWIFTAdapterTutorial\Fileact\ResponseServer</span></span>  
  
    -   <span data-ttu-id="5c28e-118">c:\SWIFTAdapterTutorial\Fileact\ServerLocation</span><span class="sxs-lookup"><span data-stu-id="5c28e-118">c:\SWIFTAdapterTutorial\Fileact\ServerLocation</span></span>  
  
    -   <span data-ttu-id="5c28e-119">c:\SWIFTAdapterTutorial\Fileact\StatusEvents</span><span class="sxs-lookup"><span data-stu-id="5c28e-119">c:\SWIFTAdapterTutorial\Fileact\StatusEvents</span></span>  
  
    -   <span data-ttu-id="5c28e-120">c:\SWIFTAdapterTutorial\Fileact\PullRequest</span><span class="sxs-lookup"><span data-stu-id="5c28e-120">c:\SWIFTAdapterTutorial\Fileact\PullRequest</span></span>  
  
    -   <span data-ttu-id="5c28e-121">c:\SWIFTAdapterTutorial\Fileact\PullResponse</span><span class="sxs-lookup"><span data-stu-id="5c28e-121">c:\SWIFTAdapterTutorial\Fileact\PullResponse</span></span>  
  
    -   <span data-ttu-id="5c28e-122">c:\SWIFTAdapterTutorial\Interact\HandleRequest</span><span class="sxs-lookup"><span data-stu-id="5c28e-122">c:\SWIFTAdapterTutorial\Interact\HandleRequest</span></span>  
  
    -   <span data-ttu-id="5c28e-123">c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime</span><span class="sxs-lookup"><span data-stu-id="5c28e-123">c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime</span></span>  
  
    -   <span data-ttu-id="5c28e-124">c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span><span class="sxs-lookup"><span data-stu-id="5c28e-124">c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span></span>  
  
    -   <span data-ttu-id="5c28e-125">c:\SWIFTAdapterTutorial\Interact\Response</span><span class="sxs-lookup"><span data-stu-id="5c28e-125">c:\SWIFTAdapterTutorial\Interact\Response</span></span>  
  
    -   <span data-ttu-id="5c28e-126">c:\SWIFTAdapterTutorial\Interact\PullRequest</span><span class="sxs-lookup"><span data-stu-id="5c28e-126">c:\SWIFTAdapterTutorial\Interact\PullRequest</span></span>  
  
    -   <span data-ttu-id="5c28e-127">c:\SWIFTAdapterTutorial\Interact\Pullresponse</span><span class="sxs-lookup"><span data-stu-id="5c28e-127">c:\SWIFTAdapterTutorial\Interact\Pullresponse</span></span>  
  
5.  <span data-ttu-id="5c28e-128">你必须连接到 SWIFT ITB 或实时的环境以进行测试适配器。</span><span class="sxs-lookup"><span data-stu-id="5c28e-128">You must have a connection to SWIFT ITB or live environment to test the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c28e-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c28e-129">See Also</span></span>  
 <span data-ttu-id="5c28e-130">[BizTalk FileAct 和交互适配器端到端教程](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="5c28e-130">[BizTalk FileAct and InterAct Adapters End-to-End Tutorial](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md) </span></span>  
 <span data-ttu-id="5c28e-131">[交互实时方案](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5c28e-131">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="5c28e-132">[交互存储和转发 （推送） 方案](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5c28e-132">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="5c28e-133">[FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5c28e-133">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="5c28e-134">FileAct 存储和转发方案</span><span class="sxs-lookup"><span data-stu-id="5c28e-134">FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)