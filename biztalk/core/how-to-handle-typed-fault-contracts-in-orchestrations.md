---
title: "如何处理类型化的错误协定在业务流程中 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typed fault contracts [orchestrations]
- WCF services, orchestrations
- orchestrations, typed fault contracts
- orchestrations, WCF services
ms.assetid: 5a1a7d22-b0ff-4d09-bebf-4995229784b0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89de313960324ea39ffc8e4eaa4905849dc38b8a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-handle-typed-fault-contracts-in-orchestrations"></a><span data-ttu-id="60623-102">如何在业务流程中处理类型化错误协定</span><span class="sxs-lookup"><span data-stu-id="60623-102">How to Handle Typed Fault Contracts in Orchestrations</span></span>
<span data-ttu-id="60623-103">本主题介绍从业务流程内部使用 WCF 服务时应如何处理类型化错误协定。</span><span class="sxs-lookup"><span data-stu-id="60623-103">This topic describes how to handle typed fault contracts when consuming WCF services from within orchestrations.</span></span> <span data-ttu-id="60623-104">若要处理在业务流程中的类型化的错误异常，你使用的 WCF 服务必须具有**FaultContractAttribute**应用于服务操作; 因此，可以通过使用引发错误**FaultException**\<T > T 可在其中的任何有效的数据协定或通过 WCF 服务的可序列化类型。</span><span class="sxs-lookup"><span data-stu-id="60623-104">To handle typed fault exceptions in orchestrations, the WCF services that you are consuming must have the **FaultContractAttribute** applied to the service operations; therefore, the faults can be thrown by using **FaultException**\<T> where T can be any valid data contract or serializable type from the WCF services.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="60623-105">过程</span><span class="sxs-lookup"><span data-stu-id="60623-105">Procedures</span></span>  
  
#### <a name="to-handle-typed-fault-contracts-in-orchestrations"></a><span data-ttu-id="60623-106">若要处理在业务流程中的类型化的错误协定</span><span class="sxs-lookup"><span data-stu-id="60623-106">To handle typed fault contracts in orchestrations</span></span>  
  
1.  <span data-ttu-id="60623-107">在你的 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目，请在解决方案资源管理器，右键单击你的项目，单击**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="60623-107">In your Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, in Solution Explorer, right-click your project, click **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="60623-108">在**添加生成的项的\<** *项目名称* **>** 对话框中，在**模板**部分中，选择**使用 WCF 服务**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="60623-108">In the **Add Generated Items - \<***Project name***>** dialog box, in the **Templates** section, select **Consume WCF Service**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="60623-109">上**欢迎 BizTalk WCF 服务使用向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="60623-109">On the **Welcome to the BizTalk WCF Service Consuming Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="60623-110">上**元数据源**页上，选择**元数据交换 (MEX) 终结点**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="60623-110">On the **Metadata source** page, select **Metadata Exchange (MEX) endpoint**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="60623-111">上**元数据终结点**页上，指定正在运行的服务，通过 WS 元数据交换或 Http Get 的下载可提供元数据的 URL — 例如，http://localhost:8005。</span><span class="sxs-lookup"><span data-stu-id="60623-111">On the **Metadata Endpoint** page, specify the URL for the running service that provides metadata for download through WS-Metadata Exchange or Http-Get—for example, http://localhost:8005.</span></span> <span data-ttu-id="60623-112">若要从 URL 中获取的元数据文档，请单击**获取**。</span><span class="sxs-lookup"><span data-stu-id="60623-112">To get the metadata document from the URL, click **Get**.</span></span> <span data-ttu-id="60623-113">如果正在运行的服务要求具有基本身份验证方案的用户凭据，请单击**编辑**以打开**BizTalk WCF 服务使用向导**对话框中，你可以在其中提供的用户名和访问正在运行的服务时要使用的密码。</span><span class="sxs-lookup"><span data-stu-id="60623-113">If the running service requires a user credential with the basic authentication scheme, click **Edit** to open the **BizTalk WCF Service Consuming Wizard** dialog box in which you can supply the user name and password to use when accessing the running service.</span></span> <span data-ttu-id="60623-114">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="60623-114">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="60623-115">上**导入 WCF 服务元数据摘要**页上，查看你的设置。</span><span class="sxs-lookup"><span data-stu-id="60623-115">On the **Import WCF Service Metadata Summary** page, review your settings.</span></span> <span data-ttu-id="60623-116">你可以单击**回**需进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="60623-116">You can click **Back** to make any changes.</span></span> <span data-ttu-id="60623-117">然后单击**导入**创建 BizTalk 项目和要用于使用 WCF 服务的类型。</span><span class="sxs-lookup"><span data-stu-id="60623-117">Then click **Import** to create the BizTalk artifacts and types to be used for consuming the WCF service.</span></span>  
  
