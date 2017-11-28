---
title: "创建发送和接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, receive ports
- adapters [JD Edwards OneWorld adapters], receive ports
- creating, receive ports [JD Edwards OneWorld adapters]
- send ports, creating [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], send ports
- adapters [JD Edwards OneWorld adapters], transport properties
- JD Edwards OneWorld adapters, send ports
- JD Edwards OneWorld adapters, transport properties
- receive ports, creating [JD Edwards OneWorld adapters]
- creating, send ports [JD Edwards OneWorld adapters]
ms.assetid: fb4ca8b1-40d9-4beb-a791-554086f8ca98
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 217a1d79dc4079c8f092985e00a1cd5636788e7b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-send-and-receive-ports"></a><span data-ttu-id="b2151-102">创建发送和接收端口</span><span class="sxs-lookup"><span data-stu-id="b2151-102">Creating Send and Receive Ports</span></span>
<span data-ttu-id="b2151-103">使用以下过程为用于 JD Edwards OneWorld 的 BizTalk 适配器创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="b2151-103">Use the following procedures to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports for BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="creating-a-port"></a><span data-ttu-id="b2151-104">创建端口</span><span class="sxs-lookup"><span data-stu-id="b2151-104">Creating a Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="b2151-105">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="b2151-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="b2151-106">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="b2151-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b2151-107">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开你想要创建发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2151-107">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="b2151-108">右键单击**发送端口**单击**新建**，然后单击**静态请求-响应端口**。</span><span class="sxs-lookup"><span data-stu-id="b2151-108">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="b2151-109">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b2151-109">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="b2151-110">在**名称**框中，键入发送端口名称 (例如， `SSOSendToJDE OneWorld`)。</span><span class="sxs-lookup"><span data-stu-id="b2151-110">In the **Name** box, type a send port name (for example, `SSOSendToJDE OneWorld`).</span></span>  
  
    -   <span data-ttu-id="b2151-111">从**类型**下拉列表中，选择**JDEdwards**。</span><span class="sxs-lookup"><span data-stu-id="b2151-111">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="b2151-112">从**发送处理程序**下拉列表中，选择发送处理程序地址。</span><span class="sxs-lookup"><span data-stu-id="b2151-112">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
    -   <span data-ttu-id="b2151-113">有关**发送管道**，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="b2151-113">For the **Send Pipeline**, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    -   <span data-ttu-id="b2151-114">有关**接收管道**，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="b2151-114">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
5.  <span data-ttu-id="b2151-115">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b2151-115">Click **OK**.</span></span>  
  
## <a name="creating-a-receive-port"></a><span data-ttu-id="b2151-116">创建接收端口</span><span class="sxs-lookup"><span data-stu-id="b2151-116">Creating a Receive Port</span></span>  
  
#### <a name="to-create-a-receive-port"></a><span data-ttu-id="b2151-117">若要创建接收端口</span><span class="sxs-lookup"><span data-stu-id="b2151-117">To create a receive port</span></span>  
  
1.  <span data-ttu-id="b2151-118">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="b2151-118">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b2151-119">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开你想要创建发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2151-119">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="b2151-120">右键单击**接收端口**单击**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="b2151-120">Right-click **Receive Ports** and click **New**, and then click **One-way Receive Port**.</span></span>  
  
     <span data-ttu-id="b2151-121">上**单向接收端口属性**屏幕上，在**名称**字段中，键入`ReceiveFromHttp`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2151-121">On the **One-Way Receive Port Properties** screen, in the **Name** field, type `ReceiveFromHttp`, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="b2151-122">输入中的以下信息**单向接收端口属性**窗口：</span><span class="sxs-lookup"><span data-stu-id="b2151-122">Enter the following information in the **One-way Receive Port Properties** window:</span></span>  
  
    -   <span data-ttu-id="b2151-123">在**名称**字段中，键入`ReceiveFromHTTP`。</span><span class="sxs-lookup"><span data-stu-id="b2151-123">In the **Name** field, type `ReceiveFromHTTP`.</span></span>  
  
    -   <span data-ttu-id="b2151-124">有关**传输类型**，选择**HTTP**。</span><span class="sxs-lookup"><span data-stu-id="b2151-124">For the **Transport Type**, select **HTTP**.</span></span>  
  
5.  <span data-ttu-id="b2151-125">在地址 (URI) 中单击省略号 (…) 按钮。</span><span class="sxs-lookup"><span data-stu-id="b2151-125">Click the ellipsis (…) button in the address (URI).</span></span>  
  
     ![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")  
  
    1.  <span data-ttu-id="b2151-126">设置虚拟目录和 ISAPI 扩展 /mySSODemo/BTSHTTPReceive.dll。</span><span class="sxs-lookup"><span data-stu-id="b2151-126">Set the Virtual directory plus ISAPI extension, /mySSODemo/BTSHTTPReceive.dll.</span></span>  
  
    2.  <span data-ttu-id="b2151-127">选择**成功后返回的相关句柄**。</span><span class="sxs-lookup"><span data-stu-id="b2151-127">Select **Return correlation handle on success**.</span></span>  
  
    3.  <span data-ttu-id="b2151-128">选择**使用单一登录**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2151-128">Select **Use Single Sign-On**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="b2151-129">在**接收处理程序**下拉列表中，选择**BizTalkServerIsolatedHost**。</span><span class="sxs-lookup"><span data-stu-id="b2151-129">In the **Receive Handler** drop-down list, select **BizTalkServerIsolatedHost**.</span></span>  
  
     ![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")  
  
7.  <span data-ttu-id="b2151-130">有关**接收管道**，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2151-130">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2151-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2151-131">See Also</span></span>  
 <span data-ttu-id="b2151-132">[创建博士 Edwards OneWorld 发送处理程序](../core/creating-jd-edwards-oneworld-send-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="b2151-132">[Creating JD Edwards OneWorld Send Handlers](../core/creating-jd-edwards-oneworld-send-handlers.md) </span></span>  
 <span data-ttu-id="b2151-133">[如何设置博士 Edwards OneWorld 传输属性](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b2151-133">[How to Set JD Edwards OneWorld Transport Properties](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span></span>  
 [<span data-ttu-id="b2151-134">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="b2151-134">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)