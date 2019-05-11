---
title: 第 1 步：配置一个 FILE 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df591263-964a-4ad8-bc3a-a553de8dae4f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ae1bb74c162a0a61521392fc4cd75e99ba26297
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392832"
---
# <a name="step-1-configure-a-file-receive-location"></a><span data-ttu-id="8104c-102">第 1 步：配置一个 FILE 接收位置</span><span class="sxs-lookup"><span data-stu-id="8104c-102">Step 1: Configure a FILE Receive Location</span></span>
<span data-ttu-id="8104c-103">在本主题中，配置文件接收位置使用你存放至文件夹来调用发送端口的虚拟请求消息。</span><span class="sxs-lookup"><span data-stu-id="8104c-103">In this topic, you configure a FILE receive location that consumes the dummy request message that you drop to a file folder to invoke the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8104c-104">在本教程中的步骤假定你使用默认应用程序 (**BizTalk Application 1**) 来创建解决方案。</span><span class="sxs-lookup"><span data-stu-id="8104c-104">The steps in this tutorial assume that you use the default application (**BizTalk Application 1**) to create the solution.</span></span> <span data-ttu-id="8104c-105">您还可以创建另一个应用程序和该应用程序中任何执行相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="8104c-105">You can also create another application and perform the same steps in any that application.</span></span>  
  
### <a name="to-configure-a-file-receive-location"></a><span data-ttu-id="8104c-106">若要配置 FILE 接收位置</span><span class="sxs-lookup"><span data-stu-id="8104c-106">To configure a FILE receive location</span></span>  
  
1.  <span data-ttu-id="8104c-107">从 BizTalk Server 管理控制台中下, **BizTalk Application 1**节点，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="8104c-107">From BizTalk Server Administration Console, under the **BizTalk Application 1** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="8104c-108">在常规选项卡上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8104c-108">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="8104c-109">使用此选项</span><span class="sxs-lookup"><span data-stu-id="8104c-109">Use this</span></span>|<span data-ttu-id="8104c-110">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8104c-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8104c-111">**名称**</span><span class="sxs-lookup"><span data-stu-id="8104c-111">**Name**</span></span>|<span data-ttu-id="8104c-112">类型**ReceivePortRestAzureMarketPlace**。</span><span class="sxs-lookup"><span data-stu-id="8104c-112">Type **ReceivePortRestAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="8104c-113">**为失败消息启用路由功能**</span><span class="sxs-lookup"><span data-stu-id="8104c-113">**Enable routing for failed messages**</span></span>|<span data-ttu-id="8104c-114">（清除）</span><span class="sxs-lookup"><span data-stu-id="8104c-114">(clear)</span></span>|  
  
3.  <span data-ttu-id="8104c-115">单击**接收位置**，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="8104c-115">Click **Receive Locations**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="8104c-116">从接收位置 1 – 接收位置属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8104c-116">From Receive Location1 – Receive Location Properties, do the following:</span></span>  
  
    |<span data-ttu-id="8104c-117">使用此选项</span><span class="sxs-lookup"><span data-stu-id="8104c-117">Use this</span></span>|<span data-ttu-id="8104c-118">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8104c-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8104c-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="8104c-119">**Name**</span></span>|<span data-ttu-id="8104c-120">类型**ReceiveLocationAzureMarketPlace**。</span><span class="sxs-lookup"><span data-stu-id="8104c-120">Type **ReceiveLocationAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="8104c-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="8104c-121">**Type**</span></span>|<span data-ttu-id="8104c-122">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="8104c-122">Select **FILE**.</span></span>|  
    |<span data-ttu-id="8104c-123">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="8104c-123">**Receive handler**</span></span>|<span data-ttu-id="8104c-124">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="8104c-124">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="8104c-125">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="8104c-125">**Receive pipeline**</span></span>|<span data-ttu-id="8104c-126">选择**PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="8104c-126">Select **PassThruReceive**.</span></span>|  
  
5.  <span data-ttu-id="8104c-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="8104c-127">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="8104c-128">从文件传输属性中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8104c-128">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="8104c-129">使用此选项</span><span class="sxs-lookup"><span data-stu-id="8104c-129">Use this</span></span>|<span data-ttu-id="8104c-130">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8104c-130">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8104c-131">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="8104c-131">**Receive folder**</span></span>|<span data-ttu-id="8104c-132">键入将存放虚拟请求消息的位置。</span><span class="sxs-lookup"><span data-stu-id="8104c-132">Type a location where you will drop the dummy request message.</span></span>|  
    |<span data-ttu-id="8104c-133">**文件名**</span><span class="sxs-lookup"><span data-stu-id="8104c-133">**File name**</span></span>|<span data-ttu-id="8104c-134">保留 `*.xml`</span><span class="sxs-lookup"><span data-stu-id="8104c-134">Retain `*.xml`</span></span>|  
  
7.  <span data-ttu-id="8104c-135">单击**确定**直到您退出所有对话框。</span><span class="sxs-lookup"><span data-stu-id="8104c-135">Click **OK** until you exit all the dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8104c-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="8104c-136">See Also</span></span>  
 [<span data-ttu-id="8104c-137">教程 5:调用 REST 接口使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8104c-137">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)