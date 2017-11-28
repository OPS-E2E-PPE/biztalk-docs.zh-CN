---
title: "如何配置 HTTP 接收处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- permissions, receive handlers
- configuring [HTTP adapters], permissions
- HTTP adapters, receive handlers
- receive handlers, permissions
- configuring [HTTP adapters], receive handlers
- permissions, HTTP adapters
- receive handlers, HTTP adapters
- HTTP adapters, permissions
ms.assetid: c295489e-dbbb-44f7-bddb-d3cdfe302cf5
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0380804039d45efbe3db06b6fc072a3afb8b6b48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-http-receive-handler"></a><span data-ttu-id="b85c9-102">如何配置 HTTP 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="b85c9-102">How to Configure an HTTP Receive Handler</span></span>
<span data-ttu-id="b85c9-103">使用以下过程来为 HTTP 配置属性接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="b85c9-103">Use the following procedure to configure the properties for an HTTP receive handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b85c9-104">每个主机只能有一个接收与之关联的处理程序。</span><span class="sxs-lookup"><span data-stu-id="b85c9-104">Each host can have only one receive handler associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b85c9-105">HTTP 接收适配器运行独立 BizTalk 主机实例的上下文中。</span><span class="sxs-lookup"><span data-stu-id="b85c9-105">The HTTP receive adapter runs in the context of a BizTalk Isolated Host instance.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b85c9-106">使用 HTTP 或 SOAP 适配器处理程序时，建议在 Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 计算机上安装这些处理程序的主机实例。</span><span class="sxs-lookup"><span data-stu-id="b85c9-106">When using HTTP or SOAP adapter handlers, it is recommended that you install the host instances for these handlers on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computers.</span></span>  
  
### <a name="to-configure-the-general-properties-for-an-http-receive-handler"></a><span data-ttu-id="b85c9-107">若要配置 HTTP 的常规属性接收处理程序</span><span class="sxs-lookup"><span data-stu-id="b85c9-107">To configure the general properties for an HTTP receive handler</span></span>  
  
1.  <span data-ttu-id="b85c9-108">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="b85c9-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="b85c9-109">在展开的适配器列表中，单击**HTTP，**在右窗格中，右键单击你想要配置，，然后单击接收处理程序**属性**。</span><span class="sxs-lookup"><span data-stu-id="b85c9-109">In the expanded adapter list, click **HTTP,** in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="b85c9-110">在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将与之关联的主机。</span><span class="sxs-lookup"><span data-stu-id="b85c9-110">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="b85c9-111">单击**属性**访问**批大小**属性 HTTP 接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="b85c9-111">Click **Properties** to access the **Batch size** property for the HTTP receive handler.</span></span>  
  
5.  <span data-ttu-id="b85c9-112">输入一个介于 1 到 256 和单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b85c9-112">Enter a value from 1 to 256 and click **OK**.</span></span>  
  
6.  <span data-ttu-id="b85c9-113">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b85c9-113">Click **OK**.</span></span>  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="b85c9-114"> 设计的目的在于有效地批处理消息，而不是快速处理单个消息。</span><span class="sxs-lookup"><span data-stu-id="b85c9-114"> is designed to process batches of messages effectively and not to process a single message very quickly.</span></span> <span data-ttu-id="b85c9-115">因此如果此接收处理程序准备用于双向/请求响应接收位置，则可以通过以下这些步骤将延迟时间缩为最短：</span><span class="sxs-lookup"><span data-stu-id="b85c9-115">So if this receive handler is going to be used for two way/request-response receive locations then you can minimize latency by following these steps:</span></span>  
  
-   <span data-ttu-id="b85c9-116">设置**批大小**属性的值为 1。</span><span class="sxs-lookup"><span data-stu-id="b85c9-116">Set the **Batch size** property to a value of 1.</span></span>  
  
