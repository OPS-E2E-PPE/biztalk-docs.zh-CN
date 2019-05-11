---
title: 适配器组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 383e8bcb-2b4d-40f9-9e98-f49e8d6f30f7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 215bb12537bbd0df859c59c8914c6cba63cd139a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361603"
---
# <a name="adapter-components"></a><span data-ttu-id="6ed19-102">适配器组件</span><span class="sxs-lookup"><span data-stu-id="6ed19-102">Adapter Components</span></span>
<span data-ttu-id="6ed19-103">自定义适配器共享标准化的配置、 管理和使用的本地适配器的安装程序机制。</span><span class="sxs-lookup"><span data-stu-id="6ed19-103">A custom adapter shares the standardized configuration, management, and setup mechanisms used by the native adapters.</span></span> <span data-ttu-id="6ed19-104">自定义适配器通过使用适配器框架进行标准化，来管理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="6ed19-104">With the standardization to the Adapter Framework, a custom adapter is managed by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="6ed19-105">下图显示了自定义适配器的主要组件： 适配器注册表文件、 适配器设计时组件和适配器运行时组件。</span><span class="sxs-lookup"><span data-stu-id="6ed19-105">The following figure shows the main components of a custom adapter: the adapter registry file, the adapter design-time component, and the adapter run-time component.</span></span>  
  
 <span data-ttu-id="6ed19-106">![](../core/media/elementsofanadapter.gif "ElementsOfAnAdapter")</span><span class="sxs-lookup"><span data-stu-id="6ed19-106">![](../core/media/elementsofanadapter.gif "ElementsOfAnAdapter")</span></span>  
  
## <a name="adapter-registry-file"></a><span data-ttu-id="6ed19-107">适配器注册表文件</span><span class="sxs-lookup"><span data-stu-id="6ed19-107">Adapter Registry File</span></span>  
 <span data-ttu-id="6ed19-108">必须在注册表和 BizTalk 管理数据库中注册适配器有关的特定信息。</span><span class="sxs-lookup"><span data-stu-id="6ed19-108">Certain information about adapters must be registered in the registry and the BizTalk Management database.</span></span> <span data-ttu-id="6ed19-109">信息的适配器的别名，如接收处理程序、 接收位置和传输类型被称为元数据。</span><span class="sxs-lookup"><span data-stu-id="6ed19-109">Information such as an adapter's alias, receive hander, receive location, and transport type is called metadata.</span></span> <span data-ttu-id="6ed19-110">在手动适配器使用注册期间创建这些元数据条目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="6ed19-110">These metadata entries are created during manual adapter registration using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="6ed19-111">或者，可以运行适配器注册向导 (AdapterRegistryWizard.exe) SDK 实用工具生成自定义适配器的注册表文件。</span><span class="sxs-lookup"><span data-stu-id="6ed19-111">Alternatively, you can run the Adapter Registry Wizard (AdapterRegistryWizard.exe) SDK utility to generate a registry file for your custom adapter.</span></span> <span data-ttu-id="6ed19-112">双击此注册表文件，或单击**导入**上**文件**使用注册表编辑器 (regedit32.exe) 的菜单将元数据写入到注册表。</span><span class="sxs-lookup"><span data-stu-id="6ed19-112">Double-clicking this registry file or clicking **Import** on the **File** menu using the registry editor (regedit32.exe) writes the metadata into the registry.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ed19-113">运行此注册表文件不会添加到 BizTalk 管理数据库适配器信息。</span><span class="sxs-lookup"><span data-stu-id="6ed19-113">Running this registry file does not add adapter information to the BizTalk Management database.</span></span> <span data-ttu-id="6ed19-114">通过使用，必须手动执行此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="6ed19-114">You must do this manually by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="design-time-component"></a><span data-ttu-id="6ed19-115">设计时组件</span><span class="sxs-lookup"><span data-stu-id="6ed19-115">Design-Time Component</span></span>  
 <span data-ttu-id="6ed19-116">通过使用适配器框架实现自定义适配器的用户界面 (UI)。</span><span class="sxs-lookup"><span data-stu-id="6ed19-116">The user interface (UI) for a custom adapter is implemented by using the Adapter Framework.</span></span> <span data-ttu-id="6ed19-117">这是因为从 XML 架构作为适配器的程序集的一部分提供呈现的 UI 的 UI 开发高效方法。</span><span class="sxs-lookup"><span data-stu-id="6ed19-117">This is a productive approach to UI development because the UI is rendered from an XML schema provided as part of the adapter's assembly.</span></span> <span data-ttu-id="6ed19-118">少量的代码需要的架构内容转换为 UI，以配置适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="6ed19-118">A small amount of code is required to transform the contents of the schema into a UI to configure the adapter's properties.</span></span>  
  
 <span data-ttu-id="6ed19-119">为业务流程，无需与 SQL 适配器之类的应用程序适配器进行通信，添加适配器元数据向导，可向 BizTalk 项目添加适配器元数据，例如架构、 消息类型和端口类型。</span><span class="sxs-lookup"><span data-stu-id="6ed19-119">For an orchestration needing to communicate with an application adapter such as the SQL adapter, the Add Adapter Metadata Wizard enables you to add adapter metadata, such as schemas, message types, and port types, to a BizTalk project.</span></span> <span data-ttu-id="6ed19-120">添加适配器元数据向导应用程序适配器使用相应架构拖入系统。</span><span class="sxs-lookup"><span data-stu-id="6ed19-120">Use the Add Adapter Metadata Wizard with application adapters to pull corresponding schemas into the system.</span></span> <span data-ttu-id="6ed19-121">若要调用此向导从 BizTalk （非适配器） 项目中的，右键单击项目，指向**添加生成的项**，单击**添加适配器元数据**然后从列表中选择注册若要导入适配器元数据的适配器。</span><span class="sxs-lookup"><span data-stu-id="6ed19-121">To invoke this wizard from within a BizTalk (non-adapter) project, right-click the project, point to **Add Generated Items**, click **Add Adapter Metadata** and then select from the list of registered adapters to import the adapter metadata.</span></span>  
  
