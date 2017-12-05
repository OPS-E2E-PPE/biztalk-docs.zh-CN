---
title: "步骤 2： 交互应用商店应用和向前情况下将 SWIFTNet 配置添加到 Paramfile |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a18a43c-1dd9-4113-bf32-8bc7bf9338b0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05524abd4cd57b8d804ab5995072905392fd3645
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="411fa-102">步骤 2： 添加 SWIFTNet 配置到 Paramfile 交互应用商店应用和转发方案</span><span class="sxs-lookup"><span data-stu-id="411fa-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="411fa-103">在压降中创建的服务器消息合作伙伴必须指定在 SWIFTNet paramfile 以便接收方可以使用这些值进行初始化。</span><span class="sxs-lookup"><span data-stu-id="411fa-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
 <span data-ttu-id="411fa-104">在开始此步骤之前，必须完成[步骤 1： 配置 SWIFT 适配器，使交互应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="411fa-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="411fa-105">若要将 SWIFTNet 配置添加到 paramfile</span><span class="sxs-lookup"><span data-stu-id="411fa-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="411fa-106">在诸如记事本之类的文本编辑器中打开 paramfile。</span><span class="sxs-lookup"><span data-stu-id="411fa-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="411fa-107">Paramfile 位于通常： C:\SWIFTAlliance\RA\Ra1\cfg\paramfile。</span><span class="sxs-lookup"><span data-stu-id="411fa-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile.</span></span>  
  
2.  <span data-ttu-id="411fa-108">在 paramfile，请突出显示的更改，以指定的服务器消息合作伙伴名称：</span><span class="sxs-lookup"><span data-stu-id="411fa-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
     <span data-ttu-id="411fa-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="411fa-109">username:snlowner</span></span>  
  
     <span data-ttu-id="411fa-110">subsystem_name:InteractStub</span><span class="sxs-lookup"><span data-stu-id="411fa-110">subsystem_name:InteractStub</span></span>  
  
     <span data-ttu-id="411fa-111">\#subsystem_group:Interactsnf</span><span class="sxs-lookup"><span data-stu-id="411fa-111">\#subsystem_group:Interactsnf</span></span>  
  
     <span data-ttu-id="411fa-112">\#subsystem_dependency:Support Swarm</span><span class="sxs-lookup"><span data-stu-id="411fa-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="411fa-113">subsystem_nature： 严重</span><span class="sxs-lookup"><span data-stu-id="411fa-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="411fa-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="411fa-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="411fa-115">**spawn"snlreceiver-SagMessagePartner\<交互 SnF 的服务器 MessagePartnerName\> -AdapterMode 交互"**</span><span class="sxs-lookup"><span data-stu-id="411fa-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for Interact SnF\> -AdapterMode Interact"**</span></span>  
  
     <span data-ttu-id="411fa-116">* 结束</span><span class="sxs-lookup"><span data-stu-id="411fa-116">*END</span></span>  
  
     <span data-ttu-id="411fa-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="411fa-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="411fa-118">* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="411fa-118">*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="411fa-119">* 结束</span><span class="sxs-lookup"><span data-stu-id="411fa-119">*END</span></span>  
  
     <span data-ttu-id="411fa-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="411fa-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="411fa-121">* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="411fa-121">*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="411fa-122">* 结束</span><span class="sxs-lookup"><span data-stu-id="411fa-122">*END</span></span>  
  
     <span data-ttu-id="411fa-123">start_event:SNL001:subsystem InteractStubSnF 已启动</span><span class="sxs-lookup"><span data-stu-id="411fa-123">start_event:SNL001:subsystem InteractStubSnF is up</span></span>  
  
     <span data-ttu-id="411fa-124">stop_event:SNL002:subsystem InteractStubSnF 已关闭</span><span class="sxs-lookup"><span data-stu-id="411fa-124">stop_event:SNL002:subsystem InteractStubSnF is down</span></span>  
  
     <span data-ttu-id="411fa-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="411fa-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="411fa-126">\## subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="411fa-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="411fa-127">\## subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="411fa-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="411fa-128">\#subsystem_nature： 严重</span><span class="sxs-lookup"><span data-stu-id="411fa-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="411fa-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="411fa-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="411fa-130">\#* 结束</span><span class="sxs-lookup"><span data-stu-id="411fa-130">\#*END</span></span>  
  
     <span data-ttu-id="411fa-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="411fa-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="411fa-132">\#* 结束</span><span class="sxs-lookup"><span data-stu-id="411fa-132">\#*END</span></span>  
  
     <span data-ttu-id="411fa-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="411fa-133">\#subsystem_status:</span></span>  
  
     <span data-ttu-id="411fa-134">\#* 结束</span><span class="sxs-lookup"><span data-stu-id="411fa-134">\#*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="411fa-135">start_event:SNL001:subsystem 用户已启动</span><span class="sxs-lookup"><span data-stu-id="411fa-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="411fa-136">stop_event:SNL002:subsystem 用户已关闭</span><span class="sxs-lookup"><span data-stu-id="411fa-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411fa-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="411fa-137">See Also</span></span>  
 <span data-ttu-id="411fa-138">[交互存储和转发 （推送） 方案](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="411fa-138">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="411fa-139">[步骤 1： 配置 SWIFT 适配器交互应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="411fa-139">[Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="411fa-140">[步骤 3： 创建发送端口和交互应用商店应用和向前情况下接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="411fa-140">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="411fa-141">步骤 4：测试 InterAct 存储和转发端到端方案</span><span class="sxs-lookup"><span data-stu-id="411fa-141">Step 4: Test the InterAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)