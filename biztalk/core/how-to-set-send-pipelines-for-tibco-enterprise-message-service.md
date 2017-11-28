---
title: "如何设置发送管道 TIBCO 企业消息服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines
- setting send pipelines
- pipelines, send
ms.assetid: 6a84d874-4b4d-4b23-913f-f5c72af1e96e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d037782e2580d52c6609c3669e2805aae92ce9eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-tibco-enterprise-message-service"></a><span data-ttu-id="09afc-102">如何设置 TIBCO Enterprise Message Service 的发送管道</span><span class="sxs-lookup"><span data-stu-id="09afc-102">How to Set Send Pipelines for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="09afc-103">用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器要求您分别选择 XMLTransmit 和 XMLReceive 作为发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="09afc-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service requires that you select XMLTransmit and XMLReceive for the Send and Receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="09afc-104">若要设置管道</span><span class="sxs-lookup"><span data-stu-id="09afc-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="09afc-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="09afc-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="09afc-106">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="09afc-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="09afc-107">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="09afc-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="09afc-108">例如，键入发送端口的名称`SendToTIBCOEMS`。</span><span class="sxs-lookup"><span data-stu-id="09afc-108">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="09afc-109">从**类型**下拉列表中，选择**TIBCO EMS**。</span><span class="sxs-lookup"><span data-stu-id="09afc-109">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="09afc-110">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="09afc-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="09afc-111">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="09afc-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="09afc-112">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="09afc-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="09afc-113">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="09afc-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09afc-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09afc-114">See Also</span></span>  
 [<span data-ttu-id="09afc-115">如何设置 TIBCO 企业消息服务接收管道</span><span class="sxs-lookup"><span data-stu-id="09afc-115">How to Set Receive Pipelines for TIBCO Enterprise Message Service</span></span>](../core/how-to-set-receive-pipelines-for-tibco-enterprise-message-service.md)