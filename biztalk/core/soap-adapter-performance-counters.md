---
title: SOAP 适配器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40b54d4e-0a2e-483f-982a-97ab9fb59202
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5f13708fc59c02a9a74b652508aa74cf1a36f00
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314046"
---
# <a name="soap-adapter-performance-counters"></a><span data-ttu-id="eaf53-102">SOAP 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="eaf53-102">SOAP Adapter Performance Counters</span></span>
<span data-ttu-id="eaf53-103">性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。</span><span class="sxs-lookup"><span data-stu-id="eaf53-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="eaf53-104">性能计数器可以帮助您确定和解决服务器性能问题。</span><span class="sxs-lookup"><span data-stu-id="eaf53-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="eaf53-105">以下性能计数器都可以访问每个主机实例下**biztalk: Soap Receive Adapter**并**biztalk: Soap Send Adapter**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="eaf53-105">The following performance counters are accessible for each host instance under the **BizTalk:SOAP Receive Adapter** and the **BizTalk:SOAP Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="eaf53-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="eaf53-106">**Category**</span></span>|<span data-ttu-id="eaf53-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="eaf53-107">**Counter**</span></span>|<span data-ttu-id="eaf53-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="eaf53-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="eaf53-109">Biztalk: Soap 接收适配器</span><span class="sxs-lookup"><span data-stu-id="eaf53-109">BizTalk:SOAP Receive Adapter</span></span>|<span data-ttu-id="eaf53-110">接收的消息</span><span class="sxs-lookup"><span data-stu-id="eaf53-110">Messages received</span></span>|<span data-ttu-id="eaf53-111">接收适配器接收的 SOAP 消息的总数。</span><span class="sxs-lookup"><span data-stu-id="eaf53-111">Total number of messages received by the SOAP receive adapter.</span></span> <span data-ttu-id="eaf53-112">此计数器递增后请求消息完全读取的适配器从 SOAP 客户端。</span><span class="sxs-lookup"><span data-stu-id="eaf53-112">The counter is incremented after a request message is completely read by the adapter from the SOAP client.</span></span>|  
||<span data-ttu-id="eaf53-113">收到的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="eaf53-113">Messages received/Sec</span></span>|<span data-ttu-id="eaf53-114">适配器每秒接收的 soap 接收的消息数。</span><span class="sxs-lookup"><span data-stu-id="eaf53-114">Number of messages received by the SOAP receive adapter per second.</span></span> <span data-ttu-id="eaf53-115">计数器仅应用于已完全读取的适配器从 SOAP 客户端的请求消息。</span><span class="sxs-lookup"><span data-stu-id="eaf53-115">The counter applies only to request messages that have been completely read by the adapter from the SOAP client.</span></span>|  
|<span data-ttu-id="eaf53-116">BizTalk:SOAP Send Adapter</span><span class="sxs-lookup"><span data-stu-id="eaf53-116">BizTalk:SOAP Send Adapter</span></span>|<span data-ttu-id="eaf53-117">发送的消息</span><span class="sxs-lookup"><span data-stu-id="eaf53-117">Messages sent</span></span>|<span data-ttu-id="eaf53-118">发送适配器发送的 SOAP 消息的总数。</span><span class="sxs-lookup"><span data-stu-id="eaf53-118">Total number of messages sent by the SOAP send adapter.</span></span> <span data-ttu-id="eaf53-119">仅对已到达目标 URL 的消息是增加计数器的数值。</span><span class="sxs-lookup"><span data-stu-id="eaf53-119">The counter is incremented only for messages that have reached the destination URL.</span></span>|  
||<span data-ttu-id="eaf53-120">发送的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="eaf53-120">Messages sent/Sec</span></span>|<span data-ttu-id="eaf53-121">适配器每秒发送的 soap 发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="eaf53-121">Number of messages sent by the SOAP send adapter per second.</span></span> <span data-ttu-id="eaf53-122">计数器仅应用于已到达目标 URL 的消息。</span><span class="sxs-lookup"><span data-stu-id="eaf53-122">The counter applies only to messages that have reached the destination URL.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="eaf53-123">若要访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="eaf53-123">To access performance counters</span></span>  
 <span data-ttu-id="eaf53-124">使用以下步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="eaf53-124">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-server-2008"></a><span data-ttu-id="eaf53-125">如果使用 Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="eaf53-125">If you are using Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="eaf53-126">单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="eaf53-126">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="eaf53-127">在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="eaf53-127">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="eaf53-128">在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: Soap**性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="eaf53-128">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:SOAP** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="eaf53-129">在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="eaf53-129">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span> <span data-ttu-id="eaf53-130">若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="eaf53-130">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="eaf53-131">添加计数器之后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="eaf53-131">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="eaf53-132">所选的性能计数器随即显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="eaf53-132">The selected performance counters appear on the **Performance Monitor** screen.</span></span>