---
title: "什么是 Windows SharePoint Services Adapter？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, process flow
- Windows SharePoint Services adapters, receiving documents
- Windows SharePoint Services adapters, sending documents
- Windows SharePoint Services adapters, security
- Windows SharePoint Services adapters
- Windows SharePoint Services adapters, about Windows SharePoint Services adapters
ms.assetid: 1875ac85-46c2-4da5-ad16-8b078cb4cbd7
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a25bc378bdbb4c8bef34c3cff0140d03094faad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="0665c-103">什么是 Windows SharePoint Services Adapter？</span><span class="sxs-lookup"><span data-stu-id="0665c-103">What Is the Windows SharePoint Services Adapter?</span></span>
<span data-ttu-id="0665c-104">针对 Windows SharePoint Services 的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 适配器可与 Windows SharePoint Services 和 Microsoft Office InfoPath 更紧密地集成在一起。</span><span class="sxs-lookup"><span data-stu-id="0665c-104">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services provides a tighter integration with Windows SharePoint Services and Microsoft Office InfoPath.</span></span> <span data-ttu-id="0665c-105">以下主题介绍了 Windows SharePoint Services 适配器的功能并对其工作原理进行了简要说明。</span><span class="sxs-lookup"><span data-stu-id="0665c-105">The following topic describes the features and an overview of how the Windows SharePoint Services adapter works.</span></span>  
  
## <a name="features-of-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="0665c-106">Windows SharePoint Services 适配器的功能</span><span class="sxs-lookup"><span data-stu-id="0665c-106">Features of the Windows SharePoint Services adapter</span></span>  
 <span data-ttu-id="0665c-107">下表介绍了 Windows SharePoint Services 适配器的重要功能：</span><span class="sxs-lookup"><span data-stu-id="0665c-107">The following list describes important features of the Windows SharePoint Services adapter:</span></span>  
  
-   <span data-ttu-id="0665c-108">将 BizTalk Server XML 和二进制消息发送到 SharePoint 文档库的功能。</span><span class="sxs-lookup"><span data-stu-id="0665c-108">The ability to send BizTalk Server XML and binary messages to SharePoint document libraries.</span></span>  
  
-   <span data-ttu-id="0665c-109">与 InfoPath 集成： 你可以将转换传出 BizTalk Server XML 消息，以在从 Windows SharePoint Services 站点打开时的 InfoPath 中自动打开。</span><span class="sxs-lookup"><span data-stu-id="0665c-109">Integration with InfoPath: You can transform outgoing BizTalk Server XML messages to automatically open in InfoPath when opened from the Windows SharePoint Services site.</span></span>  
  
-   <span data-ttu-id="0665c-110">对进入 Windows SharePoint Services 的消息执行属性升级。</span><span class="sxs-lookup"><span data-stu-id="0665c-110">Property promotion for messages going into Windows SharePoint Services.</span></span> <span data-ttu-id="0665c-111">可以用该消息的 BizTalk Server 元数据对多达 16 个 SharePoint 列进行更新，例如业务流程实例 ID、消息 ID 或从该消息中提取的值。</span><span class="sxs-lookup"><span data-stu-id="0665c-111">Up to 16 SharePoint columns can be updated with BizTalk Server metadata about the message-like orchestration instance ID, message ID, or values extracted from the message.</span></span>  
  
-   <span data-ttu-id="0665c-112">基于消息内容和 BizTalk Server 属性来生成文件名定义。</span><span class="sxs-lookup"><span data-stu-id="0665c-112">File-name definition based on message content and BizTalk Server properties.</span></span>  
  
-   <span data-ttu-id="0665c-113">要将文档发送到任意列表的功能 (而不是到文档库): 在这种情况下文档本身不存储在 Windows SharePoint Services，但属性提升仍发生因此将创建一个新列表项并检索的列的值从消息中。</span><span class="sxs-lookup"><span data-stu-id="0665c-113">The ability to send documents to an arbitrary list (instead of to a document library): In this case the document itself is not stored in Windows SharePoint Services but the property promotion still happens so a new list item is created and the column values are retrieved from the message.</span></span>  
  
