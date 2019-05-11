---
title: 如何使用 Web 服务数组 |Microsoft Docs
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
ms.openlocfilehash: f783c8521d1fbfbf3ffa9297f970ab54e90ce313
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385674"
---
# <a name="how-to-consume-web-service-arrays"></a><span data-ttu-id="34676-102">如何使用 Web 服务数组</span><span class="sxs-lookup"><span data-stu-id="34676-102">How to Consume Web Service Arrays</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="34676-103">可以使用在 BizTalk 业务流程中的 Web services 中公开的数组。</span><span class="sxs-lookup"><span data-stu-id="34676-103">provides the ability to consume arrays that are exposed in Web services from a BizTalk Orchestration.</span></span>  
  
 <span data-ttu-id="34676-104">**若要配置的业务流程，以使用 Web 服务中公开的数组：**</span><span class="sxs-lookup"><span data-stu-id="34676-104">**To configure an Orchestration to consume an array exposed in a Web service:**</span></span>  
  
 <span data-ttu-id="34676-105">确定公开数组的 Web 服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="34676-105">Determine the URL for the Web service that exposes arrays.</span></span> <span data-ttu-id="34676-106">这通常是 asmx Web 页，其中列出了支持 Web 服务的操作。</span><span class="sxs-lookup"><span data-stu-id="34676-106">This is typically an asmx Web page that lists the operations supported by the Web service.</span></span> <span data-ttu-id="34676-107">例如： http://localhost/ArrayWS/ArraySvc.asmx。</span><span class="sxs-lookup"><span data-stu-id="34676-107">For example: http://localhost/ArrayWS/ArraySvc.asmx.</span></span>  
  
1.  <span data-ttu-id="34676-108">在包含您的业务流程的 Visual Studio 项目中添加 Web 引用到此 URL:</span><span class="sxs-lookup"><span data-stu-id="34676-108">Add a Web reference to this URL in the Visual Studio project that contains your orchestration:</span></span>  
  
    -   <span data-ttu-id="34676-109">在解决方案资源管理器，右键单击**引用**，然后单击**添加服务引用**。</span><span class="sxs-lookup"><span data-stu-id="34676-109">In the Solution Explorer, right-click **References**, and click **Add Service Reference**.</span></span>  
  
    -   <span data-ttu-id="34676-110">在中**添加服务引用**对话框中，单击**高级**。</span><span class="sxs-lookup"><span data-stu-id="34676-110">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
    -   <span data-ttu-id="34676-111">在中**服务引用设置**对话框中，单击**添加 Web 引用**中**兼容性**部分。</span><span class="sxs-lookup"><span data-stu-id="34676-111">In the **Service Reference Settings** dialog box, click **Add Web Reference** in the **Compatibility** section.</span></span>  
  
    -   <span data-ttu-id="34676-112">在中**添加 Web 引用**对话框框中，输入到 Web 服务 URL **URL**文本框中，然后单击**转**。</span><span class="sxs-lookup"><span data-stu-id="34676-112">In the **Add Web Reference** dialog box, enter the URL for the Web service into the **URL** text box and then click **Go**.</span></span>  
  
    -   <span data-ttu-id="34676-113">输入 Web 引用的名称**Web 引用名**文本框中，然后单击**添加引用**按钮。</span><span class="sxs-lookup"><span data-stu-id="34676-113">Enter a name for the Web reference into the **Web reference name** text box and click the **Add Reference** button.</span></span>  
  
    -   <span data-ttu-id="34676-114">Web 引用将显示下**Web 引用**在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="34676-114">The Web reference will appear under **Web References** in the Solution Explorer.</span></span>  
  
        > [!TIP]
        >  <span data-ttu-id="34676-115">添加到项目中，Web 引用后**添加 Web 引用**当您右键单击项目名称时，才直接可用命令或**引用**或**的Web引用**.</span><span class="sxs-lookup"><span data-stu-id="34676-115">Once you have a Web reference added to the project, the **Add Web Reference** command is directly available when you right-click the project name or **References** or **Web References**.</span></span>  
  
2.  <span data-ttu-id="34676-116">向业务流程添加 Web 端口：</span><span class="sxs-lookup"><span data-stu-id="34676-116">Add a Web port to your orchestration:</span></span>  
  
    -   <span data-ttu-id="34676-117">拖动**端口**以启动在业务流程设计器中的形状从工具箱拖到一个端口图面**端口配置向导**。</span><span class="sxs-lookup"><span data-stu-id="34676-117">Drag a **Port** shape from the toolbox to one of the port surfaces in the Orchestration Designer to launch the **Port Configuration Wizard**.</span></span> <span data-ttu-id="34676-118">单击**下一步**按钮**端口配置向导**以显示**端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="34676-118">Click the **Next** button in the **Port Configuration Wizard** to display the **Port Properties** dialog.</span></span>  
  
    -   <span data-ttu-id="34676-119">输入一个值**名称**文本框中，用于标识的端口，然后单击**下一步**按钮以显示**选择端口类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="34676-119">Enter a value into the **Name** text box to identify the port, and click the **Next** button to display the **Select a Port Type** dialog.</span></span>  
  
    -   <span data-ttu-id="34676-120">选择选项**使用现有端口类型**，选择 Web 端口类型对应于 Web 引用添加，并单击**下一步**按钮以显示**端口绑定**对话框。</span><span class="sxs-lookup"><span data-stu-id="34676-120">Select the option to **Use an existing Port Type**, select the Web Port type that corresponds to the Web reference you added, and click the **Next** button to display the **Port Binding** dialog.</span></span>  
  
    -   <span data-ttu-id="34676-121">在中**端口绑定**对话框中选择相应**端口绑定**选项，然后单击**下一步**按钮，然后单击**完成**按钮。</span><span class="sxs-lookup"><span data-stu-id="34676-121">In the **Port Binding** dialog select the appropriate **Port binding** option and click the **Next** button, then click the **Finish** button.</span></span> <span data-ttu-id="34676-122">现在应具有包含 Web 服务支持的操作的业务流程设计器中显示的 Web 端口。</span><span class="sxs-lookup"><span data-stu-id="34676-122">You should now have a Web port displayed in the Orchestration Designer that includes the operations supported by the Web service.</span></span>  
  
