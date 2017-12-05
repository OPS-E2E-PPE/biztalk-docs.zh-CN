---
title: "步骤 1： 为 FileAct 实时方案配置 SWIFT 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afc52c63-9f83-4e90-9269-e90834b792bf
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991d3d37bab70e07eb21b21a040e3479fc2658df
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario"></a><span data-ttu-id="1909c-102">步骤 1： 为 FileAct 实时方案配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="1909c-102">Step 1: Configure the SWIFT Adapter for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="1909c-103">在开始此步骤之前，必须完成[准备使用本教程](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)。</span><span class="sxs-lookup"><span data-stu-id="1909c-103">Before you begin this step, you must complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="1909c-104">若要配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="1909c-104">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="1909c-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="1909c-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="1909c-106">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**平台设置**，展开**适配器**，右键单击**FILEACT**，指向**新建**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="1909c-106">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **FILEACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="1909c-107">在**FILEACT – 适配器处理程序属性**对话框中，在**常规**选项卡上，从**主机名**下拉列表中，选择**fileacthost**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="1909c-107">In the **FILEACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **fileacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="1909c-108">在**FILEACT 传输属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1909c-108">In the **FILEACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="1909c-109">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="1909c-109">**Use this**</span></span>|<span data-ttu-id="1909c-110">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="1909c-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="1909c-111">**参数**</span><span class="sxs-lookup"><span data-stu-id="1909c-111">**Arguments**</span></span>|<span data-ttu-id="1909c-112">键入以下参数:-SagMessagePartner \<Fileact 客户端消息合作伙伴创建在压降\>**注意：**自变量中的客户端是在压降中配置 MessagePartner。</span><span class="sxs-lookup"><span data-stu-id="1909c-112">Type the following argument: -SagMessagePartner \<Fileact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="1909c-113">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="1909c-113">**Crypto Mode**</span></span>|<span data-ttu-id="1909c-114">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="1909c-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="1909c-115">**FACryptoMode**</span><span class="sxs-lookup"><span data-stu-id="1909c-115">**FACryptoMode**</span></span>|<span data-ttu-id="1909c-116">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="1909c-116">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="1909c-117">**日志消息**</span><span class="sxs-lookup"><span data-stu-id="1909c-117">**LogMessages**</span></span>|<span data-ttu-id="1909c-118">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="1909c-118">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="1909c-119">这样将捕获和 BAM 门户中跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="1909c-119">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="1909c-120">**启用**</span><span class="sxs-lookup"><span data-stu-id="1909c-120">**Enable**</span></span>|<span data-ttu-id="1909c-121">False</span><span class="sxs-lookup"><span data-stu-id="1909c-121">False</span></span>|  
    |<span data-ttu-id="1909c-122">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="1909c-122">**Event end-point**</span></span>|<span data-ttu-id="1909c-123">键入相应压降终结点。</span><span class="sxs-lookup"><span data-stu-id="1909c-123">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="1909c-124">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="1909c-124">**PhysicalFolderName**</span></span>|<span data-ttu-id="1909c-125">键入服务器上的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="1909c-125">Type the name of the folder on the server.</span></span> <span data-ttu-id="1909c-126">例如，C:\Fileact\ServerLocation。</span><span class="sxs-lookup"><span data-stu-id="1909c-126">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="1909c-127">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="1909c-127">**PollingInterval**</span></span>|<span data-ttu-id="1909c-128">键入适当的间隔 （以秒为单位） 后检查适配器的状态的文件传输。</span><span class="sxs-lookup"><span data-stu-id="1909c-128">Type the appropriate interval (in seconds) after which the adapter checks for the status of file transfer.</span></span>|  
    |<span data-ttu-id="1909c-129">**密码**</span><span class="sxs-lookup"><span data-stu-id="1909c-129">**Password**</span></span>|<span data-ttu-id="1909c-130">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="1909c-130">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="1909c-131">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="1909c-131">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="1909c-132">**用户名**</span><span class="sxs-lookup"><span data-stu-id="1909c-132">**Username**</span></span>|<span data-ttu-id="1909c-133">键入用于连接到压降的用户名称。</span><span class="sxs-lookup"><span data-stu-id="1909c-133">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="1909c-134">单击**确定**以关闭 FILEACT 传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="1909c-134">Click **OK** to close the FILEACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="1909c-135">单击**确定**关闭 FILEACT – 适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="1909c-135">Click **OK** to close the FILEACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="1909c-136">在消息框中，单击**确定**，然后重新启动 FileAct 主机实例。</span><span class="sxs-lookup"><span data-stu-id="1909c-136">In the message box, click **OK**, and then restart the FileAct host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1909c-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1909c-137">See Also</span></span>  
 <span data-ttu-id="1909c-138">[FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="1909c-138">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="1909c-139">[步骤 2： 添加 SWIFTNet 配置到 Paramfile FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="1909c-139">[Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="1909c-140">[步骤 3： 创建发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="1909c-140">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="1909c-141">步骤 4：测试 FileAct 实时端到端方案</span><span class="sxs-lookup"><span data-stu-id="1909c-141">Step 4: Test FileAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)