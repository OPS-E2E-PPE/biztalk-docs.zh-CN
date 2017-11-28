---
title: "如何为 TIBCO 会合创建发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- ports, send
- send ports, creating
ms.assetid: 0c8d9fdc-b273-4876-9f93-b5a85539a3c1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0b6e7dbb1a3b32979c94ec1af9483bd9fcb7cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a><span data-ttu-id="ac5a7-102">如何创建 TIBCO Rendezvous 的发送端口</span><span class="sxs-lookup"><span data-stu-id="ac5a7-102">How to Create Send Ports for TIBCO Rendezvous</span></span>
<span data-ttu-id="ac5a7-103">请按照以下步骤，使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 创建一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-103">Follow these steps to create a send port using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="ac5a7-104">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="ac5a7-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="ac5a7-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="ac5a7-106">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="ac5a7-107">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ac5a7-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ac5a7-108">例如，键入发送端口的名称`SendToTIBCORV`。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-108">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="ac5a7-109">从**类型**下拉列表中，选择**TIBCO 会合**。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-109">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="ac5a7-110">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="ac5a7-111">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="ac5a7-112">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="ac5a7-113">单击**配置**配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-113">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="ac5a7-114">在**TIBCO 会合传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ac5a7-114">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ac5a7-115">输入属性。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-115">Enter the properties.</span></span>  
  
         <span data-ttu-id="ac5a7-116">您不必设置登录信息。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-116">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="ac5a7-117">在列表中，选择 SSO 关联应用程序创建的用来表示 TIBCO 会合系统。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-117">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="ac5a7-118">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-118">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="ac5a7-119">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-119">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="ac5a7-120">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="ac5a7-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5a7-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac5a7-121">See Also</span></span>  
 [<span data-ttu-id="ac5a7-122">创建 TIBCO 会合发送处理程序</span><span class="sxs-lookup"><span data-stu-id="ac5a7-122">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)