-   <span data-ttu-id="0665c-114">从任何文档库的任何视图中接收消息并使用指定文件名将其存档到指定文档库的功能。</span><span class="sxs-lookup"><span data-stu-id="0665c-114">The ability to receive messages from any view of any document library and archive them to a specified document library using the specified file name.</span></span>  
  
-   <span data-ttu-id="0665c-115">BizTalk Server 中的 Windows SharePoint Services 适配器属性中的升级： Windows SharePoint Services 文件信息进行消息上下文属性作为 BizTalk Server 中可用。</span><span class="sxs-lookup"><span data-stu-id="0665c-115">Promotion of Windows SharePoint Services adapter properties in BizTalk Server: Windows SharePoint Services file information is made available in BizTalk Server as message context properties.</span></span> <span data-ttu-id="0665c-116">消息上下文属性可以访问从管道、 业务流程，等等。可以通过 WSS 访问自定义 SharePoint 列。InPropertiesXml 文档。</span><span class="sxs-lookup"><span data-stu-id="0665c-116">The message context properties can be accessed from pipelines, orchestrations, etc. Custom SharePoint columns can be accessed through the WSS.InPropertiesXml document.</span></span>  
  
-   <span data-ttu-id="0665c-117">完全支持动态端口： 发送适配器可以支持 （由用户在创建时定义发送端口） 的静态 URI 绑定或动态 （发送消息时由业务流程定义） 的 URI 绑定。</span><span class="sxs-lookup"><span data-stu-id="0665c-117">Full support for dynamic ports: Send adapters can support static URI binding (defined by the user when the send port is created) or dynamic URI binding (defined by the orchestration when sending the message).</span></span> <span data-ttu-id="0665c-118">对于动态发送端口以及物理发送端口，所有配置信息都可以通过消息上下文属性（例如，WSS.Filename 和 WSS.ConfigTimeout）来定义。</span><span class="sxs-lookup"><span data-stu-id="0665c-118">All configuration information can be defined through message context properties, such as WSS.Filename and WSS.ConfigTimeout, for dynamic send ports as well as physical send ports.</span></span>  
  
-   <span data-ttu-id="0665c-119">性能计数器</span><span class="sxs-lookup"><span data-stu-id="0665c-119">Performance counters</span></span>  
  
## <a name="how-the-windows-sharepoint-services-adapter-works"></a><span data-ttu-id="0665c-120">Windows SharePoint Services 适配器的工作原理</span><span class="sxs-lookup"><span data-stu-id="0665c-120">How the Windows SharePoint Services adapter works</span></span>  
 <span data-ttu-id="0665c-121">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器 Windows SharePoint Services 的由三个主要组件组成：</span><span class="sxs-lookup"><span data-stu-id="0665c-121">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services consists of three main components:</span></span>  
  
-   <span data-ttu-id="0665c-122">Windows SharePoint Services 适配器 Web 服务</span><span class="sxs-lookup"><span data-stu-id="0665c-122">Windows SharePoint Services adapter Web service</span></span>  
  
-   <span data-ttu-id="0665c-123">Windows SharePoint Services 接收适配器</span><span class="sxs-lookup"><span data-stu-id="0665c-123">Windows SharePoint Services receive adapter</span></span>  
  
