---
title: 准备使用 Tutorial1 |Microsoft Docs
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
ms.openlocfilehash: 8bc4614d82471f6573134c6da47966bf8ca57330
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366576"
---
# <a name="preparing-to-use-the-tutorial"></a><span data-ttu-id="8067f-102">为使用教程做准备</span><span class="sxs-lookup"><span data-stu-id="8067f-102">Preparing to Use the Tutorial</span></span>
<span data-ttu-id="8067f-103">必须执行以下操作之前使用 A4SWIFT 适配器端到端教程。</span><span class="sxs-lookup"><span data-stu-id="8067f-103">You must do the following before using the A4SWIFT adapter end-to-end tutorial.</span></span>  
  
1.  <span data-ttu-id="8067f-104">本教程中，您将需要以下 SWIFT 项目：</span><span class="sxs-lookup"><span data-stu-id="8067f-104">You will need the following SWIFT artifacts for this tutorial:</span></span>  
  
    -   <span data-ttu-id="8067f-105">SWIFT 联盟网关 （压降） 6.1</span><span class="sxs-lookup"><span data-stu-id="8067f-105">SWIFT Alliance Gateway (SAG) 6.1</span></span>  
  
    -   <span data-ttu-id="8067f-106">远程访问 (RA) 6.1</span><span class="sxs-lookup"><span data-stu-id="8067f-106">Remote Access (RA) 6.1</span></span>  
  
    -   <span data-ttu-id="8067f-107">SWIFT WebStation 6.0</span><span class="sxs-lookup"><span data-stu-id="8067f-107">SWIFT WebStation 6.0</span></span>  
  
    -   <span data-ttu-id="8067f-108">SWIFTNet 链接 (SNL) 6.1</span><span class="sxs-lookup"><span data-stu-id="8067f-108">SWIFTNet Link (SNL) 6.1</span></span>  
  
2.  <span data-ttu-id="8067f-109">必须配置压降： 压降，在创建 MessagePartners、 终结点和路由规则和测试压降连接，可以在其中安装适配器的计算机。</span><span class="sxs-lookup"><span data-stu-id="8067f-109">You must configure SAG: create the MessagePartners, End Points, and Routing Rules in SAG, and test SAG connectivity on the computer where you install the adapters.</span></span> <span data-ttu-id="8067f-110">有关信息，请参阅压降文档。</span><span class="sxs-lookup"><span data-stu-id="8067f-110">For information, see the SAG documentation.</span></span>  
  
