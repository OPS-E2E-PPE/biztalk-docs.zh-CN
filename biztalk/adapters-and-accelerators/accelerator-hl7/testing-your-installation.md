---
title: 测试安装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing installation
- installing, testing installation
ms.assetid: db27a75c-db7f-46ff-b8ef-2624ff18dcc8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d2d94ffce01bd299ad836b7f1fb7c82f66a8196
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971902"
---
# <a name="testing-your-installation"></a><span data-ttu-id="4caf8-102">测试安装</span><span class="sxs-lookup"><span data-stu-id="4caf8-102">Testing Your Installation</span></span>
<span data-ttu-id="4caf8-103">你可以设置您[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]的端到端教程通过手动运行或通过执行端到端教程程序来测试安装。</span><span class="sxs-lookup"><span data-stu-id="4caf8-103">You can set up your [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] installation for testing either by manually running through the end-to-end tutorial or by executing the end-to-end tutorial program.</span></span> <span data-ttu-id="4caf8-104">若要执行该程序，可单击**启动教程**按钮在安装期间或在 C:\Program Files\Microsoft BizTalk 中执行 EndToEndTutorial.exe\<版本\>HL7\SDK\ 的快捷键（后运行安装和配置） 的端到端教程文件夹。</span><span class="sxs-lookup"><span data-stu-id="4caf8-104">To exercise the program, either click the **Launch Tutorial** button during setup or execute EndToEndTutorial.exe in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder (after running installation and configuration).</span></span> <span data-ttu-id="4caf8-105">这两种自动操作将执行相同的安装步骤，你将通过运行本教程通过手动执行。</span><span class="sxs-lookup"><span data-stu-id="4caf8-105">Either of these automated actions will perform the same setup steps that you would manually perform by running through the tutorial.</span></span> <span data-ttu-id="4caf8-106">端到端教程程序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4caf8-106">The end-to-end tutorial program does the following:</span></span>  
  
- <span data-ttu-id="4caf8-107">部署 MSH 和确认架构</span><span class="sxs-lookup"><span data-stu-id="4caf8-107">Deploys MSH and ACK schemas</span></span>  
  
- <span data-ttu-id="4caf8-108">部署版本 2.3.1 通用架构</span><span class="sxs-lookup"><span data-stu-id="4caf8-108">Deploys Version 2.3.1 common schemas</span></span>  
  
- <span data-ttu-id="4caf8-109">部署 ADT 架构</span><span class="sxs-lookup"><span data-stu-id="4caf8-109">Deploys ADT schemas</span></span>  
  
- <span data-ttu-id="4caf8-110">创建 Tutorial_1WayReceive 接收端口</span><span class="sxs-lookup"><span data-stu-id="4caf8-110">Creates the Tutorial_1WayReceive receive port</span></span>  
  
- <span data-ttu-id="4caf8-111">创建 Tutorial_MLLPReceive 接收位置</span><span class="sxs-lookup"><span data-stu-id="4caf8-111">Creates the Tutorial_MLLPReceive receive location</span></span>  
  
- <span data-ttu-id="4caf8-112">创建 Tutorial_BTAHL7PickUp 接收端口</span><span class="sxs-lookup"><span data-stu-id="4caf8-112">Creates the Tutorial_BTAHL7PickUp receive port</span></span>  
  
- <span data-ttu-id="4caf8-113">创建 Tutorial_FileReceiveLoc 接收位置</span><span class="sxs-lookup"><span data-stu-id="4caf8-113">Creates the Tutorial_FileReceiveLoc receive location</span></span>  
  
- <span data-ttu-id="4caf8-114">创建 Tutorial_sendAck_ADT 发送端口</span><span class="sxs-lookup"><span data-stu-id="4caf8-114">Creates the Tutorial_sendAck_ADT send port</span></span>  
  
- <span data-ttu-id="4caf8-115">创建 Tutorial_sendMsg_RX 发送端口</span><span class="sxs-lookup"><span data-stu-id="4caf8-115">Creates the Tutorial_sendMsg_RX send port</span></span>  
  
- <span data-ttu-id="4caf8-116">创建 Tutorial_BTAHL7Drop 发送端口</span><span class="sxs-lookup"><span data-stu-id="4caf8-116">Creates the Tutorial_BTAHL7Drop send port</span></span>  
  