-   <span data-ttu-id="0665c-124">Windows SharePoint Services 发送适配器</span><span class="sxs-lookup"><span data-stu-id="0665c-124">Windows SharePoint Services send adapter</span></span>  
  
 <span data-ttu-id="0665c-125">在 Windows SharePoint Services 服务器上，安装了 Web Services (BTSharePointAdapterWS.asmx) 以提供对 Windows SharePoint Services 库和列表的访问。</span><span class="sxs-lookup"><span data-stu-id="0665c-125">On the Windows SharePoint Services server, the Web service (BTSharePointAdapterWS.asmx) is installed to provide access to the Windows SharePoint Services libraries and lists.</span></span> <span data-ttu-id="0665c-126">该 Web Services 公开了从 SharePoint 库中获取、放置、删除和存档文档的方法。</span><span class="sxs-lookup"><span data-stu-id="0665c-126">The Web service exposes methods to get, put, delete, and archive documents from a SharePoint library.</span></span> <span data-ttu-id="0665c-127">接收适配器可从该 Web Services 检索文件，而发送适配器则可以向其张贴文件。</span><span class="sxs-lookup"><span data-stu-id="0665c-127">The receive adapter retrieves files from the Web service and the send adapter posts files to it.</span></span>  
  
 <span data-ttu-id="0665c-128">下图显示的主要组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供这些功能的 Windows SharePoint Services 的适配器。</span><span class="sxs-lookup"><span data-stu-id="0665c-128">The following figure shows the main components of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services that provide these capabilities.</span></span>  
  
 ![](../core/media/bts-dev-adapters-wss-architecture.gif "BTS_Dev_Adapters_WSS_Architecture")  
  
### <a name="receiving-documents-from-windows-sharepoint-services"></a><span data-ttu-id="0665c-129">从 Windows SharePoint Services 接收文档</span><span class="sxs-lookup"><span data-stu-id="0665c-129">Receiving documents from Windows SharePoint Services</span></span>  
 <span data-ttu-id="0665c-130">接收适配器轮询 Windows SharePoint Services 文档库视图。</span><span class="sxs-lookup"><span data-stu-id="0665c-130">The receive adapter polls Windows SharePoint Services document library views.</span></span> <span data-ttu-id="0665c-131">它对 Windows SharePoint Services 服务器调用 Web 方法，该方法使用 Windows SharePoint Services 对象模型来浏览库，签出文件，并将文件数据返回给适配器。</span><span class="sxs-lookup"><span data-stu-id="0665c-131">It calls a Web method on the Windows SharePoint Services server which uses the Windows SharePoint Services object model to browse the library, check out the files and return the file data to the adapter.</span></span> <span data-ttu-id="0665c-132">然后，适配器将文件提交给 BizTalk Server MessageBox，并调用另一个 Web 方法从 Windows SharePoint Services 中删除或存档文件。</span><span class="sxs-lookup"><span data-stu-id="0665c-132">The adapter then submits the files to the BizTalk Server MessageBox and calls another Web method to delete or archive the files from Windows SharePoint Services.</span></span> <span data-ttu-id="0665c-133">为了对 Windows SharePoint Services 库中的文件进行筛选，该适配器会通过 Windows SharePoint Services 视图轮询 Windows SharePoint Services 库。</span><span class="sxs-lookup"><span data-stu-id="0665c-133">In order to filter files in a Windows SharePoint Services library, the adapter polls the Windows SharePoint Services library through a Windows SharePoint Services view.</span></span>  
  
 <span data-ttu-id="0665c-134">集中式（轮询）方法提供了一种简单的管理模型，在该模型中，配置工作在 BizTalk Server 上完成。</span><span class="sxs-lookup"><span data-stu-id="0665c-134">The centralized (polling) approach offers a simple management model where configuration is done on the BizTalk server.</span></span> <span data-ttu-id="0665c-135">由于该方法允许对消息进行批处理，因此还提供了更优异的性能。</span><span class="sxs-lookup"><span data-stu-id="0665c-135">It also offers better performance due to the fact that it allows batching of the messages.</span></span>  
  
 <span data-ttu-id="0665c-136">由于不能跨 Windows SharePoint Services、Web Services 和 BizTalk Server 提供平台级别的事务支持，因此使用签出机制来最大限度地减少与失败条件相关联的错误。</span><span class="sxs-lookup"><span data-stu-id="0665c-136">Since platform-level transaction support is not available across Windows SharePoint Services, Web services, and BizTalk Server, the check-out mechanism is used to minimize errors associated with failure conditions.</span></span> <span data-ttu-id="0665c-137">在某些情况下（即文件成功发送到 BizTalk Server MessageBox 数据库中，但无法从 Windows SharePoint Services 删除），即使文件已提交到 BizTalk Server，这些文件仍将在 Windows SharePoint Services 服务器上继续处于已签出状态。</span><span class="sxs-lookup"><span data-stu-id="0665c-137">Under certain conditions (that is, files are successfully sent into the BizTalk Server MessageBox database but cannot be deleted from Windows SharePoint Services), the files will remain checked out on the Windows SharePoint Services server even though they were submitted to BizTalk Server.</span></span> <span data-ttu-id="0665c-138">错误将记录到 BizTalk 服务器上的事件日志中。</span><span class="sxs-lookup"><span data-stu-id="0665c-138">Errors will be logged to the event log on the BizTalk server.</span></span>  
  