3.  <span data-ttu-id="34676-123">添加**发送**并**接收**向相应的业务流程的形状：</span><span class="sxs-lookup"><span data-stu-id="34676-123">Add **Send** and **Receive** shapes to your Orchestration as appropriate:</span></span>  
  
    -   <span data-ttu-id="34676-124">拖动**发送**形状从工具箱拖到业务流程设计器图面，若要配置业务流程，以将请求消息发送到 Web 端口中的连接线。</span><span class="sxs-lookup"><span data-stu-id="34676-124">Drag a **Send** shape from the toolbox to a connecting line in the Orchestration Designer surface to configure the orchestration to send a request message to the Web port.</span></span> <span data-ttu-id="34676-125">如果连接**发送**形状添加到其中一个 Web 端口请求消息连接器，BizTalk 将自动创建向此端口发送请求消息时要使用的相应类型的消息。</span><span class="sxs-lookup"><span data-stu-id="34676-125">If you connect the **Send** shape to one of the Web port request message connectors, BizTalk will automatically create a message of the appropriate type to be used when sending a request message to this port.</span></span>  
  
    -   <span data-ttu-id="34676-126">拖动**接收**形状从工具箱拖到业务流程设计器图面，若要配置为接收来自 Web 端口的响应消息的业务流程中的连接线。</span><span class="sxs-lookup"><span data-stu-id="34676-126">Drag a **Receive** shape from the toolbox to a connecting line in the Orchestration Designer surface to configure the orchestration to receive a response message from the Web port.</span></span> <span data-ttu-id="34676-127">如果连接**接收**形状到其中一个 Web 端口响应消息连接器，BizTalk 将自动创建接收来自此端口的响应消息时要使用的相应类型的消息。</span><span class="sxs-lookup"><span data-stu-id="34676-127">If you connect the **Receive** shape to one of the Web port response message connectors, BizTalk will automatically create a message of the appropriate type to be used when receiving a response message from this port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34676-128">使用 SOAP 适配器将消息发送到或从 Web 服务接收消息。</span><span class="sxs-lookup"><span data-stu-id="34676-128">Use the SOAP Adapter to send messages to or receive messages from a Web service.</span></span> <span data-ttu-id="34676-129">有关配置 SOAP 适配器的详细信息请参阅[配置 SOAP 适配器](../core/configuring-the-soap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="34676-129">For more information about configuring the SOAP Adapter see [Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md).</span></span>  
  
 <span data-ttu-id="34676-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程引擎使用一维和交错数组公开的 Web 服务提供支持。</span><span class="sxs-lookup"><span data-stu-id="34676-130">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Orchestration Engine provides support for consuming both one dimensional and jagged arrays that are exposed by Web services.</span></span> <span data-ttu-id="34676-131">如果添加对公开数组的 Web 服务的 Web 引用时，业务流程设计器将生成 Web 消息类型用于描述相应数组。</span><span class="sxs-lookup"><span data-stu-id="34676-131">If you add a Web reference to a Web service that exposes arrays, the Orchestration Designer will generate a Web message type that describes the array.</span></span> <span data-ttu-id="34676-132">然后，您可以发送和接收方式与任何其他消息类似此类型的消息。</span><span class="sxs-lookup"><span data-stu-id="34676-132">You can then send and receive messages of this type like any other message.</span></span> <span data-ttu-id="34676-133">BizTalk Server 不会限制的 Web 消息包含数组到仅 Web 端口发送。</span><span class="sxs-lookup"><span data-stu-id="34676-133">BizTalk Server does not limit the sending of Web messages containing arrays to only Web ports.</span></span>  
  
 <span data-ttu-id="34676-134">有关使用 Web 服务数组的示例，请参阅 SDK 示例"使用 Web 服务"和"使用 Web 服务与数组参数"网址[ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="34676-134">For an example of consuming Web service arrays, see the SDK sample "Consume Web Services" and "Consuming Web Services with Array Parameters" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34676-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="34676-135">See Also</span></span>  
 [<span data-ttu-id="34676-136">在业务流程中使用消息</span><span class="sxs-lookup"><span data-stu-id="34676-136">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)