-   <span data-ttu-id="b85c9-117">减少**MaxReceiveInterval**从 500 的默认值为小于 100 的值的值**独立消息传送、 XLANG/s，**和**消息传送过程中**服务类。</span><span class="sxs-lookup"><span data-stu-id="b85c9-117">Reduce the **MaxReceiveInterval** value from the default value of 500 to a value less than 100 for the **Messaging Isolated, XLANG/s,** and **Messaging In-Process** service classes.</span></span>  <span data-ttu-id="b85c9-118">进行更改**adm_ServiceClass** BizTalk 管理数据库，其中包含上述每种服务类型的一条记录的表。</span><span class="sxs-lookup"><span data-stu-id="b85c9-118">Changes are made the **adm_ServiceClass** table of the BizTalk Management database, which contains one record for each of these service types.</span></span>  <span data-ttu-id="b85c9-119">更改此设置，因为这是服务类型范围的更改时要格外小心。</span><span class="sxs-lookup"><span data-stu-id="b85c9-119">Use caution when changing this setting because this is a service-type-wide change.</span></span> <span data-ttu-id="b85c9-120">此设置指定最大的轮询间隔时间（以毫秒为单位），[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 消息传送代理会为消息轮询 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="b85c9-120">This setting specifies the maximum polling interval (in milliseconds) at which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messaging agent polls the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Messagebox database for messages.</span></span>  <span data-ttu-id="b85c9-121">阻止控制器还会将其用来决定消息阻止是否在某些加载条件下需要。</span><span class="sxs-lookup"><span data-stu-id="b85c9-121">It also is used by the throttle controller to decide whether message throttling is needed under certain load conditions.</span></span> <span data-ttu-id="b85c9-122">如果需要，根据系统的繁忙情况，阻止控制器会以递增方式延迟消息调度时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b85c9-122">If needed, the throttling controller will incrementally delay the message dispatch interval based upon stress conditions on the system.</span></span> <span data-ttu-id="b85c9-123">在较高吞吐量系统中，将不会使用此设置。</span><span class="sxs-lookup"><span data-stu-id="b85c9-123">In a high throughput system, this setting will not be used.</span></span>  <span data-ttu-id="b85c9-124">但是，如果使用此值，时间间隔将在 MaxReceiveInteral/10 和 MaxReceiveInterval 间发生动态更改。</span><span class="sxs-lookup"><span data-stu-id="b85c9-124">Once this values is used, however, the time interval will dynamically change between MaxReceiveInteral/10 and MaxReceiveInterval.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b85c9-125">更改此设置会影响使用创建的所有主机**主机类型**的**Isolated**。</span><span class="sxs-lookup"><span data-stu-id="b85c9-125">Changing this setting affects all hosts that are created with a **Host Type** of **Isolated**.</span></span>  
  
-   <span data-ttu-id="b85c9-126">重新启动 IIS 应用程序池关联的任何 HTTP 接收已配置的函数。</span><span class="sxs-lookup"><span data-stu-id="b85c9-126">Restart the IIS Application Pool(s) associated with any HTTP receive functions that you have configured.</span></span>  
  
 <span data-ttu-id="b85c9-127">登录帐户**BizTalkServerIsolatedHost**主机实例必须具有读取和写入到临时目录或目录的权限来动态编译使用 HTTP 的代码隐藏文件接收函数。</span><span class="sxs-lookup"><span data-stu-id="b85c9-127">The logon account for the **BizTalkServerIsolatedHost** host instance must have Read and Write permissions to the temp directory or directories to dynamically compile the code-behind files used by the HTTP receive function.</span></span> <span data-ttu-id="b85c9-128">使用以下过程向其授予权限。</span><span class="sxs-lookup"><span data-stu-id="b85c9-128">Use the following procedure to grant permissions.</span></span>  
  
### <a name="to-grant-the-account-for-the-biztalkserverisolatedhost-host-instance-read-and-write-permissions-to-the-temp-directory-of-your-biztalk-server"></a><span data-ttu-id="b85c9-129">向帐户授予的 BizTalkServerIsolatedHost 主机实例将读取和写入到 BizTalk server 的临时目录的权限</span><span class="sxs-lookup"><span data-stu-id="b85c9-129">To grant the account for the BizTalkServerIsolatedHost host instance Read and Write permissions to the temp directory of your BizTalk server</span></span>  
  
1.  <span data-ttu-id="b85c9-130">单击**启动**，单击**运行**，类型**CMD**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="b85c9-130">Click **Start**, click **Run**, type **CMD**, and press ENTER.</span></span>  
  
2.  <span data-ttu-id="b85c9-131">在命令提示符处，键入**设置 TEMP** ，然后按 enter 键以显示与关联的目录**TEMP**环境变量。</span><span class="sxs-lookup"><span data-stu-id="b85c9-131">At the command prompt, type **set TEMP** and press ENTER to display the directory associated with the **TEMP** environment variable.</span></span>  
  
3.  <span data-ttu-id="b85c9-132">在命令提示符处，键入**设置 TMP** ，然后按 enter 键以显示与关联的目录**TMP**环境变量。</span><span class="sxs-lookup"><span data-stu-id="b85c9-132">At the command prompt, type **set TMP** and press ENTER to display the directory associated with the **TMP** environment variable.</span></span>  
  
 <span data-ttu-id="b85c9-133">指定为的登录帐户的帐户授予**BizTalkServerIsolatedHost**托管实例读取和写入权限或多个目录与关联**TEMP**和**TMP**环境变量。</span><span class="sxs-lookup"><span data-stu-id="b85c9-133">Grant the account that is specified as the logon account for the **BizTalkServerIsolatedHost** host instance Read and Write permissions to the directory or directories associated with the **TEMP** and **TMP** environment variables.</span></span> <span data-ttu-id="b85c9-134">若要确定的登录帐户**BizTalkServerIsolatedHost**实例，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，展开**主机实例**，右键单击**BizTalkServerIsolatedHost**主机在右窗格中，实例，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b85c9-134">To determine the logon account for the **BizTalkServerIsolatedHost** instance, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, expand **Host Instances**, right-click the **BizTalkServerIsolatedHost** host instance in the right pane, and then click **Properties**.</span></span> <span data-ttu-id="b85c9-135">用于的主机实例的登录帐户列出旁边**登录**标签。</span><span class="sxs-lookup"><span data-stu-id="b85c9-135">The logon account used for the host instance is listed next to the **Logon** label.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85c9-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b85c9-136">See Also</span></span>  
 [<span data-ttu-id="b85c9-137">配置 HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="b85c9-137">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)