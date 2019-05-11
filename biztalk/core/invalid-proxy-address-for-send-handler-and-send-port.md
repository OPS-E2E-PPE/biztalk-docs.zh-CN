---
title: 无效的代理地址 （用于发送处理程序和发送端口） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccedd23e-7d44-4419-b519-e04511e1f176
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdfa5951ed261d3e8bd63811764595d1b7e3858c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330621"
---
# <a name="invalid-proxy-address-for-send-handler-and-send-port"></a><span data-ttu-id="2d397-102">无效的代理地址 （用于发送处理程序和发送端口）</span><span class="sxs-lookup"><span data-stu-id="2d397-102">Invalid proxy address (for send handler and send port)</span></span>
## <a name="details"></a><span data-ttu-id="2d397-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2d397-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="2d397-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2d397-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="2d397-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="2d397-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="2d397-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2d397-106">Event ID</span></span>     |                                         <span data-ttu-id="2d397-107">0</span><span class="sxs-lookup"><span data-stu-id="2d397-107">0</span></span>                                          |
|  <span data-ttu-id="2d397-108">事件源</span><span class="sxs-lookup"><span data-stu-id="2d397-108">Event Source</span></span>   |                                         <span data-ttu-id="2d397-109">0</span><span class="sxs-lookup"><span data-stu-id="2d397-109">0</span></span>                                          |
|    <span data-ttu-id="2d397-110">组件</span><span class="sxs-lookup"><span data-stu-id="2d397-110">Component</span></span>    |                                         <span data-ttu-id="2d397-111">0</span><span class="sxs-lookup"><span data-stu-id="2d397-111">0</span></span>                                          |
|  <span data-ttu-id="2d397-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="2d397-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="2d397-113">0</span><span class="sxs-lookup"><span data-stu-id="2d397-113">0</span></span>                                          |
|  <span data-ttu-id="2d397-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="2d397-114">Message Text</span></span>   |                             <span data-ttu-id="2d397-115">无效的代理地址： {0}</span><span class="sxs-lookup"><span data-stu-id="2d397-115">Invalid proxy address: {0}</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="2d397-116">解释</span><span class="sxs-lookup"><span data-stu-id="2d397-116">Explanation</span></span>  
 <span data-ttu-id="2d397-117">未提供 WCF 发送处理程序或 WCF 发送端口使用有效的代理地址。</span><span class="sxs-lookup"><span data-stu-id="2d397-117">You did not provide a WCF send handler or a WCF send port with a valid proxy address.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2d397-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="2d397-118">User Action</span></span>  
 <span data-ttu-id="2d397-119">使用以下过程来配置代理地址。</span><span class="sxs-lookup"><span data-stu-id="2d397-119">Use the following procedure to configure a proxy address.</span></span>  
  
#### <a name="to-configure-a-proxy-address"></a><span data-ttu-id="2d397-120">若要配置的代理地址</span><span class="sxs-lookup"><span data-stu-id="2d397-120">To configure a proxy address</span></span>  
  
1. <span data-ttu-id="2d397-121">单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="2d397-121">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="2d397-122">在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="2d397-122">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="2d397-123">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="2d397-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="2d397-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="2d397-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="2d397-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="2d397-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="2d397-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="2d397-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="2d397-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="2d397-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="2d397-128">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**代理**选项卡。</span><span class="sxs-lookup"><span data-stu-id="2d397-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Proxy** tab.</span></span>  
  
9. <span data-ttu-id="2d397-129">验证中的代理地址**代理设置**部分已正确配置。</span><span class="sxs-lookup"><span data-stu-id="2d397-129">Verify that the proxy address in the **Proxy settings** section is configured properly.</span></span>  
  
   <span data-ttu-id="2d397-130">发送端口和发送处理程序的其他信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="2d397-130">For additional information on send ports and send handlers, see the following resources:</span></span>  
  
-   [<span data-ttu-id="2d397-131">如何配置 Wcf-wshttp 发送端口</span><span class="sxs-lookup"><span data-stu-id="2d397-131">How to Configure a WCF-WSHttp Send Port</span></span>](../core/how-to-configure-a-wcf-wshttp-send-port.md)  
  
-   [<span data-ttu-id="2d397-132">如何配置 Wcf-basichttp 发送端口</span><span class="sxs-lookup"><span data-stu-id="2d397-132">How to Configure a WCF-BasicHttp Send Port</span></span>](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)  
  
-   [<span data-ttu-id="2d397-133">如何配置 wcf-basichttp: Wcf-basichttp 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="2d397-133">How to Configure a WCF-BasicHttp Send Handler</span></span>](http://msdn.microsoft.com/library/18dcc616-4732-42f8-bd64-e55a5ebbaa49)  
  
-   [<span data-ttu-id="2d397-134">如何配置 Wcf-wshttp 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="2d397-134">How to Configure a WCF-WSHttp Send Handler</span></span>](../core/how-to-configure-a-wcf-wshttp-send-handler.md)  
  
-   [<span data-ttu-id="2d397-135">如何配置 Wcf-custom 发送端口</span><span class="sxs-lookup"><span data-stu-id="2d397-135">How to Configure a WCF-Custom Send Port</span></span>](../core/how-to-configure-a-wcf-custom-send-port.md)