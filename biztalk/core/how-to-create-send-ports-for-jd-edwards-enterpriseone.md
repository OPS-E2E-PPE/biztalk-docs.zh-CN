---
title: "如何为博士 Edwards EnterpriseOne 创建发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, send ports
- send ports, creating [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], send ports
- send ports, JD Edwards EnterpriseOne adapters
- creating, send ports [JD Edwards EnterpriseOne adapters]
ms.assetid: 687f9207-ad3e-41ea-8640-5b9b6efbc14e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36a3e8d2d3e8e1db230a03d9c4a0351d3a0f8394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-enterpriseone"></a><span data-ttu-id="adc74-102">如何创建 JD Edwards EnterpriseOne 的发送端口</span><span class="sxs-lookup"><span data-stu-id="adc74-102">How to Create Send Ports for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="adc74-103">使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 创建发送端口。</span><span class="sxs-lookup"><span data-stu-id="adc74-103">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="adc74-104">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="adc74-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="adc74-105">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="adc74-105">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="adc74-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开你想要创建发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="adc74-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="adc74-107">右键单击**发送端口**单击**新建**，然后单击**静态请求-响应端口**。</span><span class="sxs-lookup"><span data-stu-id="adc74-107">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="adc74-108">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="adc74-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="adc74-109">在**名称**框中，键入发送端口名称 (例如， `SendToJDE`)。</span><span class="sxs-lookup"><span data-stu-id="adc74-109">In the **Name** box, type a send port name (for example, `SendToJDE`).</span></span>  
  
    -   <span data-ttu-id="adc74-110">从**类型**下拉列表中，选择**JDEdwards**。</span><span class="sxs-lookup"><span data-stu-id="adc74-110">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="adc74-111">从**发送处理程序**下拉列表中，选择发送处理程序地址。</span><span class="sxs-lookup"><span data-stu-id="adc74-111">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
5.  <span data-ttu-id="adc74-112">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="adc74-112">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc74-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="adc74-113">See Also</span></span>  
 [<span data-ttu-id="adc74-114">创建博士 Edwards EnterpriseOne 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="adc74-114">Creating JD Edwards EnterpriseOne Send Handlers</span></span>](../core/creating-jd-edwards-enterpriseone-send-handlers.md)