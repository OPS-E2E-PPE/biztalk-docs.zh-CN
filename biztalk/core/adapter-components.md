---
title: "适配器组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 383e8bcb-2b4d-40f9-9e98-f49e8d6f30f7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2a5f2a78a9ea555d22f585c0aa50eda65b6c287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-components"></a><span data-ttu-id="349c7-102">适配器组件</span><span class="sxs-lookup"><span data-stu-id="349c7-102">Adapter Components</span></span>
<span data-ttu-id="349c7-103">自定义适配器共享本地适配器所使用的标准配置、管理和设置机制。</span><span class="sxs-lookup"><span data-stu-id="349c7-103">A custom adapter shares the standardized configuration, management, and setup mechanisms used by the native adapters.</span></span> <span data-ttu-id="349c7-104">为适配器框架标准化，自定义适配器通过使用进行管理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="349c7-104">With the standardization to the Adapter Framework, a custom adapter is managed by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="349c7-105">下图显示的自定义适配器的主要组件： 适配器注册表文件、 适配器设计时组件和适配器运行时组件。</span><span class="sxs-lookup"><span data-stu-id="349c7-105">The following figure shows the main components of a custom adapter: the adapter registry file, the adapter design-time component, and the adapter run-time component.</span></span>  
  
 ![](../core/media/elementsofanadapter.gif "ElementsOfAnAdapter")  
  
## <a name="adapter-registry-file"></a><span data-ttu-id="349c7-106">适配器注册表文件</span><span class="sxs-lookup"><span data-stu-id="349c7-106">Adapter Registry File</span></span>  
 <span data-ttu-id="349c7-107">有关适配器的特定信息必须在注册表和 BizTalk 管理数据库中注册。</span><span class="sxs-lookup"><span data-stu-id="349c7-107">Certain information about adapters must be registered in the registry and the BizTalk Management database.</span></span> <span data-ttu-id="349c7-108">适配器别名、接收处理程序、接收位置和传输类型之类的信息被称为元数据。</span><span class="sxs-lookup"><span data-stu-id="349c7-108">Information such as an adapter's alias, receive hander, receive location, and transport type is called metadata.</span></span> <span data-ttu-id="349c7-109">这些元数据项创建在过程中手动适配器注册使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="349c7-109">These metadata entries are created during manual adapter registration using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="349c7-110">或者，你可以运行适配器注册表向导 (AdapterRegistryWizard.exe) SDK 实用程序生成自定义适配器注册表文件。</span><span class="sxs-lookup"><span data-stu-id="349c7-110">Alternatively, you can run the Adapter Registry Wizard (AdapterRegistryWizard.exe) SDK utility to generate a registry file for your custom adapter.</span></span> <span data-ttu-id="349c7-111">双击此注册表文件，或单击**导入**上**文件**使用注册表编辑器 (regedit32.exe) 的菜单将元数据写入到注册表。</span><span class="sxs-lookup"><span data-stu-id="349c7-111">Double-clicking this registry file or clicking **Import** on the **File** menu using the registry editor (regedit32.exe) writes the metadata into the registry.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="349c7-112">运行此注册表文件并不能将适配器信息添加到 BizTalk 管理数据库中。</span><span class="sxs-lookup"><span data-stu-id="349c7-112">Running this registry file does not add adapter information to the BizTalk Management database.</span></span> <span data-ttu-id="349c7-113">你必须手动执行此操作通过使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="349c7-113">You must do this manually by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="design-time-component"></a><span data-ttu-id="349c7-114">设计时组件</span><span class="sxs-lookup"><span data-stu-id="349c7-114">Design-Time Component</span></span>  
 <span data-ttu-id="349c7-115">自定义适配器的用户界面 (UI) 通过使用适配器框架来实现。</span><span class="sxs-lookup"><span data-stu-id="349c7-115">The user interface (UI) for a custom adapter is implemented by using the Adapter Framework.</span></span> <span data-ttu-id="349c7-116">这是一种高效的 UI 开发方法，因为 UI 可以通过作为适配器程序集一部分提供的 XML 架构来呈现。</span><span class="sxs-lookup"><span data-stu-id="349c7-116">This is a productive approach to UI development because the UI is rendered from an XML schema provided as part of the adapter's assembly.</span></span> <span data-ttu-id="349c7-117">只需少量代码就可以将架构内容转换为 UI，以配置适配器属性。</span><span class="sxs-lookup"><span data-stu-id="349c7-117">A small amount of code is required to transform the contents of the schema into a UI to configure the adapter's properties.</span></span>  
  
 <span data-ttu-id="349c7-118">对于需要与 SQL 适配器之类的应用程序适配器通信的业务流程，可以使用“添加适配器元数据”向导向某个 BizTalk 项目添加适配器元数据，如架构、消息类型和端口类型。</span><span class="sxs-lookup"><span data-stu-id="349c7-118">For an orchestration needing to communicate with an application adapter such as the SQL adapter, the Add Adapter Metadata Wizard enables you to add adapter metadata, such as schemas, message types, and port types, to a BizTalk project.</span></span> <span data-ttu-id="349c7-119">将“添加适配器元数据”向导与应用程序适配器一同使用可以将相应架构拖入系统。</span><span class="sxs-lookup"><span data-stu-id="349c7-119">Use the Add Adapter Metadata Wizard with application adapters to pull corresponding schemas into the system.</span></span> <span data-ttu-id="349c7-120">若要调用此向导从在 BizTalk （非适配器） 项目内的，右键单击项目，指向**添加生成的项**，单击**添加适配器元数据**然后从列表中选择注册适配器元数据导入的适配器。</span><span class="sxs-lookup"><span data-stu-id="349c7-120">To invoke this wizard from within a BizTalk (non-adapter) project, right-click the project, point to **Add Generated Items**, click **Add Adapter Metadata** and then select from the list of registered adapters to import the adapter metadata.</span></span>  
  
