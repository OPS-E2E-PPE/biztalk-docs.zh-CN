---
title: 如何使用 Web 服务数组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, Web services
- Web services, arrays
- orchestrations, Web services
- orchestrations, Web ports
ms.assetid: 29ecaaed-aa8a-4cf9-a7c8-4b0d6dd412ac
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e78f12405c9c331a888a268d39e2a1520c84fdc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249893"
---
# <a name="how-to-consume-web-service-arrays"></a><span data-ttu-id="bf63b-102">如何使用 Web 服务数组</span><span class="sxs-lookup"><span data-stu-id="bf63b-102">How to Consume Web Service Arrays</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bf63b-103"> 提供了从 BizTalk 业务流程使用在 Web Services 中公开的数组的功能。</span><span class="sxs-lookup"><span data-stu-id="bf63b-103"> provides the ability to consume arrays that are exposed in Web services from a BizTalk Orchestration.</span></span>  
  
 <span data-ttu-id="bf63b-104">**配置业务流程来使用数组中的 Web 服务公开：**</span><span class="sxs-lookup"><span data-stu-id="bf63b-104">**To configure an Orchestration to consume an array exposed in a Web service:**</span></span>  
  
 <span data-ttu-id="bf63b-105">确定公开数组的 Web Services 的 URL。</span><span class="sxs-lookup"><span data-stu-id="bf63b-105">Determine the URL for the Web service that exposes arrays.</span></span> <span data-ttu-id="bf63b-106">它通常是列出了 Web Services 支持的操作的 asmx 网页。</span><span class="sxs-lookup"><span data-stu-id="bf63b-106">This is typically an asmx Web page that lists the operations supported by the Web service.</span></span> <span data-ttu-id="bf63b-107">例如： http://localhost/ArrayWS/ArraySvc.asmx。</span><span class="sxs-lookup"><span data-stu-id="bf63b-107">For example: http://localhost/ArrayWS/ArraySvc.asmx.</span></span>  
  
1.  <span data-ttu-id="bf63b-108">在业务流程所在的 Visual Studio 项目中添加对此 URL 的 Web 引用：</span><span class="sxs-lookup"><span data-stu-id="bf63b-108">Add a Web reference to this URL in the Visual Studio project that contains your orchestration:</span></span>  
  
    -   <span data-ttu-id="bf63b-109">在解决方案资源管理器，右键单击**引用**，然后单击**添加服务引用**。</span><span class="sxs-lookup"><span data-stu-id="bf63b-109">In the Solution Explorer, right-click **References**, and click **Add Service Reference**.</span></span>  
  
    -   <span data-ttu-id="bf63b-110">在**添加服务引用**对话框中，单击**高级**。</span><span class="sxs-lookup"><span data-stu-id="bf63b-110">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
    -   <span data-ttu-id="bf63b-111">在**服务引用设置**对话框中，单击**添加 Web 引用**中**兼容性**部分。</span><span class="sxs-lookup"><span data-stu-id="bf63b-111">In the **Service Reference Settings** dialog box, click **Add Web Reference** in the **Compatibility** section.</span></span>  
  
    -   <span data-ttu-id="bf63b-112">在**添加 Web 引用**对话框框中，输入到 Web 服务的 URL **URL**文本中，然后单击**转**。</span><span class="sxs-lookup"><span data-stu-id="bf63b-112">In the **Add Web Reference** dialog box, enter the URL for the Web service into the **URL** text box and then click **Go**.</span></span>  
  
    -   <span data-ttu-id="bf63b-113">输入到该 Web 引用的名称**Web 引用名称**文本框中，然后单击**添加引用**按钮。</span><span class="sxs-lookup"><span data-stu-id="bf63b-113">Enter a name for the Web reference into the **Web reference name** text box and click the **Add Reference** button.</span></span>  
  
    -   <span data-ttu-id="bf63b-114">Web 引用将出现在**Web 引用**在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="bf63b-114">The Web reference will appear under **Web References** in the Solution Explorer.</span></span>  
  
        > [!TIP]
        >  <span data-ttu-id="bf63b-115">Web 引用添加到项目中，一旦**添加 Web 引用**右键单击项目名称时，命令时直接可用或**引用**或**Web 引用**.</span><span class="sxs-lookup"><span data-stu-id="bf63b-115">Once you have a Web reference added to the project, the **Add Web Reference** command is directly available when you right-click the project name or **References** or **Web References**.</span></span>  
  
