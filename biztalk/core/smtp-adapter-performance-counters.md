---
title: SMTP 适配器性能计数器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c7aa7dd-1674-4bbb-b22f-92204d55c4b8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3503b5a37a7b2ab48be2478879cc61187895029
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973387"
---
# <a name="smtp-adapter-performance-counters"></a><span data-ttu-id="540d2-102">SMTP 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="540d2-102">SMTP Adapter Performance Counters</span></span>
<span data-ttu-id="540d2-103">使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="540d2-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="540d2-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="540d2-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="540d2-105">以下性能计数器进行访问每个主机实例下**BizTalk:SMTP 发送适配器**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="540d2-105">The following performance counters are accessible for each host instance under the **BizTalk:SMTP Send Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="540d2-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="540d2-106">**Category**</span></span>|<span data-ttu-id="540d2-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="540d2-107">**Counter**</span></span>|<span data-ttu-id="540d2-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="540d2-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="540d2-109">BizTalk:SMTP Send Adapter</span><span class="sxs-lookup"><span data-stu-id="540d2-109">BizTalk:SMTP Send Adapter</span></span>|<span data-ttu-id="540d2-110">发送的消息</span><span class="sxs-lookup"><span data-stu-id="540d2-110">Messages sent</span></span>|<span data-ttu-id="540d2-111">SMTP 适配器已发送的消息总数。</span><span class="sxs-lookup"><span data-stu-id="540d2-111">Total number of messages sent by the SMTP adapter.</span></span> <span data-ttu-id="540d2-112">只有消息已传输到 SMTP 服务器时，该计数器的值才会增加。</span><span class="sxs-lookup"><span data-stu-id="540d2-112">The counter is incremented only for messages that have been transmitted to the SMTP server.</span></span>|  
||<span data-ttu-id="540d2-113">每秒发送的消息数</span><span class="sxs-lookup"><span data-stu-id="540d2-113">Messages sent/Sec</span></span>|<span data-ttu-id="540d2-114">SMTP 适配器每秒发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="540d2-114">Number of messages sent by the SMTP adapter per second.</span></span> <span data-ttu-id="540d2-115">计数器仅适用于已传送到 SMTP 服务器的消息。</span><span class="sxs-lookup"><span data-stu-id="540d2-115">The counter applies only to messages that have been transmitted to the SMTP server.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="540d2-116">访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="540d2-116">To access performance counters</span></span>  
 <span data-ttu-id="540d2-117">依照下述步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="540d2-117">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="540d2-118">如果您使用的是 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="540d2-118">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="540d2-119">单击**启动**，指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="540d2-119">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="540d2-120">在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="540d2-120">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="540d2-121">在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:SMTP 发送适配器**性能计数器对象，然后选择要将的计数器监视</span><span class="sxs-lookup"><span data-stu-id="540d2-121">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:SMTP Send Adapter**performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="540d2-122">在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="540d2-122">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="540d2-123">若要选择的所有可用的计数器实例，选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="540d2-123">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="540d2-124">添加计数器后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="540d2-124">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="540d2-125">所选的性能计数器显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="540d2-125">The selected performance counters appear on the **Performance Monitor** screen.</span></span>