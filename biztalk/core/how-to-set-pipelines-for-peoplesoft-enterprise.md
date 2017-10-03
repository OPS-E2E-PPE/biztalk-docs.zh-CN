---
title: "如何为 PeopleSoft 企业设置管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting pipelines
- pipelines, setting
ms.assetid: 36914615-eac0-47b6-9e66-deeb40d21f10
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69bebce2dadf0bb038b0e8c56ffa544ad02c78ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-pipelines-for-peoplesoft-enterprise"></a><span data-ttu-id="b9c0b-102">如何设置 PeopleSoft Enterprise 的管道</span><span class="sxs-lookup"><span data-stu-id="b9c0b-102">How to Set Pipelines for PeopleSoft Enterprise</span></span>
<span data-ttu-id="b9c0b-103">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器要求您选择一个适当的管道。</span><span class="sxs-lookup"><span data-stu-id="b9c0b-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise requires that you select an appropriate pipeline.</span></span>  
  
## <a name="setting-pipelines"></a><span data-ttu-id="b9c0b-104">设置管道</span><span class="sxs-lookup"><span data-stu-id="b9c0b-104">Setting Pipelines</span></span>  
  
#### <a name="to-set-pipelines"></a><span data-ttu-id="b9c0b-105">若要设置管道</span><span class="sxs-lookup"><span data-stu-id="b9c0b-105">To set pipelines</span></span>  
  
1.  <span data-ttu-id="b9c0b-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9c0b-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="b9c0b-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b9c0b-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="b9c0b-108">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b9c0b-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="b9c0b-109">例如，键入发送端口的名称`SSOSendToPeopleSoft`。</span><span class="sxs-lookup"><span data-stu-id="b9c0b-109">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="b9c0b-110">从**类型**下拉列表中，选择**PeopleSoft**。</span><span class="sxs-lookup"><span data-stu-id="b9c0b-110">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="b9c0b-111">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="b9c0b-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="b9c0b-112">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="b9c0b-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="b9c0b-113">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="b9c0b-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="b9c0b-114">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b9c0b-114">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c0b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9c0b-115">See Also</span></span>  
 [<span data-ttu-id="b9c0b-116">创建 PeopleSoft 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="b9c0b-116">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)