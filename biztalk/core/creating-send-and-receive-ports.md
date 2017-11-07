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
ms.openlocfilehash: da4b117ca2d032ef1dc10731128acca903a51790
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="creating-send-and-receive-ports"></a><span data-ttu-id="8566c-102">创建发送和接收端口</span><span class="sxs-lookup"><span data-stu-id="8566c-102">Creating Send and Receive Ports</span></span>
<span data-ttu-id="8566c-103">使用以下过程为用于 JD Edwards OneWorld 的 BizTalk 适配器创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="8566c-103">Use the following procedures to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports for BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="creating-a-port"></a><span data-ttu-id="8566c-104">创建端口</span><span class="sxs-lookup"><span data-stu-id="8566c-104">Creating a Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="8566c-105">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="8566c-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="8566c-106">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="8566c-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="8566c-107">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开你想要创建发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8566c-107">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="8566c-108">右键单击**发送端口**单击**新建**，然后单击**静态请求-响应端口**。</span><span class="sxs-lookup"><span data-stu-id="8566c-108">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="8566c-109">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8566c-109">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="8566c-110">在**名称**框中，键入发送端口名称 (例如， `SSOSendToJDE OneWorld`)。</span><span class="sxs-lookup"><span data-stu-id="8566c-110">In the **Name** box, type a send port name (for example, `SSOSendToJDE OneWorld`).</span></span>  
  
    -   <span data-ttu-id="8566c-111">从**类型**下拉列表中，选择**JDEdwards**。</span><span class="sxs-lookup"><span data-stu-id="8566c-111">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="8566c-112">从**发送处理程序**下拉列表中，选择发送处理程序地址。</span><span class="sxs-lookup"><span data-stu-id="8566c-112">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
    -   <span data-ttu-id="8566c-113">有关**发送管道**，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="8566c-113">For the **Send Pipeline**, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    -   <span data-ttu-id="8566c-114">有关**接收管道**，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="8566c-114">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
5.  <span data-ttu-id="8566c-115">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8566c-115">Click **OK**.</span></span>  
  
## <a name="creating-a-receive-port"></a><span data-ttu-id="8566c-116">创建接收端口</span><span class="sxs-lookup"><span data-stu-id="8566c-116">Creating a Receive Port</span></span>  
  
#### <a name="to-create-a-receive-port"></a><span data-ttu-id="8566c-117">若要创建接收端口</span><span class="sxs-lookup"><span data-stu-id="8566c-117">To create a receive port</span></span>  
  
1.  <span data-ttu-id="8566c-118">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="8566c-118">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="8566c-119">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开你想要创建发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8566c-119">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="8566c-120">右键单击**接收端口**单击**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="8566c-120">Right-click **Receive Ports** and click **New**, and then click **One-way Receive Port**.</span></span>  
  
     <span data-ttu-id="8566c-121">上**单向接收端口属性**屏幕上，在**名称**字段中，键入`ReceiveFromHttp`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8566c-121">On the **One-Way Receive Port Properties** screen, in the **Name** field, type `ReceiveFromHttp`, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="8566c-122">输入中的以下信息**单向接收端口属性**窗口：</span><span class="sxs-lookup"><span data-stu-id="8566c-122">Enter the following information in the **One-way Receive Port Properties** window:</span></span>  
  
    -   <span data-ttu-id="8566c-123">在**名称**字段中，键入`ReceiveFromHTTP`。</span><span class="sxs-lookup"><span data-stu-id="8566c-123">In the **Name** field, type `ReceiveFromHTTP`.</span></span>  
  
    -   <span data-ttu-id="8566c-124">有关**传输类型**，选择**HTTP**。</span><span class="sxs-lookup"><span data-stu-id="8566c-124">For the **Transport Type**, select **HTTP**.</span></span>  
  
5.  <span data-ttu-id="8566c-125">在地址 (URI) 中单击省略号 (…) 按钮。</span><span class="sxs-lookup"><span data-stu-id="8566c-125">Click the ellipsis (…) button in the address (URI).</span></span>  
  
     ![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")  
  
    1.  <span data-ttu-id="8566c-126">设置虚拟目录和 ISAPI 扩展 /mySSODemo/BTSHTTPReceive.dll。</span><span class="sxs-lookup"><span data-stu-id="8566c-126">Set the Virtual directory plus ISAPI extension, /mySSODemo/BTSHTTPReceive.dll.</span></span>  
  
    2.  <span data-ttu-id="8566c-127">选择**成功后返回的相关句柄**。</span><span class="sxs-lookup"><span data-stu-id="8566c-127">Select **Return correlation handle on success**.</span></span>  
  
    3.  <span data-ttu-id="8566c-128">选择**使用单一登录**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8566c-128">Select **Use Single Sign-On**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="8566c-129">在**接收处理程序**下拉列表中，选择**BizTalkServerIsolatedHost**。</span><span class="sxs-lookup"><span data-stu-id="8566c-129">In the **Receive Handler** drop-down list, select **BizTalkServerIsolatedHost**.</span></span>  
  
     ![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")  
  
7.  <span data-ttu-id="8566c-130">有关**接收管道**，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8566c-130">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8566c-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8566c-131">See Also</span></span>  
 <span data-ttu-id="8566c-132">[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="8566c-132">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 <span data-ttu-id="8566c-133">[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="8566c-133">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="8566c-134">适配器中的安全</span><span class="sxs-lookup"><span data-stu-id="8566c-134">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)