### <a name="sending-documents-to-windows-sharepoint-services"></a><span data-ttu-id="0665c-139">向 Windows SharePoint Services 发送文档</span><span class="sxs-lookup"><span data-stu-id="0665c-139">Sending documents to Windows SharePoint Services</span></span>  
 <span data-ttu-id="0665c-140">适配器通过对 Windows SharePoint Services 服务器调用 Web 方法来向 Windows SharePoint Services 发送文档。</span><span class="sxs-lookup"><span data-stu-id="0665c-140">The adapter sends documents to Windows SharePoint Services by calling a Web method on the Windows SharePoint Services server.</span></span> <span data-ttu-id="0665c-141">适配器指定 Windows SharePoint Services 站点 URL、相对于站点的文档库或列表 URL、文件或列表项名称以及要与该文件关联的升级属性。</span><span class="sxs-lookup"><span data-stu-id="0665c-141">The adapter specifies the Windows SharePoint Services site URL, document library or list URL relative to the site, file, or list item name and promoted properties to associate with the file.</span></span>  
  
 <span data-ttu-id="0665c-142">可以将文件名设置为固定字符串，也可以设置为从文档中的 XML 数据派生的名称。</span><span class="sxs-lookup"><span data-stu-id="0665c-142">You can set the file name to a fixed string or to a name derived from the XML data in the document.</span></span> <span data-ttu-id="0665c-143">对于强制执行标准命名约定来说，派生名称会非常有用。</span><span class="sxs-lookup"><span data-stu-id="0665c-143">Deriving the name can be very useful to enforce standard naming conventions.</span></span> <span data-ttu-id="0665c-144">适配器还可以将文件的升级属性值设置为列值。</span><span class="sxs-lookup"><span data-stu-id="0665c-144">The adapter can also set promoted property values on the file as column values.</span></span> <span data-ttu-id="0665c-145">与文件名一样，升级属性值可以为固定值，也可以从文档中的 XML 数据派生。</span><span class="sxs-lookup"><span data-stu-id="0665c-145">As with the file names, the promoted property values can be fixed or can be derived from the XML data in the document.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0665c-146">Windows SharePoint Services 适配器中的升级属性是与 BizTalk Server 中的升级属性或 Windows SharePoint Services 中的升级属性不同的实体。</span><span class="sxs-lookup"><span data-stu-id="0665c-146">Promoted properties in the Windows SharePoint Services adapter are different entities than promoted properties in BizTalk Server, or promoted properties in Windows SharePoint Services.</span></span>  
  
 <span data-ttu-id="0665c-147">在浏览 Windows SharePoint Services 表单库时，Windows SharePoint Services 升级属性用来使 XML 元素可见。</span><span class="sxs-lookup"><span data-stu-id="0665c-147">Windows SharePoint Services promoted properties are used to make XML elements visible when browsing a Windows SharePoint Services forms library.</span></span> <span data-ttu-id="0665c-148">在将 InfoPath 表单发布到 Windows SharePoint Services 表单库时，InfoPath 会对表单库进行配置以升级关键元素，使此操作自动进行。</span><span class="sxs-lookup"><span data-stu-id="0665c-148">When an InfoPath form is published to a Windows SharePoint Services forms library, InfoPath configures the forms library to promote key elements, making this happen automatically.</span></span> <span data-ttu-id="0665c-149">只有在使用 InfoPath 表单库（使用相同的 XSD 架构和 InfoPath 解决方案存储 InfoPath 表单的文档库）时，才可在 Windows SharePoint Services 中使用此功能。</span><span class="sxs-lookup"><span data-stu-id="0665c-149">This feature is available in Windows SharePoint Services only when using InfoPath form libraries (document libraries that store InfoPath forms with the same XSD schema and InfoPath solution).</span></span>  
  
 <span data-ttu-id="0665c-150">将具有不同架构的文档存储在同一文档库中时，Windows SharePoint Services 适配器属性升级使用户能够将属性升级到 Windows SharePoint Services 中。</span><span class="sxs-lookup"><span data-stu-id="0665c-150">Windows SharePoint Services adapter property promotion enables the user to promote properties into Windows SharePoint Services when documents with different schemas are stored in the same document library.</span></span>  
  
 <span data-ttu-id="0665c-151">BizTalk Server 属性升级的概念与此类似，唯一不同的是属性是作为消息的属性对业务流程可见，而不是在用户界面上对最终用户可见。</span><span class="sxs-lookup"><span data-stu-id="0665c-151">BizTalk Server property promotion is a similar concept, only that properties are made visible to the orchestration as properties on the message and not to the end user on the UI.</span></span> <span data-ttu-id="0665c-152">此外，在将属性值保存回文档时，BizTalk Server 支持属性降级的概念。</span><span class="sxs-lookup"><span data-stu-id="0665c-152">In addition, BizTalk Server supports a concept of property demotion when the property values are saved back into the document.</span></span>  
  
 <span data-ttu-id="0665c-153">将 Windows SharePoint Services 适配器用于 InfoPath 表单和表单库（而不是任意 XML 和文档库）时，不需要通过发送适配器设置升级属性。</span><span class="sxs-lookup"><span data-stu-id="0665c-153">When using the Windows SharePoint Services adapter with InfoPath forms and forms libraries (rather than arbitrary XML and document libraries), you do not need to set the promoted properties through the send adapter.</span></span> <span data-ttu-id="0665c-154">相反，可以在业务流程中更改文档（通过更改消息直接进行更改，或通过将要降级的属性间接进行更改）。</span><span class="sxs-lookup"><span data-stu-id="0665c-154">Instead, the document can be changed within the orchestration (directly by changing the message or indirectly through properties that will be demoted).</span></span> <span data-ttu-id="0665c-155">Windows SharePoint Services 将会对这些值进行自动升级。</span><span class="sxs-lookup"><span data-stu-id="0665c-155">The values will be automatically promoted by Windows SharePoint Services.</span></span>  
  
