---
title: "如何为 PeopleSoft 的企业创建发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: 374261ce-2cb5-4193-a0a2-658f989b2c60
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b6b5caa44976aec7a4afb8e0eccf5b1f8904111
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-peoplesoft-enterprise"></a><span data-ttu-id="1c070-102">如何创建 PeopleSoft Enterprise 的发送端口</span><span class="sxs-lookup"><span data-stu-id="1c070-102">How to Create Send Ports for PeopleSoft Enterprise</span></span>
<span data-ttu-id="1c070-103">请按照下列步骤以创建发送端口使用 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1c070-103">Follow these steps to create a send port using BizTalk Server Administration Console.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="1c070-104">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="1c070-104">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="1c070-105">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="1c070-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="1c070-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c070-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="1c070-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="1c070-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="1c070-108">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1c070-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="1c070-109">例如，键入发送端口的名称`SSOSendToPeopleSoft`。</span><span class="sxs-lookup"><span data-stu-id="1c070-109">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="1c070-110">从**类型**下拉列表中，选择**PeopleSoft**。</span><span class="sxs-lookup"><span data-stu-id="1c070-110">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="1c070-111">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="1c070-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="1c070-112">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="1c070-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="1c070-113">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="1c070-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="1c070-114">单击**配置**配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="1c070-114">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="1c070-115">在**PeopleSoft 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1c070-115">In the **PeopleSoft Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="1c070-116">展开**适配器所需属性**，并输入**应用程序服务器路径**， **JAVA_HOME**，**用户名**， **密码**，和连接到 Peoplesoft 系统的 Jar 文件。</span><span class="sxs-lookup"><span data-stu-id="1c070-116">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="1c070-117">您不必设置登录信息。</span><span class="sxs-lookup"><span data-stu-id="1c070-117">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="1c070-118">在列表中选择为表示 PeopleSoft 系统所创建的 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c070-118">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="1c070-119">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="1c070-119">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="1c070-120">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="1c070-120">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="1c070-121">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="1c070-121">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c070-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c070-122">See Also</span></span>  
 [<span data-ttu-id="1c070-123">创建 PeopleSoft 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="1c070-123">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)