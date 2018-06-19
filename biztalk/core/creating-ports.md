---
title: 创建端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, creating
- receive ports
- creating, send ports
- creating, ports
- Configuration database [BizTalk Server], connecting
- receive ports, creating
- send ports
- send ports, creating
ms.assetid: 4f99f884-5b84-4f9f-8cec-dd5da259ba7f
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d109e102ada04e673fa5eddc3010201b266a150
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015124"
---
# <a name="creating-ports"></a><span data-ttu-id="64d96-102">创建端口</span><span class="sxs-lookup"><span data-stu-id="64d96-102">Creating Ports</span></span>
<span data-ttu-id="64d96-103">使用以下过程可创建单一登录的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="64d96-103">Use the following procedures to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports for Single Sign-on.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="64d96-104">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="64d96-104">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="64d96-105">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="64d96-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="64d96-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="64d96-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="64d96-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="64d96-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="64d96-108">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="64d96-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="64d96-109">例如，键入发送端口的名称`SSOSendToPeopleSoft`。</span><span class="sxs-lookup"><span data-stu-id="64d96-109">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="64d96-110">从**类型**下拉列表中，选择**PeopleSoft**。</span><span class="sxs-lookup"><span data-stu-id="64d96-110">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="64d96-111">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="64d96-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="64d96-112">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="64d96-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="64d96-113">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="64d96-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="64d96-114">单击**配置**配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="64d96-114">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="64d96-115">在**PeopleSoft 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="64d96-115">In the **PeopleSoft Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="64d96-116">展开**适配器所需属性**，并输入**应用程序服务器路径**， **JAVA_HOME**，**用户名**， **密码**，和连接到 Peoplesoft 系统的 Jar 文件。</span><span class="sxs-lookup"><span data-stu-id="64d96-116">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="64d96-117">您不必设置登录信息。</span><span class="sxs-lookup"><span data-stu-id="64d96-117">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="64d96-118">在列表中选择为表示 PeopleSoft 系统所创建的 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="64d96-118">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="64d96-119">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="64d96-119">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="64d96-120">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="64d96-120">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="64d96-121">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="64d96-121">Click **OK**.</span></span>  
  
## <a name="creating-a-receive-port"></a><span data-ttu-id="64d96-122">创建接收端口</span><span class="sxs-lookup"><span data-stu-id="64d96-122">Creating a Receive Port</span></span>  
  
#### <a name="to-create-a-receive-port"></a><span data-ttu-id="64d96-123">若要创建接收端口</span><span class="sxs-lookup"><span data-stu-id="64d96-123">To create a receive port</span></span>  
  
1.  <span data-ttu-id="64d96-124">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="64d96-124">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="64d96-125">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="64d96-125">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="64d96-126">在**接收端口属性**窗口，请在**常规**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="64d96-126">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="64d96-127">在**名称**字段中，键入`ReceiveFromTIBCOEMS`。</span><span class="sxs-lookup"><span data-stu-id="64d96-127">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="64d96-128">在**身份验证**组框中，指定使用身份验证时处理消息的方式。</span><span class="sxs-lookup"><span data-stu-id="64d96-128">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="64d96-129">选择**启用路由失败消息**复选框。</span><span class="sxs-lookup"><span data-stu-id="64d96-129">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="64d96-130">上**接收位置**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="64d96-130">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="64d96-131">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="64d96-131">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="64d96-132">在**接收位置**窗口，请在**常规**页上，键入**名称**的接收位置。</span><span class="sxs-lookup"><span data-stu-id="64d96-132">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="64d96-133">从**类型**下拉列表中，选择传输类型，并从**接收处理程序**下拉列表中，选择的传输地址。</span><span class="sxs-lookup"><span data-stu-id="64d96-133">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="64d96-134">从**接收管道**下拉列表中，选择接收管道。</span><span class="sxs-lookup"><span data-stu-id="64d96-134">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="64d96-135">上**计划**页上，选择**开始日期**和**结束日期**限制接收的文档。</span><span class="sxs-lookup"><span data-stu-id="64d96-135">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="64d96-136">选择**启用服务窗口**复选框。</span><span class="sxs-lookup"><span data-stu-id="64d96-136">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="64d96-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="64d96-137">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="64d96-138">上**入站映射**页上，选择转换所选的端口上的文档的入站的映射。</span><span class="sxs-lookup"><span data-stu-id="64d96-138">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="64d96-139">上**跟踪**页上，选择所需的跟踪消息正文和跟踪消息属性。</span><span class="sxs-lookup"><span data-stu-id="64d96-139">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="64d96-140">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="64d96-140">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d96-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64d96-141">See Also</span></span>  
 [<span data-ttu-id="64d96-142">安全适配器</span><span class="sxs-lookup"><span data-stu-id="64d96-142">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)