## <a name="security-considerations-for-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="0665c-156">Windows SharePoint Services 适配器的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="0665c-156">Security considerations for the Windows SharePoint Services adapter</span></span>  
 <span data-ttu-id="0665c-157">Windows SharePoint Services 适配器由子系统、运行在 Windows SharePoint Services 网站上的 BTSharePointAdapterWS Web Services 以及运行在 BizTalk Server 主机实例进程中的 BizTalk 服务器上的适配器运行时组成。</span><span class="sxs-lookup"><span data-stu-id="0665c-157">The Windows SharePoint Services adapter consists of subsystems, the BTSharePointAdapterWS Web service that runs on the Windows SharePoint Services Web site, and the adapter runtime that runs on the BizTalk server within the BizTalk Server host instance process.</span></span> <span data-ttu-id="0665c-158">适配器运行时调用 BTSharePointAdapterWS Web Services，该 Web Services 必须具有在 Windows SharePoint Services 中执行某些任务的权限。</span><span class="sxs-lookup"><span data-stu-id="0665c-158">The adapter runtime invokes the BTSharePointAdapterWS Web service which must have permissions to perform certain tasks within Windows SharePoint Services.</span></span> <span data-ttu-id="0665c-159">由于此组件作为调用方运行，因此需要向调用方授予权限。</span><span class="sxs-lookup"><span data-stu-id="0665c-159">Since this component runs as the caller, the permissions need to be granted to the caller.</span></span> <span data-ttu-id="0665c-160">这意味着必须进行 BizTalk 主机实例**参与者**为了能够发送和接收消息，从该站点的 SharePoint 站点上。</span><span class="sxs-lookup"><span data-stu-id="0665c-160">This means that the BizTalk host instance must be made a **Contributor** on the SharePoint site in order to be able to send and receive messages from that site.</span></span> <span data-ttu-id="0665c-161">BTSharePointAdapterWS Web 服务可以仅由的成员调用**SharePoint 启用主机**组。</span><span class="sxs-lookup"><span data-stu-id="0665c-161">The BTSharePointAdapterWS Web service can be invoked only by members of the **SharePoint Enabled Hosts** group.</span></span> <span data-ttu-id="0665c-162">若要允许运行适配器运行时，与 Web 服务进行交互的 BizTalk 主机实例，主机实例的 Windows 帐户必须进行的成员**SharePoint 启用主机**组。</span><span class="sxs-lookup"><span data-stu-id="0665c-162">In order to allow a BizTalk host instance, running the adapter runtime, to interact with the Web service, the host instance Windows account must be made a member of the **SharePoint Enabled Hosts** group.</span></span> <span data-ttu-id="0665c-163">它是管理员可以添加和从使主机实例以及此组中删除帐户的责任帐户成员的 sharepoint**参与者**角色。</span><span class="sxs-lookup"><span data-stu-id="0665c-163">It is the responsibility of the administrator to add and remove accounts from this group as well as to make the host instance accounts members of the SharePoint **Contributor** role.</span></span>  
  
