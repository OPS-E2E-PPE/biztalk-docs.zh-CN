---
title: 步骤 2： 将 SWIFTNet 配置添加到 FileAct 应用商店应用和向前方案 Paramfile |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 088ab41f-8325-4330-b6f2-0164aa1911b1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394e570ad9bd1c0e7532923dac9c2cc702f2f567
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966411"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="9b0f9-102">步骤 2： 将 SWIFTNet 配置添加到 Paramfile FileAct 应用商店应用和转发方案</span><span class="sxs-lookup"><span data-stu-id="9b0f9-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="9b0f9-103">在压降中创建的服务器消息合作伙伴必须指定在 SWIFTNet paramfile 以便接收方可以使用这些值进行初始化。</span><span class="sxs-lookup"><span data-stu-id="9b0f9-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
<span data-ttu-id="9b0f9-104">完成[步骤 1： 配置 FileAct 应用商店应用和转发方案 SWIFT 适配器](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)在开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="9b0f9-104">Complete [Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) before you begin this step.</span></span>
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="9b0f9-105">将 SWIFTNet 配置添加到 paramfile</span><span class="sxs-lookup"><span data-stu-id="9b0f9-105">Add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="9b0f9-106">在诸如记事本之类的文本编辑器中打开 paramfile。</span><span class="sxs-lookup"><span data-stu-id="9b0f9-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="9b0f9-107">Paramfile 位于通常： C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="9b0f9-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
3.  <span data-ttu-id="9b0f9-108">在 paramfile，请突出显示的更改，以指定的服务器消息合作伙伴名称：</span><span class="sxs-lookup"><span data-stu-id="9b0f9-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
    
     <span data-ttu-id="9b0f9-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="9b0f9-109">username:snlowner</span></span>  
  
     <span data-ttu-id="9b0f9-110">subsystem_name:FileactStub</span><span class="sxs-lookup"><span data-stu-id="9b0f9-110">subsystem_name:FileactStub</span></span>  
  
     <span data-ttu-id="9b0f9-111">\#subsystem_group:fileactsnf</span><span class="sxs-lookup"><span data-stu-id="9b0f9-111">\#subsystem_group:fileactsnf</span></span>  
  
     <span data-ttu-id="9b0f9-112">\#subsystem_dependency:Support Swarm</span><span class="sxs-lookup"><span data-stu-id="9b0f9-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="9b0f9-113">subsystem_nature： 严重</span><span class="sxs-lookup"><span data-stu-id="9b0f9-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="9b0f9-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="9b0f9-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="9b0f9-115">**spawn"snlreceiver-SagMessagePartner \<fileact SnF 的服务器 MessagePartnerName\> -AdapterMode fileact"**</span><span class="sxs-lookup"><span data-stu-id="9b0f9-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for fileact SnF\> -AdapterMode fileact"**</span></span>  
  
     <span data-ttu-id="9b0f9-116">\* 结束</span><span class="sxs-lookup"><span data-stu-id="9b0f9-116">\*END</span></span>  
  
     <span data-ttu-id="9b0f9-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="9b0f9-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="9b0f9-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="9b0f9-118">\*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="9b0f9-119">\* 结束</span><span class="sxs-lookup"><span data-stu-id="9b0f9-119">\*END</span></span>  
  
     <span data-ttu-id="9b0f9-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="9b0f9-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="9b0f9-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="9b0f9-121">\*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="9b0f9-122">\* 结束</span><span class="sxs-lookup"><span data-stu-id="9b0f9-122">\*END</span></span>  
  
     <span data-ttu-id="9b0f9-123">start_event:SNL001:subsystem FileactStubSnF 已启动</span><span class="sxs-lookup"><span data-stu-id="9b0f9-123">start_event:SNL001:subsystem FileactStubSnF is up</span></span>  
  
     <span data-ttu-id="9b0f9-124">stop_event:SNL002:subsystem FileactStubSnF 已关闭</span><span class="sxs-lookup"><span data-stu-id="9b0f9-124">stop_event:SNL002:subsystem FileactStubSnF is down</span></span>  
  
     <span data-ttu-id="9b0f9-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="9b0f9-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="9b0f9-126">\## subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="9b0f9-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="9b0f9-127">\## subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="9b0f9-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="9b0f9-128">\#subsystem_nature： 严重</span><span class="sxs-lookup"><span data-stu-id="9b0f9-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="9b0f9-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="9b0f9-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="9b0f9-130">\#\* 结束</span><span class="sxs-lookup"><span data-stu-id="9b0f9-130">\#\*END</span></span>  
  
     <span data-ttu-id="9b0f9-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="9b0f9-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="9b0f9-132">\#\* 结束</span><span class="sxs-lookup"><span data-stu-id="9b0f9-132">\#\*END</span></span>  
  
     <span data-ttu-id="9b0f9-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="9b0f9-133">\#subsystem_status:</span></span>  
  
     <span data-ttu-id="9b0f9-134">\#\* 结束</span><span class="sxs-lookup"><span data-stu-id="9b0f9-134">\#\*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="9b0f9-135">start_event:SNL001:subsystem 用户已启动</span><span class="sxs-lookup"><span data-stu-id="9b0f9-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="9b0f9-136">stop_event:SNL002:subsystem 用户已关闭</span><span class="sxs-lookup"><span data-stu-id="9b0f9-136">stop_event:SNL002:subsystem User is down</span></span>  
    
  
## <a name="complete-steps"></a><span data-ttu-id="9b0f9-137">完成步骤</span><span class="sxs-lookup"><span data-stu-id="9b0f9-137">Complete steps</span></span>
 <span data-ttu-id="9b0f9-138">[FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9b0f9-138">[FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="9b0f9-139">[步骤 1： 配置 SWIFT 适配器 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9b0f9-139">[Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="9b0f9-140">[步骤 3： 创建发送端口和接收端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="9b0f9-140">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="9b0f9-141">步骤 4：测试 FileAct 存储和转发端到端方案</span><span class="sxs-lookup"><span data-stu-id="9b0f9-141">Step 4: Test FileAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)