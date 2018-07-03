---
title: 步骤 2： 向为 Paramfile 添加 SWIFTNet 配置 InterAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a900a6e-3e08-430a-8766-4a7192adba5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d36758716fb368760e9a93909f70bf4d92c5f840
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992446"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-real-time-scenario"></a><span data-ttu-id="b1cd5-102">步骤 2： 向为 Paramfile 添加 SWIFTNet 配置 InterAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="b1cd5-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="b1cd5-103">在压降中创建的服务器消息合作伙伴必须指定 SWIFTNet paramfile 启用接收方可以使用这些值进行初始化。</span><span class="sxs-lookup"><span data-stu-id="b1cd5-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span> <span data-ttu-id="b1cd5-104">在开始此过程之前，必须完成中的说明[步骤 1： 为交互实时方案配置 SWIFT 适配器](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="b1cd5-104">Before you begin the procedure, you must complete the instructions in [Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="b1cd5-105">若要向 paramfile 添加 SWIFTNet 配置</span><span class="sxs-lookup"><span data-stu-id="b1cd5-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1. <span data-ttu-id="b1cd5-106">在诸如记事本之类的文本编辑器中打开 paramfile。</span><span class="sxs-lookup"><span data-stu-id="b1cd5-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
    <span data-ttu-id="b1cd5-107">Paramfile 是通常位于： C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="b1cd5-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
2. <span data-ttu-id="b1cd5-108">在 paramfile，请突出显示的更改来指定服务器消息合作伙伴名称：</span><span class="sxs-lookup"><span data-stu-id="b1cd5-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
    <span data-ttu-id="b1cd5-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="b1cd5-109">username:snlowner</span></span>  
  
    <span data-ttu-id="b1cd5-110">subsystem_name:InteractStub</span><span class="sxs-lookup"><span data-stu-id="b1cd5-110">subsystem_name:InteractStub</span></span>  
  
    <span data-ttu-id="b1cd5-111">\#subsystem_group:InteractRT</span><span class="sxs-lookup"><span data-stu-id="b1cd5-111">\#subsystem_group:InteractRT</span></span>  
  
    <span data-ttu-id="b1cd5-112">\#subsystem_dependency:Support Swarm</span><span class="sxs-lookup"><span data-stu-id="b1cd5-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
    <span data-ttu-id="b1cd5-113">subsystem_nature： 关键</span><span class="sxs-lookup"><span data-stu-id="b1cd5-113">subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="b1cd5-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="b1cd5-114">subsystem_start:</span></span>  
  
    <span data-ttu-id="b1cd5-115">**生成"snlreceiver-SagMessagePartner \<Interact RT 的 Server MessagePartnerName \> -AdapterMode 交互"**</span><span class="sxs-lookup"><span data-stu-id="b1cd5-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for Interact RT \> -AdapterMode Interact"**</span></span>  
  
    <span data-ttu-id="b1cd5-116">\* 结束</span><span class="sxs-lookup"><span data-stu-id="b1cd5-116">\*END</span></span>  
  
    <span data-ttu-id="b1cd5-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="b1cd5-117">subsystem_stop:</span></span>  
  
    <span data-ttu-id="b1cd5-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="b1cd5-118">\*KILL9:snlreceiver</span></span>  
  
    <span data-ttu-id="b1cd5-119">\* 结束</span><span class="sxs-lookup"><span data-stu-id="b1cd5-119">\*END</span></span>  
  
    <span data-ttu-id="b1cd5-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="b1cd5-120">subsystem_status:</span></span>  
  
    <span data-ttu-id="b1cd5-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="b1cd5-121">\*NB:1:snlreceiver</span></span>  
  
    <span data-ttu-id="b1cd5-122">\* 结束</span><span class="sxs-lookup"><span data-stu-id="b1cd5-122">\*END</span></span>  
  
    <span data-ttu-id="b1cd5-123">start_event:SNL001:subsystem InteractStub 已启动</span><span class="sxs-lookup"><span data-stu-id="b1cd5-123">start_event:SNL001:subsystem InteractStub is up</span></span>  
  
    <span data-ttu-id="b1cd5-124">stop_event:SNL002:subsystem InteractStub 已关闭</span><span class="sxs-lookup"><span data-stu-id="b1cd5-124">stop_event:SNL002:subsystem InteractStub is down</span></span>  
  
    <span data-ttu-id="b1cd5-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="b1cd5-125">\#subsystem_name:User</span></span>  
  
    <span data-ttu-id="b1cd5-126">\## subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="b1cd5-126">\##subsystem_group:user</span></span>  
  
    <span data-ttu-id="b1cd5-127">\## subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="b1cd5-127">\##subsystem_dependency:</span></span>  
  
    <span data-ttu-id="b1cd5-128">\#subsystem_nature： 关键</span><span class="sxs-lookup"><span data-stu-id="b1cd5-128">\#subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="b1cd5-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="b1cd5-129">\#subsystem_start:</span></span>  
  
    <span data-ttu-id="b1cd5-130">\#\* 结束</span><span class="sxs-lookup"><span data-stu-id="b1cd5-130">\#\*END</span></span>  
  
    <span data-ttu-id="b1cd5-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="b1cd5-131">\#subsystem_stop:</span></span>  
  
    <span data-ttu-id="b1cd5-132">\#\* 结束</span><span class="sxs-lookup"><span data-stu-id="b1cd5-132">\#\*END</span></span>  
  
    <span data-ttu-id="b1cd5-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="b1cd5-133">\#subsystem_status:</span></span>  
  
    # <a name="end"></a><span data-ttu-id="b1cd5-134">\* 结束</span><span class="sxs-lookup"><span data-stu-id="b1cd5-134">\*END</span></span>  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="b1cd5-135">start_event:SNL001:subsystem 用户已启动</span><span class="sxs-lookup"><span data-stu-id="b1cd5-135">start_event:SNL001:subsystem User is up</span></span>  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="b1cd5-136">stop_event:SNL002:subsystem 用户已关闭</span><span class="sxs-lookup"><span data-stu-id="b1cd5-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1cd5-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1cd5-137">See Also</span></span>  
 <span data-ttu-id="b1cd5-138">[InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b1cd5-138">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="b1cd5-139">[步骤 1： 配置 SWIFT 适配器为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b1cd5-139">[Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="b1cd5-140">[步骤 3： 创建发送和接收端口的 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b1cd5-140">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="b1cd5-141">步骤 4：测试 InterAct 实时端到端方案</span><span class="sxs-lookup"><span data-stu-id="b1cd5-141">Step 4: Test the InterAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)