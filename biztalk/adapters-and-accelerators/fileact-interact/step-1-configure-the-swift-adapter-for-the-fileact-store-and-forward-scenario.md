---
title: 第 1 步：配置 SWIFT 适配器为 FileAct 存储和转发方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18653322-b748-4954-93f7-9a7a39e406f8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40426064973a74c96d7ce3be2fd681b69e3d7f5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366486"
---
# <a name="step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="2f4ab-102">第 1 步：配置 SWIFT 适配器为 FileAct 存储和转发方案</span><span class="sxs-lookup"><span data-stu-id="2f4ab-102">Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="2f4ab-103">完整[准备使用本教程](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-103">Complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md) before you begin this step.</span></span>
  
## <a name="configure-the-swift-adapter"></a><span data-ttu-id="2f4ab-104">配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="2f4ab-104">Configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="2f4ab-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2f4ab-106">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**平台设置**，展开**适配器**，右键单击**FILEACT**，依次指向**新建**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-106">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **FILEACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="2f4ab-107">在中**FILEACT – 适配器 HandlerProperties**对话框中，在**常规**选项卡上，从**主机名**下拉列表中，选择**fileacthost**，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-107">In the **FILEACT – Adapter HandlerProperties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **fileacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="2f4ab-108">在中**FILEACT 传输属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2f4ab-108">In the **FILEACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="2f4ab-109">**使用此**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-109">**Use this**</span></span>|<span data-ttu-id="2f4ab-110">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="2f4ab-111">**参数**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-111">**Arguments**</span></span>|<span data-ttu-id="2f4ab-112">键入以下参数:-SagMessagePartner \<Fileact 客户端消息合作伙伴创建在压降\>**注意：** 参数中的客户端是 MessagePartner 压降中配置。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-112">Type the following argument: -SagMessagePartner \<Fileact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="2f4ab-113">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-113">**Crypto Mode**</span></span>|<span data-ttu-id="2f4ab-114">从下拉列表中，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="2f4ab-115">**FACryptoMode**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-115">**FACryptoMode**</span></span>|<span data-ttu-id="2f4ab-116">从下拉列表中，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-116">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="2f4ab-117">**LogMessages**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-117">**LogMessages**</span></span>|<span data-ttu-id="2f4ab-118">从下拉列表中，选择 **，则返回 TRUE**。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-118">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="2f4ab-119">这样，要捕获和跟踪在 BAM 门户中的消息事件。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-119">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="2f4ab-120">**启用**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-120">**Enable**</span></span>|<span data-ttu-id="2f4ab-121">False</span><span class="sxs-lookup"><span data-stu-id="2f4ab-121">False</span></span>|  
    |<span data-ttu-id="2f4ab-122">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-122">**Event end-point**</span></span>|<span data-ttu-id="2f4ab-123">键入相应压降终结点。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-123">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="2f4ab-124">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-124">**PhysicalFolderName**</span></span>|<span data-ttu-id="2f4ab-125">在服务器上键入文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-125">Type the name of the folder on the server.</span></span> <span data-ttu-id="2f4ab-126">例如，C:\Fileact\ServerLocation。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-126">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="2f4ab-127">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-127">**PollingInterval**</span></span>|<span data-ttu-id="2f4ab-128">键入适当的时间间隔 （以秒为单位） 后其检查适配器文件传输状态。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-128">Type the appropriate interval (in seconds) after which the adapter checks for the status of file transfer.</span></span>|  
    |<span data-ttu-id="2f4ab-129">**密码**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-129">**Password**</span></span>|<span data-ttu-id="2f4ab-130">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-130">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="2f4ab-131">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-131">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="2f4ab-132">**用户名**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-132">**User Name**</span></span>|<span data-ttu-id="2f4ab-133">键入用于连接到压降的用户名。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-133">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="2f4ab-134">单击**确定**以关闭 FILEACT 传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-134">Click **OK** to close the FILEACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="2f4ab-135">单击**确定**关闭 FILEACT – 适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-135">Click **OK** to close the FILEACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="2f4ab-136">在消息框中，单击**确定**，然后重新启动 FileAct 主机实例。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-136">In the Message box, click **OK**, and then restart the FileAct host instance.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="2f4ab-137">完成的步骤</span><span class="sxs-lookup"><span data-stu-id="2f4ab-137">Complete steps</span></span>
 <span data-ttu-id="2f4ab-138">[FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="2f4ab-138">[FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="2f4ab-139">[步骤 2：向为 FileAct 存储和转发方案 Paramfile 添加 SWIFTNet 配置](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="2f4ab-139">[Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="2f4ab-140">[步骤 3：创建发送端口和接收端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="2f4ab-140">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="2f4ab-141">步骤 4：测试 FileAct 存储和转发端到端方案</span><span class="sxs-lookup"><span data-stu-id="2f4ab-141">Step 4: Test FileAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)