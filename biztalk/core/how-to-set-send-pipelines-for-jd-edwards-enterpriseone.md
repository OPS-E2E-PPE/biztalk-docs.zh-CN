---
title: "如何设置发送管道的博士 Edwards EnterpriseOne |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, send pipelines
- send pipelines, configuring [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], configuring
- adapters [JD Edwards EnterpriseOne adapters], send pipelines
- JD Edwards EnterpriseOne adapters, configuring
ms.assetid: 4cfcecc1-febe-47c8-b75f-2b84defcdbbc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c9a6337195c8050afca1f12a015ec492db7f7ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-jd-edwards-enterpriseone"></a><span data-ttu-id="464b2-102">如何设置 JD Edwards EnterpriseOne 的发送管道</span><span class="sxs-lookup"><span data-stu-id="464b2-102">How to Set Send Pipelines for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="464b2-103">Microsoft BizTalk Adapter for 博士 Edwards EnterpriseOne 要求你选择**XMLTransmit**和**XMLReceive**为发送和接收管道分别。</span><span class="sxs-lookup"><span data-stu-id="464b2-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne requires that you select **XMLTransmit** and **XMLReceive** for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="464b2-104">若要设置管道</span><span class="sxs-lookup"><span data-stu-id="464b2-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="464b2-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="464b2-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="464b2-106">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="464b2-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="464b2-107">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="464b2-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="464b2-108">例如，键入发送端口的名称`SendToJDEEnterpriseOne`。</span><span class="sxs-lookup"><span data-stu-id="464b2-108">Type a name for the send port, for example, `SendToJDEEnterpriseOne`.</span></span>  
  
    2.  <span data-ttu-id="464b2-109">从**类型**下拉列表中，选择**JDE EnterpriseOne**。</span><span class="sxs-lookup"><span data-stu-id="464b2-109">From the **Type** drop-down list, select **JDE EnterpriseOne**.</span></span>  
  
    3.  <span data-ttu-id="464b2-110">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="464b2-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="464b2-111">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="464b2-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="464b2-112">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="464b2-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="464b2-113">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="464b2-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="464b2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="464b2-114">See Also</span></span>  
 [<span data-ttu-id="464b2-115">创建博士 Edwards EnterpriseOne 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="464b2-115">Creating JD Edwards EnterpriseOne Send Handlers</span></span>](../core/creating-jd-edwards-enterpriseone-send-handlers.md)