|<span data-ttu-id="0665c-164">组件</span><span class="sxs-lookup"><span data-stu-id="0665c-164">Component</span></span>|<span data-ttu-id="0665c-165">进程标识</span><span class="sxs-lookup"><span data-stu-id="0665c-165">Process identity</span></span>|<span data-ttu-id="0665c-166">权限</span><span class="sxs-lookup"><span data-stu-id="0665c-166">Permission</span></span>|  
|---------------|----------------------|----------------|  
|<span data-ttu-id="0665c-167">BTSharePointAdapterWS Web Services</span><span class="sxs-lookup"><span data-stu-id="0665c-167">BTSharePointAdapterWS Web service</span></span>|<span data-ttu-id="0665c-168">调用方标识</span><span class="sxs-lookup"><span data-stu-id="0665c-168">Caller identity</span></span>|<span data-ttu-id="0665c-169">调用授予 SharePoint Enabled Hosts 组的权限</span><span class="sxs-lookup"><span data-stu-id="0665c-169">Invoke permission granted to SharePoint Enabled Hosts group</span></span>|  
|<span data-ttu-id="0665c-170">适配器运行时</span><span class="sxs-lookup"><span data-stu-id="0665c-170">Adapter runtime</span></span>|<span data-ttu-id="0665c-171">BizTalk 主机的标识</span><span class="sxs-lookup"><span data-stu-id="0665c-171">Identity of BizTalk host</span></span>|<span data-ttu-id="0665c-172">N/A</span><span class="sxs-lookup"><span data-stu-id="0665c-172">N/A</span></span>|  
|<span data-ttu-id="0665c-173">Windows SharePoint Services 对象模型</span><span class="sxs-lookup"><span data-stu-id="0665c-173">Windows SharePoint Services Object Model</span></span>|<span data-ttu-id="0665c-174">N/A</span><span class="sxs-lookup"><span data-stu-id="0665c-174">N/A</span></span>|<span data-ttu-id="0665c-175">SharePoint 启用主机组必须属于**参与者**SharePoint 服务中的角色。</span><span class="sxs-lookup"><span data-stu-id="0665c-175">The SharePoint Enabled Hosts group must be a member of the **Contributor** role in SharePoint Services.</span></span>|  
  
 <span data-ttu-id="0665c-176">BizTalk Server 安装程序 BTSharePointAdapterWS Web 服务上配置权限，以便仅的帐户，是的成员**SharePoint 启用主机**组可以访问此 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="0665c-176">BizTalk Server Setup configures the permissions on the BTSharePointAdapterWS Web service so that only the accounts that are members of the **SharePoint Enabled Hosts** group can access this Web service.</span></span> <span data-ttu-id="0665c-177">如果你希望主机运行 Windows SharePoint Services 适配器，管理员将需要添加到该主机与关联的 NT 组**SharePoint 启用主机**分组以及还添加**SharePoint 启用主机**组，以便 Windows SharePoint Services**参与者**角色。</span><span class="sxs-lookup"><span data-stu-id="0665c-177">If you want hosts to run the Windows SharePoint Services adapter, the administrator will have to add the NT group associated with that host to the **SharePoint Enabled Hosts** group and also add the **SharePoint Enabled Hosts** group to the Windows SharePoint Services **Contributor** role.</span></span>  
  
 <span data-ttu-id="0665c-178">对 Windows SharePoint Services 文件、列表和文档库的权限使用 Windows SharePoint Services 安全性进行限制。</span><span class="sxs-lookup"><span data-stu-id="0665c-178">Permissions to Windows SharePoint Services files, lists, and document libraries are restricted using Windows SharePoint Services security.</span></span> <span data-ttu-id="0665c-179">消息从 Windows SharePoint Services 直接发送到 BizTalk Server 中。</span><span class="sxs-lookup"><span data-stu-id="0665c-179">The messages are sent from Windows SharePoint Services directly into BizTalk Server.</span></span> <span data-ttu-id="0665c-180">适配器运行时与 Web Services 之间的通信通过 HTTP 或 HTTPS 来完成。</span><span class="sxs-lookup"><span data-stu-id="0665c-180">The communication between the adapter runtime and the Web service is done over HTTP or HTTPS.</span></span>  
  
 <span data-ttu-id="0665c-181">适配器假定 BTSharePointAdapterWS Web Services 正在使用相同的 HTTP 方案（HTTP 或 HTTPS）作为 Windows SharePoint Services 站点。</span><span class="sxs-lookup"><span data-stu-id="0665c-181">The adapter assumes that the BTSharePointAdapterWS Web service is using the same HTTP scheme (HTTP or HTTPS) as the Windows SharePoint Services site.</span></span> <span data-ttu-id="0665c-182">这意味着，在安全 IIS 网站上创建 Windows SharePoint Services 站点时，适配器将使用 HTTPS 与 BTSSharePointAdapterWS Web Services 进行通信，或者在没有服务器证书的 IIS 网站上创建 Windows SharePoint Services 站点时，它将使用 HTTP 与 BTSharePointAdapterWS Web Services 进行通信。</span><span class="sxs-lookup"><span data-stu-id="0665c-182">This means that the adapter will use HTTPS to communicate with the BTSSharePointAdapterWS Web service when the Windows SharePoint Services Site is created on a secure IIS Web site, or it will use HTTP to communicate with the BTSharePointAdapterWS Web service when the Windows SharePoint Services site is created on an IIS Web site without a server certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0665c-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0665c-183">See Also</span></span>  
 <span data-ttu-id="0665c-184">[设置和部署 Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0665c-184">[Setting Up and Deploying the Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md) </span></span>  
 <span data-ttu-id="0665c-185">[配置 Windows SharePoint Services Adapter](../core/configuring-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0665c-185">[Configuring the Windows SharePoint Services Adapter](../core/configuring-the-windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="0665c-186">Windows SharePoint Services 适配器演练</span><span class="sxs-lookup"><span data-stu-id="0665c-186">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)