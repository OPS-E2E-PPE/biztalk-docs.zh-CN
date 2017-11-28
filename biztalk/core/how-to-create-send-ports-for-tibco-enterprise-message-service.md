---
title: "如何为 TIBCO 企业消息服务创建发送端口 |Microsoft 文档"
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
ms.assetid: 6e569244-494e-4db4-8030-eda3b390d073
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfadeb3306687bfcbea27c0df41973b12b003563
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-tibco-enterprise-message-service"></a><span data-ttu-id="910c6-102">如何创建 TIBCO Enterprise Message Service 的发送端口</span><span class="sxs-lookup"><span data-stu-id="910c6-102">How to Create Send Ports for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="910c6-103">请按照以下步骤创建发送端口。</span><span class="sxs-lookup"><span data-stu-id="910c6-103">Follow these steps to create a send port.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="910c6-104">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="910c6-104">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="910c6-105">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="910c6-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="910c6-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="910c6-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="910c6-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="910c6-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="910c6-108">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="910c6-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="910c6-109">例如，键入发送端口的名称`SendToTIBCOEMS`。</span><span class="sxs-lookup"><span data-stu-id="910c6-109">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="910c6-110">从**类型**下拉列表中，选择**TIBCO EMS**。</span><span class="sxs-lookup"><span data-stu-id="910c6-110">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="910c6-111">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="910c6-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="910c6-112">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="910c6-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="910c6-113">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="910c6-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="910c6-114">单击**配置**配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="910c6-114">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="910c6-115">在**TIBCO EMS 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="910c6-115">In the **TIBCO EMS Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="910c6-116">输入**消息处理**，**服务器连接定义**，**事务支持**，**用户名**，和**密码**。</span><span class="sxs-lookup"><span data-stu-id="910c6-116">Enter **Message Handling**, **Server Connection Definition**, **Transaction Support**, **Username**, and the **password**.</span></span>  
  
         <span data-ttu-id="910c6-117">您不必设置登录信息。</span><span class="sxs-lookup"><span data-stu-id="910c6-117">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="910c6-118">在列表中选择为表示 TIBCO EMS 系统所创建的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="910c6-118">In the list, select the affiliate application you created to represent the TIBCO EMS system.</span></span>  
  
    3.  <span data-ttu-id="910c6-119">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="910c6-119">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="910c6-120">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="910c6-120">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="910c6-121">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="910c6-121">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="910c6-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="910c6-122">See Also</span></span>  
 <span data-ttu-id="910c6-123">[设置为发送端口的 TIBCO 企业消息服务传输属性](../core/setting-tibco-enterprise-message-service-transport-properties-for-the-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="910c6-123">[Setting TIBCO Enterprise Message Service Transport Properties for the Send Port](../core/setting-tibco-enterprise-message-service-transport-properties-for-the-send-port.md) </span></span>  
 [<span data-ttu-id="910c6-124">创建 TIBCO 企业消息服务发送处理程序</span><span class="sxs-lookup"><span data-stu-id="910c6-124">Creating  TIBCO Enterprise Message Service Send Handlers</span></span>](../core/creating-tibco-enterprise-message-service-send-handlers.md)