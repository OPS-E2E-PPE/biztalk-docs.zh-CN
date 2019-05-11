---
title: 步骤 3E:添加 FILE 发送端口为 FileAct 存储和转发方案，以捕获 Sw-exchangesnfresponse 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04bad2ab-1ea4-4602-9dee-5b9af9be3b93
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e77a6b8ded2a2a779155df621b3e25267b20370
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365378"
---
# <a name="step-3e-add-a-file-send-port-for-the-fileact-store-and-forward-scenario-to-capture-sw-exchangesnfresponse-messages"></a><span data-ttu-id="109c0-102">步骤 3E:添加 FILE 发送端口为 FileAct 存储和转发方案，以捕获 Sw-exchangesnfresponse 消息</span><span class="sxs-lookup"><span data-stu-id="109c0-102">Step 3E: Add a FILE Send Port for the FileAct Store and Forward Scenario to capture Sw-ExchangeSnFResponse messages</span></span>
<span data-ttu-id="109c0-103">在开始此步骤之前，必须完成[步骤 3D:添加 FILEACT 发送端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="109c0-103">Before you begin this step, you must complete [Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a><span data-ttu-id="109c0-104">若要添加 FILE 发送端口以捕获状态事件：</span><span class="sxs-lookup"><span data-stu-id="109c0-104">To add a FILE send port to capture Status Events:</span></span>  
  
1.  <span data-ttu-id="109c0-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="109c0-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="109c0-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="109c0-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="109c0-107">右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="109c0-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
4.  <span data-ttu-id="109c0-108">在中**发送端口属性**窗口中，命名该发送端口，Tutorial_ GetStatusReports。</span><span class="sxs-lookup"><span data-stu-id="109c0-108">In the **Send Port Properties** window, name the send port, Tutorial_ GetStatusReports.</span></span>  
  
5.  <span data-ttu-id="109c0-109">在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="109c0-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="109c0-110">在中**FILE 传输属性**对话框中**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ StatusEvents，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="109c0-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ StatusEvents, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="109c0-111">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="109c0-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="109c0-112">**使用此**</span><span class="sxs-lookup"><span data-stu-id="109c0-112">**Use this**</span></span>|<span data-ttu-id="109c0-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="109c0-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="109c0-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="109c0-114">**Send handler**</span></span>|<span data-ttu-id="109c0-115">从下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="109c0-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="109c0-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="109c0-116">**Send pipeline**</span></span>|<span data-ttu-id="109c0-117">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="109c0-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="109c0-118">在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="109c0-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="109c0-119">**使用此**</span><span class="sxs-lookup"><span data-stu-id="109c0-119">**Use this**</span></span>|<span data-ttu-id="109c0-120">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="109c0-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="109c0-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="109c0-121">**Property**</span></span>|<span data-ttu-id="109c0-122">Select BTS.MessageType</span><span class="sxs-lookup"><span data-stu-id="109c0-122">Select BTS.MessageType</span></span>|  
    |<span data-ttu-id="109c0-123">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="109c0-123">**Operator**</span></span>|<span data-ttu-id="109c0-124">选择 = =</span><span class="sxs-lookup"><span data-stu-id="109c0-124">Select ==</span></span>|  
    |<span data-ttu-id="109c0-125">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="109c0-125">**Value**</span></span>|<span data-ttu-id="109c0-126">Type Sw-HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="109c0-126">Type Sw-HandleFileEventRequest</span></span>|  
    |<span data-ttu-id="109c0-127">**分组**</span><span class="sxs-lookup"><span data-stu-id="109c0-127">**Group**</span></span>|<span data-ttu-id="109c0-128">或</span><span class="sxs-lookup"><span data-stu-id="109c0-128">Or</span></span>|  
    |<span data-ttu-id="109c0-129">**属性**</span><span class="sxs-lookup"><span data-stu-id="109c0-129">**Property**</span></span>|<span data-ttu-id="109c0-130">选择 BTS。</span><span class="sxs-lookup"><span data-stu-id="109c0-130">Select BTS.</span></span> <span data-ttu-id="109c0-131">MessageType</span><span class="sxs-lookup"><span data-stu-id="109c0-131">MessageType</span></span>|  
    |<span data-ttu-id="109c0-132">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="109c0-132">**Operator**</span></span>|<span data-ttu-id="109c0-133">选择 = =</span><span class="sxs-lookup"><span data-stu-id="109c0-133">Select ==</span></span>|  
    |<span data-ttu-id="109c0-134">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="109c0-134">**Value**</span></span>|<span data-ttu-id="109c0-135">类型 Sw-exchangesnfresponse</span><span class="sxs-lookup"><span data-stu-id="109c0-135">Type Sw-ExchangeSnFResponse</span></span>|