- <span data-ttu-id="4caf8-117">创建 Tutorial_MLLPSend 发送端口</span><span class="sxs-lookup"><span data-stu-id="4caf8-117">Creates the Tutorial_MLLPSend send port</span></span>  
  
- <span data-ttu-id="4caf8-118">创建 Tutorial_ADTSystem 参与方</span><span class="sxs-lookup"><span data-stu-id="4caf8-118">Creates the Tutorial_ADTSystem party</span></span>  
  
- <span data-ttu-id="4caf8-119">创建 Tutorial_RXSystem 参与方</span><span class="sxs-lookup"><span data-stu-id="4caf8-119">Creates the Tutorial_RXSystem party</span></span>  
  
- <span data-ttu-id="4caf8-120">创建 Tutorial_HISystem 参与方</span><span class="sxs-lookup"><span data-stu-id="4caf8-120">Creates the Tutorial_HISystem party</span></span>  
  
- <span data-ttu-id="4caf8-121">重新启动 BizTalk 服务</span><span class="sxs-lookup"><span data-stu-id="4caf8-121">Restarts the BizTalk Service</span></span>  
  
  <span data-ttu-id="4caf8-122">如果已执行端到端教程程序，可以为 HL7 预定义文件夹中删除测试实例。</span><span class="sxs-lookup"><span data-stu-id="4caf8-122">If you have executed the end-to-end tutorial program, you can drop a test instance for HL7 in a pre-defined folder.</span></span> <span data-ttu-id="4caf8-123">与文件夹关联的接收管道提取消息并对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="4caf8-123">The receive pipeline associated with the folder picks up the message and processes it.</span></span> <span data-ttu-id="4caf8-124">基于筛选器，发送管道将文档路由到目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="4caf8-124">Based on filters, a send pipeline routes the document to the destination folder.</span></span> <span data-ttu-id="4caf8-125">此简单的"往返"运用 Microsoft 的基本构建基块[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 引擎，并确认您的安装。</span><span class="sxs-lookup"><span data-stu-id="4caf8-125">This simple "round-trip" exercises the basic building blocks of the Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) engine and confirms your installation.</span></span>  
  
### <a name="to-test-your-installation"></a><span data-ttu-id="4caf8-126">若要测试您的安装</span><span class="sxs-lookup"><span data-stu-id="4caf8-126">To test your installation</span></span>  
  
1. <span data-ttu-id="4caf8-127">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for HL7\SDK\End 端到端教程文件夹。</span><span class="sxs-lookup"><span data-stu-id="4caf8-127">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder.</span></span>  
  
2. <span data-ttu-id="4caf8-128">右键单击**TutorialSampleInstance.txt**文件，，然后单击**副本**。</span><span class="sxs-lookup"><span data-stu-id="4caf8-128">Right-click the **TutorialSampleInstance.txt** file, and then click **Copy**.</span></span>  
  
3. <span data-ttu-id="4caf8-129">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_ 的快捷键BTAHL7PickUp 文件夹。</span><span class="sxs-lookup"><span data-stu-id="4caf8-129">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp folder.</span></span>  
  
4. <span data-ttu-id="4caf8-130">右键单击文件夹，然后依次**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="4caf8-130">Right-click the folder, and then click **Paste**.</span></span>  
  
5. <span data-ttu-id="4caf8-131">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_ 的快捷键BTAHL7Drop 文件夹。</span><span class="sxs-lookup"><span data-stu-id="4caf8-131">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop folder.</span></span>  
  
    <span data-ttu-id="4caf8-132">你可以验证您的安装是否成功，如果已处理的实例出现在**Tutorial_BTAHL7Drop**的文件夹\< *Guid*\>.txt。</span><span class="sxs-lookup"><span data-stu-id="4caf8-132">You can verify if your installation was successful if the processed instance appears in the **Tutorial_BTAHL7Drop** folder as \<*Guid*\>.txt.</span></span>  
  
   <span data-ttu-id="4caf8-133">请继续执行下一步[准备使用本教程](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)。</span><span class="sxs-lookup"><span data-stu-id="4caf8-133">Proceed to the next step, [Preparing to Use the Tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md).</span></span>