2.  <span data-ttu-id="bf63b-116">将 Web 端口添加到您的业务流程：</span><span class="sxs-lookup"><span data-stu-id="bf63b-116">Add a Web port to your orchestration:</span></span>  
  
    -   <span data-ttu-id="bf63b-117">拖动**端口**从工具箱拖到某个端口的形状呈现在业务流程设计器中以启动**端口配置向导**。</span><span class="sxs-lookup"><span data-stu-id="bf63b-117">Drag a **Port** shape from the toolbox to one of the port surfaces in the Orchestration Designer to launch the **Port Configuration Wizard**.</span></span> <span data-ttu-id="bf63b-118">单击**下一步**按钮**端口配置向导**以显示**端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="bf63b-118">Click the **Next** button in the **Port Configuration Wizard** to display the **Port Properties** dialog.</span></span>  
  
    -   <span data-ttu-id="bf63b-119">输入一个值**名称**文本框中，以确定该端口，并单击**下一步**按钮以显示**选择端口类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="bf63b-119">Enter a value into the **Name** text box to identify the port, and click the **Next** button to display the **Select a Port Type** dialog.</span></span>  
  
    -   <span data-ttu-id="bf63b-120">选择该选项以**使用现有的端口类型**，选择 Web 端口类型对应于 Web 引用你添加，并单击**下一步**按钮以显示**端口绑定**对话框。</span><span class="sxs-lookup"><span data-stu-id="bf63b-120">Select the option to **Use an existing Port Type**, select the Web Port type that corresponds to the Web reference you added, and click the **Next** button to display the **Port Binding** dialog.</span></span>  
  
    -   <span data-ttu-id="bf63b-121">在**端口绑定**对话框选择相应**端口绑定**选项，然后单击**下一步**按钮，然后单击**完成**按钮。</span><span class="sxs-lookup"><span data-stu-id="bf63b-121">In the **Port Binding** dialog select the appropriate **Port binding** option and click the **Next** button, then click the **Finish** button.</span></span> <span data-ttu-id="bf63b-122">现在，你应有包括 Web 服务支持的操作的业务流程设计器中显示的 Web 端口。</span><span class="sxs-lookup"><span data-stu-id="bf63b-122">You should now have a Web port displayed in the Orchestration Designer that includes the operations supported by the Web service.</span></span>  
  
3.  <span data-ttu-id="bf63b-123">添加**发送**和**接收**根据您的业务流程的形状：</span><span class="sxs-lookup"><span data-stu-id="bf63b-123">Add **Send** and **Receive** shapes to your Orchestration as appropriate:</span></span>  
  
    -   <span data-ttu-id="bf63b-124">拖动**发送**从工具箱拖到连接线配置业务流程将请求消息发送到 Web 端口的业务流程设计器图面中的形状。</span><span class="sxs-lookup"><span data-stu-id="bf63b-124">Drag a **Send** shape from the toolbox to a connecting line in the Orchestration Designer surface to configure the orchestration to send a request message to the Web port.</span></span> <span data-ttu-id="bf63b-125">如果连接**发送**形状上的与 Web 端口之一请求消息连接器时，BizTalk 将自动创建适当类型的消息，用于将请求消息发送到此端口。</span><span class="sxs-lookup"><span data-stu-id="bf63b-125">If you connect the **Send** shape to one of the Web port request message connectors, BizTalk will automatically create a message of the appropriate type to be used when sending a request message to this port.</span></span>  
  
    -   <span data-ttu-id="bf63b-126">拖动**接收**从工具箱拖到连接线的业务流程设计器图面，配置业务流程，用于从 Web 端口接收响应消息中的形状。</span><span class="sxs-lookup"><span data-stu-id="bf63b-126">Drag a **Receive** shape from the toolbox to a connecting line in the Orchestration Designer surface to configure the orchestration to receive a response message from the Web port.</span></span> <span data-ttu-id="bf63b-127">如果连接**接收**形状 Web 端口响应消息连接器之一，BizTalk 将自动创建适当类型的消息，用于接收来自此端口的响应消息。</span><span class="sxs-lookup"><span data-stu-id="bf63b-127">If you connect the **Receive** shape to one of the Web port response message connectors, BizTalk will automatically create a message of the appropriate type to be used when receiving a response message from this port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf63b-128">使用 SOAP 适配器向 Web Services 发送消息或者接收来自 Web Services 的消息。</span><span class="sxs-lookup"><span data-stu-id="bf63b-128">Use the SOAP Adapter to send messages to or receive messages from a Web service.</span></span> <span data-ttu-id="bf63b-129">有关配置 SOAP 适配器的详细信息请参阅[配置 SOAP 适配器](../core/configuring-the-soap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="bf63b-129">For more information about configuring the SOAP Adapter see [Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md).</span></span>  
  
 <span data-ttu-id="bf63b-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程引擎支持使用由 Web Services 公开的一维和交错数组。</span><span class="sxs-lookup"><span data-stu-id="bf63b-130">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Orchestration Engine provides support for consuming both one dimensional and jagged arrays that are exposed by Web services.</span></span> <span data-ttu-id="bf63b-131">如果添加对公开数组的 Web Services 的 Web 引用，业务流程设计器将生成用于描述相应数组的 Web 消息类型。</span><span class="sxs-lookup"><span data-stu-id="bf63b-131">If you add a Web reference to a Web service that exposes arrays, the Orchestration Designer will generate a Web message type that describes the array.</span></span> <span data-ttu-id="bf63b-132">然后，您就可以像收发任何其他消息一样，收发此种类型的消息。</span><span class="sxs-lookup"><span data-stu-id="bf63b-132">You can then send and receive messages of this type like any other message.</span></span> <span data-ttu-id="bf63b-133">BizTalk Server 并不是只允许将包含数组的 Web 消息发送到 Web 端口。</span><span class="sxs-lookup"><span data-stu-id="bf63b-133">BizTalk Server does not limit the sending of Web messages containing arrays to only Web ports.</span></span>  
  
 <span data-ttu-id="bf63b-134">使用 Web 服务数组的示例，请参阅 SDK 示例"使用 Web 服务"和"使用 Web 服务与数组参数"在[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="bf63b-134">For an example of consuming Web service arrays, see the SDK sample "Consume Web Services" and "Consuming Web Services with Array Parameters" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf63b-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf63b-135">See Also</span></span>  
 [<span data-ttu-id="bf63b-136">在业务流程中使用消息</span><span class="sxs-lookup"><span data-stu-id="bf63b-136">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)