## <a name="run-time-component"></a><span data-ttu-id="349c7-121">运行时组件</span><span class="sxs-lookup"><span data-stu-id="349c7-121">Run-Time Component</span></span>  
 <span data-ttu-id="349c7-122">适配器通常包括两个公共运行时组件： 实现消息接收方，并实现消息发送方的组件的组件。</span><span class="sxs-lookup"><span data-stu-id="349c7-122">Typically an adapter consists of two public run-time components: the component that implements the message receiver and the component that implements the message sender.</span></span> <span data-ttu-id="349c7-123">这些组件可以部署在同一程序集内，也可以部署在两个不同的程序集内。</span><span class="sxs-lookup"><span data-stu-id="349c7-123">These components may be deployed in the same assembly or in two different assemblies.</span></span>  
  
#### <a name="receive-adapter"></a><span data-ttu-id="349c7-124">接收适配器</span><span class="sxs-lookup"><span data-stu-id="349c7-124">Receive Adapter</span></span>  
 <span data-ttu-id="349c7-125">接收适配器负责通过将网络/数据源流附加到消息正文来创建新的 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="349c7-125">A receive adapter is responsible for creating a new BizTalk message by attaching the network/data source stream to the message body.</span></span> <span data-ttu-id="349c7-126">它还添加与接收数据的终结点相关的任何元数据，然后将该消息提交给消息引擎。</span><span class="sxs-lookup"><span data-stu-id="349c7-126">It also adds any metadata pertinent to the endpoint over which the data was received, and then submits that message to the Messaging Engine.</span></span> <span data-ttu-id="349c7-127">适配器从接收终结点中删除数据，或将相应的确认消息发送到客户端，该值指示数据已接受到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="349c7-127">The adapter deletes the data from the receive endpoint or sends the appropriate acknowledgment message to the client indicating that the data was accepted into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
#### <a name="send-adapter"></a><span data-ttu-id="349c7-128">发送适配器</span><span class="sxs-lookup"><span data-stu-id="349c7-128">Send Adapter</span></span>  
 <span data-ttu-id="349c7-129">发送适配器负责使用其特定的传输协议将 BizTalk 消息发送到指定的终结点。</span><span class="sxs-lookup"><span data-stu-id="349c7-129">A send adapter is responsible for sending a BizTalk message to the specified endpoint using its specific transport protocol.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="349c7-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="349c7-130">See Also</span></span>  
 [<span data-ttu-id="349c7-131">什么是适配器 Framework？</span><span class="sxs-lookup"><span data-stu-id="349c7-131">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)