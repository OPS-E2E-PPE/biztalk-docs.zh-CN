---
title: 创建发送和接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 808c3d7295031832852ca40596a77a369aedb507
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353578"
---
# <a name="creating-send-and-receive-ports"></a><span data-ttu-id="c74a8-102">创建发送和接收端口</span><span class="sxs-lookup"><span data-stu-id="c74a8-102">Creating Send and Receive Ports</span></span>
<span data-ttu-id="c74a8-103">使用以下过程创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送和接收端口的 BizTalk 适配器用于 JD Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="c74a8-103">Use the following procedures to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports for BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="creating-a-port"></a><span data-ttu-id="c74a8-104">创建端口</span><span class="sxs-lookup"><span data-stu-id="c74a8-104">Creating a Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="c74a8-105">若要创建的发送端口</span><span class="sxs-lookup"><span data-stu-id="c74a8-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="c74a8-106">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c74a8-107">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开要为其创建发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c74a8-107">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="c74a8-108">右键单击**发送端口**然后单击**新建**，然后单击**静态要求响应端口**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-108">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="c74a8-109">在中**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c74a8-109">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="c74a8-110">在中**名称**框中，键入发送端口名称 (例如， `SSOSendToJDE OneWorld`)。</span><span class="sxs-lookup"><span data-stu-id="c74a8-110">In the **Name** box, type a send port name (for example, `SSOSendToJDE OneWorld`).</span></span>  
  
    -   <span data-ttu-id="c74a8-111">从**类型**下拉列表中，选择**JDEdwards**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-111">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="c74a8-112">从**发送处理程序**下拉列表中，选择发送处理程序地址。</span><span class="sxs-lookup"><span data-stu-id="c74a8-112">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
    -   <span data-ttu-id="c74a8-113">有关**发送管道**，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-113">For the **Send Pipeline**, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    -   <span data-ttu-id="c74a8-114">有关**接收管道**，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-114">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
5.  <span data-ttu-id="c74a8-115">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="c74a8-115">Click **OK**.</span></span>  
  
## <a name="creating-a-receive-port"></a><span data-ttu-id="c74a8-116">创建接收端口</span><span class="sxs-lookup"><span data-stu-id="c74a8-116">Creating a Receive Port</span></span>  
  
#### <a name="to-create-a-receive-port"></a><span data-ttu-id="c74a8-117">若要创建的接收端口</span><span class="sxs-lookup"><span data-stu-id="c74a8-117">To create a receive port</span></span>  
  
1.  <span data-ttu-id="c74a8-118">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-118">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c74a8-119">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开要为其创建发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c74a8-119">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="c74a8-120">右键单击**接收端口**然后单击**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-120">Right-click **Receive Ports** and click **New**, and then click **One-way Receive Port**.</span></span>  
  
     <span data-ttu-id="c74a8-121">上**单向接收端口属性**屏幕上，在**名称**字段中，键入`ReceiveFromHttp`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-121">On the **One-Way Receive Port Properties** screen, in the **Name** field, type `ReceiveFromHttp`, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="c74a8-122">输入中的以下信息**单向接收端口属性**窗口：</span><span class="sxs-lookup"><span data-stu-id="c74a8-122">Enter the following information in the **One-way Receive Port Properties** window:</span></span>  
  
    -   <span data-ttu-id="c74a8-123">在中**名称**字段中，键入`ReceiveFromHTTP`。</span><span class="sxs-lookup"><span data-stu-id="c74a8-123">In the **Name** field, type `ReceiveFromHTTP`.</span></span>  
  
    -   <span data-ttu-id="c74a8-124">有关**传输类型**，选择**HTTP**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-124">For the **Transport Type**, select **HTTP**.</span></span>  
  
5.  <span data-ttu-id="c74a8-125">单击地址 (URI) 中的省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="c74a8-125">Click the ellipsis (…) button in the address (URI).</span></span>  
  
     <span data-ttu-id="c74a8-126">![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")</span><span class="sxs-lookup"><span data-stu-id="c74a8-126">![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")</span></span>  
  
    1.  <span data-ttu-id="c74a8-127">设置虚拟目录和 ISAPI 扩展 /myssodemo/btshttpreceive.dll。</span><span class="sxs-lookup"><span data-stu-id="c74a8-127">Set the Virtual directory plus ISAPI extension, /mySSODemo/BTSHTTPReceive.dll.</span></span>  
  
    2.  <span data-ttu-id="c74a8-128">选择**成功后的返回相关句柄**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-128">Select **Return correlation handle on success**.</span></span>  
  
    3.  <span data-ttu-id="c74a8-129">选择**使用单一登录**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-129">Select **Use Single Sign-On**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="c74a8-130">在中**接收处理程序**下拉列表中，选择**BizTalkServerIsolatedHost**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-130">In the **Receive Handler** drop-down list, select **BizTalkServerIsolatedHost**.</span></span>  
  
     <span data-ttu-id="c74a8-131">![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")</span><span class="sxs-lookup"><span data-stu-id="c74a8-131">![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")</span></span>  
  
7.  <span data-ttu-id="c74a8-132">有关**接收管道**，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c74a8-132">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c74a8-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="c74a8-133">See Also</span></span>  
 <span data-ttu-id="c74a8-134">[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="c74a8-134">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 <span data-ttu-id="c74a8-135">[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="c74a8-135">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="c74a8-136">适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="c74a8-136">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)