## <a name="run-time-component"></a><span data-ttu-id="6ed19-122">运行时组件</span><span class="sxs-lookup"><span data-stu-id="6ed19-122">Run-Time Component</span></span>  
 <span data-ttu-id="6ed19-123">适配器通常包含两个公共运行时组件： 实现消息接收方和实现消息发件人的组件的组件。</span><span class="sxs-lookup"><span data-stu-id="6ed19-123">Typically an adapter consists of two public run-time components: the component that implements the message receiver and the component that implements the message sender.</span></span> <span data-ttu-id="6ed19-124">在同一程序集中或两个不同的程序集，这些组件可以进行部署。</span><span class="sxs-lookup"><span data-stu-id="6ed19-124">These components may be deployed in the same assembly or in two different assemblies.</span></span>  
  
#### <a name="receive-adapter"></a><span data-ttu-id="6ed19-125">接收适配器</span><span class="sxs-lookup"><span data-stu-id="6ed19-125">Receive Adapter</span></span>  
 <span data-ttu-id="6ed19-126">接收适配器负责通过将网络/数据源流附加到消息正文中创建新的 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="6ed19-126">A receive adapter is responsible for creating a new BizTalk message by attaching the network/data source stream to the message body.</span></span> <span data-ttu-id="6ed19-127">它还会添加到终结点的数据接收的然后该将消息提交到消息引擎相关的任何元数据。</span><span class="sxs-lookup"><span data-stu-id="6ed19-127">It also adds any metadata pertinent to the endpoint over which the data was received, and then submits that message to the Messaging Engine.</span></span> <span data-ttu-id="6ed19-128">适配器从接收终结点删除数据，或将相应的确认消息发送到客户端，该值指示数据已被接受到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6ed19-128">The adapter deletes the data from the receive endpoint or sends the appropriate acknowledgment message to the client indicating that the data was accepted into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
#### <a name="send-adapter"></a><span data-ttu-id="6ed19-129">发送适配器</span><span class="sxs-lookup"><span data-stu-id="6ed19-129">Send Adapter</span></span>  
 <span data-ttu-id="6ed19-130">发送适配器负责将 BizTalk 消息发送到指定的终结点使用其特定的传输协议。</span><span class="sxs-lookup"><span data-stu-id="6ed19-130">A send adapter is responsible for sending a BizTalk message to the specified endpoint using its specific transport protocol.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ed19-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ed19-131">See Also</span></span>  
 [<span data-ttu-id="6ed19-132">适配器框架概述</span><span class="sxs-lookup"><span data-stu-id="6ed19-132">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)