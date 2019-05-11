---
title: SMTP 适配器性能计数器 |Microsoft Docs
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
ms.openlocfilehash: 739f926ed4b42b254c5c57e5f71a1cb914dbcb5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401849"
---
# <a name="smtp-adapter-performance-counters"></a><span data-ttu-id="57806-102">SMTP 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="57806-102">SMTP Adapter Performance Counters</span></span>
<span data-ttu-id="57806-103">性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。</span><span class="sxs-lookup"><span data-stu-id="57806-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="57806-104">性能计数器可以帮助您确定和解决服务器性能问题。</span><span class="sxs-lookup"><span data-stu-id="57806-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="57806-105">以下性能计数器都可以访问每个主机实例下**biztalk: Smtp Send Adapter**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="57806-105">The following performance counters are accessible for each host instance under the **BizTalk:SMTP Send Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="57806-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="57806-106">**Category**</span></span>|<span data-ttu-id="57806-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="57806-107">**Counter**</span></span>|<span data-ttu-id="57806-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="57806-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="57806-109">Biztalk: Smtp 发送适配器</span><span class="sxs-lookup"><span data-stu-id="57806-109">BizTalk:SMTP Send Adapter</span></span>|<span data-ttu-id="57806-110">发送的消息</span><span class="sxs-lookup"><span data-stu-id="57806-110">Messages sent</span></span>|<span data-ttu-id="57806-111">SMTP 适配器发送的消息的总数。</span><span class="sxs-lookup"><span data-stu-id="57806-111">Total number of messages sent by the SMTP adapter.</span></span> <span data-ttu-id="57806-112">已传输到 SMTP 服务器的消息才是增加计数器的数值。</span><span class="sxs-lookup"><span data-stu-id="57806-112">The counter is incremented only for messages that have been transmitted to the SMTP server.</span></span>|  
||<span data-ttu-id="57806-113">发送的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="57806-113">Messages sent/Sec</span></span>|<span data-ttu-id="57806-114">SMTP 适配器每秒发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="57806-114">Number of messages sent by the SMTP adapter per second.</span></span> <span data-ttu-id="57806-115">计数器仅应用于已传输到 SMTP 服务器的消息。</span><span class="sxs-lookup"><span data-stu-id="57806-115">The counter applies only to messages that have been transmitted to the SMTP server.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="57806-116">若要访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="57806-116">To access performance counters</span></span>  
 <span data-ttu-id="57806-117">使用以下步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="57806-117">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="57806-118">如果您使用的 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="57806-118">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="57806-119">单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="57806-119">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="57806-120">在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="57806-120">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="57806-121">在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: Smtp Send Adapter**性能计数器对象，然后选择要进行的计数器监视</span><span class="sxs-lookup"><span data-stu-id="57806-121">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:SMTP Send Adapter**performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="57806-122">在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="57806-122">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="57806-123">若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="57806-123">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="57806-124">添加计数器之后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="57806-124">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="57806-125">所选的性能计数器随即显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="57806-125">The selected performance counters appear on the **Performance Monitor** screen.</span></span>