3.  <span data-ttu-id="8067f-111">按照"如何为创建新主机"Microsoft BizTalk Server 帮助中的主题中列出的说明 ([http://go.microsoft.com/fwlink/?LinkId=100422](http://go.microsoft.com/fwlink/?LinkId=100422)) 创建 InterAct 适配器的一个进程内主机名为*interacthost*，另一个进程内主机的名为的 FileAct 适配器*fileacthost*。</span><span class="sxs-lookup"><span data-stu-id="8067f-111">Follow the instructions listed in the topic “How to Create a New Host” in Microsoft BizTalk Server Help ([http://go.microsoft.com/fwlink/?LinkId=100422](http://go.microsoft.com/fwlink/?LinkId=100422)) to create one in-process Host for the InterAct adapter, named *interacthost*, and one in-process Host for the FileAct adapter, named *fileacthost*.</span></span> <span data-ttu-id="8067f-112">创建适配器处理程序时，将使用这些主机。</span><span class="sxs-lookup"><span data-stu-id="8067f-112">You will use these hosts while creating handlers for the adapters.</span></span>  
  
4.  <span data-ttu-id="8067f-113">本教程中创建以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="8067f-113">Create the following folders for the tutorial:</span></span>  
  
    -   <span data-ttu-id="8067f-114">c:\SWIFTAdapterTutorial\Fileact\ClientLocation</span><span class="sxs-lookup"><span data-stu-id="8067f-114">c:\SWIFTAdapterTutorial\Fileact\ClientLocation</span></span>  
  
    -   <span data-ttu-id="8067f-115">c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime</span><span class="sxs-lookup"><span data-stu-id="8067f-115">c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime</span></span>  
  
    -   <span data-ttu-id="8067f-116">c:\SWIFTAdapterTutorial\Fileact\ResponseClient</span><span class="sxs-lookup"><span data-stu-id="8067f-116">c:\SWIFTAdapterTutorial\Fileact\ResponseClient</span></span>  
  
    -   <span data-ttu-id="8067f-117">c:\SWIFTAdapterTutorial\Fileact\ResponseServer</span><span class="sxs-lookup"><span data-stu-id="8067f-117">c:\SWIFTAdapterTutorial\Fileact\ResponseServer</span></span>  
  
    -   <span data-ttu-id="8067f-118">c:\SWIFTAdapterTutorial\Fileact\ServerLocation</span><span class="sxs-lookup"><span data-stu-id="8067f-118">c:\SWIFTAdapterTutorial\Fileact\ServerLocation</span></span>  
  
    -   <span data-ttu-id="8067f-119">c:\SWIFTAdapterTutorial\Fileact\StatusEvents</span><span class="sxs-lookup"><span data-stu-id="8067f-119">c:\SWIFTAdapterTutorial\Fileact\StatusEvents</span></span>  
  
    -   <span data-ttu-id="8067f-120">c:\SWIFTAdapterTutorial\Fileact\PullRequest</span><span class="sxs-lookup"><span data-stu-id="8067f-120">c:\SWIFTAdapterTutorial\Fileact\PullRequest</span></span>  
  
    -   <span data-ttu-id="8067f-121">c:\SWIFTAdapterTutorial\Fileact\PullResponse</span><span class="sxs-lookup"><span data-stu-id="8067f-121">c:\SWIFTAdapterTutorial\Fileact\PullResponse</span></span>  
  
    -   <span data-ttu-id="8067f-122">c:\SWIFTAdapterTutorial\Interact\HandleRequest</span><span class="sxs-lookup"><span data-stu-id="8067f-122">c:\SWIFTAdapterTutorial\Interact\HandleRequest</span></span>  
  
    -   <span data-ttu-id="8067f-123">c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime</span><span class="sxs-lookup"><span data-stu-id="8067f-123">c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime</span></span>  
  
    -   <span data-ttu-id="8067f-124">c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span><span class="sxs-lookup"><span data-stu-id="8067f-124">c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span></span>  
  
    -   <span data-ttu-id="8067f-125">c:\SWIFTAdapterTutorial\Interact\Response</span><span class="sxs-lookup"><span data-stu-id="8067f-125">c:\SWIFTAdapterTutorial\Interact\Response</span></span>  
  
    -   <span data-ttu-id="8067f-126">c:\SWIFTAdapterTutorial\Interact\PullRequest</span><span class="sxs-lookup"><span data-stu-id="8067f-126">c:\SWIFTAdapterTutorial\Interact\PullRequest</span></span>  
  
    -   <span data-ttu-id="8067f-127">c:\SWIFTAdapterTutorial\Interact\Pullresponse</span><span class="sxs-lookup"><span data-stu-id="8067f-127">c:\SWIFTAdapterTutorial\Interact\Pullresponse</span></span>  
  
5.  <span data-ttu-id="8067f-128">您必须具有连接到 SWIFT ITB 或实时环境来测试适配器。</span><span class="sxs-lookup"><span data-stu-id="8067f-128">You must have a connection to SWIFT ITB or live environment to test the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8067f-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="8067f-129">See Also</span></span>  
 <span data-ttu-id="8067f-130">[BizTalk FileAct 和交互适配器端到端教程](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="8067f-130">[BizTalk FileAct and InterAct Adapters End-to-End Tutorial](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md) </span></span>  
 <span data-ttu-id="8067f-131">[InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="8067f-131">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="8067f-132">[InterAct 存储和转发 （推送） 方案](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="8067f-132">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="8067f-133">[FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="8067f-133">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="8067f-134">FileAct 存储和转发方案</span><span class="sxs-lookup"><span data-stu-id="8067f-134">FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)