7.  <span data-ttu-id="60623-118">上**完成 BizTalk WCF 服务使用向导**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="60623-118">On the **Completing the BizTalk WCF Service Consuming Wizard** page, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="60623-119">假设您正在使用的 WCF 服务引发以下错误异常：</span><span class="sxs-lookup"><span data-stu-id="60623-119">Suppose that the WCF service that you are consuming throws the following fault exception:</span></span>  
  
    ```  
    throw new FaultException<MyOperationException>(divideException);  
    ```  
  
     <span data-ttu-id="60623-120">发送端口上的错误操作需要类型的消息的**MyOperationException**，但 WCF 响应消息包含整个错误正文。</span><span class="sxs-lookup"><span data-stu-id="60623-120">The fault operation on the send port expects a message of type **MyOperationException**, but the WCF response message contains the whole fault body.</span></span> <span data-ttu-id="60623-121">因此，你需要提取**MyOperationException**一部分从通过配置消息**入站 BizTalk 消息正文**传输的属性对话框中的选项。</span><span class="sxs-lookup"><span data-stu-id="60623-121">Therefore, you need to extract the **MyOperationException** part from the message by configuring the **Inbound BizTalk message body** option in the transport properties dialog box.</span></span> <span data-ttu-id="60623-122">例如：</span><span class="sxs-lookup"><span data-stu-id="60623-122">For example,</span></span>  
  
    -   <span data-ttu-id="60623-123">选择**路径--由正文路径定位的内容**。</span><span class="sxs-lookup"><span data-stu-id="60623-123">Select **Path -- content located by body path**.</span></span>  
  
    -   <span data-ttu-id="60623-124">设置正文路径表达式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="60623-124">Set the Body path expression to the following:</span></span>  
  
        ```  
        /*[local-name()='Fault']/*[local-name()='Detail']/* | /*[local-name()='DivideResponse']  
        ```  
  
    -   <span data-ttu-id="60623-125">选择**Xml**从**节点编码**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="60623-125">Select **Xml** from the **Node encoding** drop-down list.</span></span>  
  
9. <span data-ttu-id="60623-126">在业务流程中，您需要添加一个作用域和两个异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="60623-126">In the orchestration, you will need to add a scope and two exception handlers.</span></span> <span data-ttu-id="60623-127">一个异常处理程序是错误的操作，类似于**MyOperationException**显示在前面的示例; 其他异常处理程序是用于捕获泛型**SOAPExceptions**。</span><span class="sxs-lookup"><span data-stu-id="60623-127">One exception handler is for the Fault operation, similar to **MyOperationException** shown in the preceding example; the other exception handler is for catching generic **SOAPExceptions**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60623-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60623-128">See Also</span></span>  
 <span data-ttu-id="60623-129">[如何从作为 WCF 服务发布的业务流程引发错误异常](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="60623-129">[How to Throw Fault Exceptions from Orchestrations Published as WCF Services](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md) </span></span>  
 [<span data-ttu-id="60623-130">如何通过 BizTalk WCF 服务使用向导来使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="60623-130">How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service</span></span>](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)