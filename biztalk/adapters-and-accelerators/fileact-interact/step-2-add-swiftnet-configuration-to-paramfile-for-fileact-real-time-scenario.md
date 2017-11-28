---
title: "步骤 2: FileAct 实时方案将 SWIFTNet 配置添加到 Paramfile |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4feec3f-4755-477e-b3d6-1dd6d075255e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 793378e25c3ba92170e1da36b0c8276ab13357ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-real-time-scenario"></a><span data-ttu-id="f6b39-102">步骤 2： 添加 SWIFTNet 配置到 Paramfile FileAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="f6b39-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="f6b39-103">在压降中创建的服务器消息合作伙伴必须指定在 SWIFTNet paramfile 以便接收方可以使用这些值进行初始化。</span><span class="sxs-lookup"><span data-stu-id="f6b39-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
 <span data-ttu-id="f6b39-104">在开始此步骤之前，必须完成[步骤 1： 为 FileAct 实时方案配置 SWIFT 适配器](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="f6b39-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="f6b39-105">若要将 SWIFTNet 配置添加到 paramfile</span><span class="sxs-lookup"><span data-stu-id="f6b39-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="f6b39-106">在诸如记事本之类的文本编辑器中打开 paramfile。</span><span class="sxs-lookup"><span data-stu-id="f6b39-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6b39-107">Paramfile 位于通常： C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="f6b39-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
2.  <span data-ttu-id="f6b39-108">在 paramfile，请突出显示的更改，以指定的服务器消息合作伙伴名称：</span><span class="sxs-lookup"><span data-stu-id="f6b39-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
     <span data-ttu-id="f6b39-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="f6b39-109">username:snlowner</span></span>  
  
     <span data-ttu-id="f6b39-110">subsystem_name:FileactStub</span><span class="sxs-lookup"><span data-stu-id="f6b39-110">subsystem_name:FileactStub</span></span>  
  
     <span data-ttu-id="f6b39-111">\#subsystem_group:fileact</span><span class="sxs-lookup"><span data-stu-id="f6b39-111">\#subsystem_group:fileact</span></span>  
  
     <span data-ttu-id="f6b39-112">\#subsystem_dependency:Support Swarm</span><span class="sxs-lookup"><span data-stu-id="f6b39-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="f6b39-113">subsystem_nature： 严重</span><span class="sxs-lookup"><span data-stu-id="f6b39-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="f6b39-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="f6b39-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="f6b39-115">**spawn"snlreceiver-SagMessagePartner \<fileact RT 的服务器 MessagePartnerName >-AdapterMode fileact"**</span><span class="sxs-lookup"><span data-stu-id="f6b39-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for fileact RT > -AdapterMode fileact"**</span></span>  
  
     <span data-ttu-id="f6b39-116">* 结束</span><span class="sxs-lookup"><span data-stu-id="f6b39-116">*END</span></span>  
  
     <span data-ttu-id="f6b39-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="f6b39-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="f6b39-118">* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="f6b39-118">*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="f6b39-119">* 结束</span><span class="sxs-lookup"><span data-stu-id="f6b39-119">*END</span></span>  
  
     <span data-ttu-id="f6b39-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="f6b39-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="f6b39-121">* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="f6b39-121">*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="f6b39-122">* 结束</span><span class="sxs-lookup"><span data-stu-id="f6b39-122">*END</span></span>  
  
     <span data-ttu-id="f6b39-123">start_event:SNL001:subsystem FileactStub 已启动</span><span class="sxs-lookup"><span data-stu-id="f6b39-123">start_event:SNL001:subsystem FileactStub is up</span></span>  
  
     <span data-ttu-id="f6b39-124">stop_event:SNL002:subsystem FileactStub 已关闭</span><span class="sxs-lookup"><span data-stu-id="f6b39-124">stop_event:SNL002:subsystem FileactStub is down</span></span>  
  
     <span data-ttu-id="f6b39-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="f6b39-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="f6b39-126">\## subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="f6b39-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="f6b39-127">\## subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="f6b39-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="f6b39-128">\#subsystem_nature： 严重</span><span class="sxs-lookup"><span data-stu-id="f6b39-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="f6b39-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="f6b39-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="f6b39-130">\#* 结束</span><span class="sxs-lookup"><span data-stu-id="f6b39-130">\#*END</span></span>  
  
     <span data-ttu-id="f6b39-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="f6b39-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="f6b39-132">\#* 结束</span><span class="sxs-lookup"><span data-stu-id="f6b39-132">\#*END</span></span>  
  
     <span data-ttu-id="f6b39-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="f6b39-133">\#subsystem_status:</span></span>  
  
     #<a name="end"></a><span data-ttu-id="f6b39-134">* 结束</span><span class="sxs-lookup"><span data-stu-id="f6b39-134">*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="f6b39-135">start_event:SNL001:subsystem 用户已启动</span><span class="sxs-lookup"><span data-stu-id="f6b39-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="f6b39-136">stop_event:SNL002:subsystem 用户已关闭</span><span class="sxs-lookup"><span data-stu-id="f6b39-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b39-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6b39-137">See Also</span></span>  
 <span data-ttu-id="f6b39-138">[FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f6b39-138">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="f6b39-139">[步骤 1： 为 FileAct 实时方案配置 SWIFT 适配器](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f6b39-139">[Step 1: Configure the SWIFT Adapter for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="f6b39-140">[步骤 3： 创建发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f6b39-140">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="f6b39-141">步骤 4： 测试 FileAct 实时的端到端方案</span><span class="sxs-lookup"><span data-stu-id="f6b39-141">Step 4: Test FileAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)