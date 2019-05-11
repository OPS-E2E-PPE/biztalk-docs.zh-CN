---
title: Windows SharePoint Services 4.0 支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84be7aa0-2ff2-4e40-9c39-5cb89549c636
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36c1e22d33076516bf04282f65586af0ea737930
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240301"
---
# <a name="windows-sharepoint-services-40-support"></a><span data-ttu-id="af6ff-102">Windows SharePoint Services 4.0 支持</span><span class="sxs-lookup"><span data-stu-id="af6ff-102">Windows SharePoint Services 4.0 Support</span></span>
<span data-ttu-id="af6ff-103">用于 BizTalk Server 的 Windows SharePoint Services 适配器提供相同的功能用于 Windows SharePoint Services adapter [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="af6ff-103">The Windows SharePoint Services adapter for BizTalk Server provides feature/functionality parity with the Windows SharePoint Services adapter for [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)].</span></span> <span data-ttu-id="af6ff-104">用于 BizTalk Server 的 Windows SharePoint Services 适配器还支持以下功能，可与 Windows SharePoint Services 4.0:</span><span class="sxs-lookup"><span data-stu-id="af6ff-104">The Windows SharePoint Services adapter for BizTalk Server also supports the following functionality available with Windows SharePoint Services 4.0:</span></span>  

- <span data-ttu-id="af6ff-105">将消息发送到 Windows SharePoint Services 4.0 博客站点。</span><span class="sxs-lookup"><span data-stu-id="af6ff-105">Sending messages to a Windows SharePoint Services 4.0 blog site.</span></span>  

- <span data-ttu-id="af6ff-106">发送消息和来自 Windows SharePoint Services 4.0 Wiki 站点接收消息。</span><span class="sxs-lookup"><span data-stu-id="af6ff-106">Sending messages to and receiving message from a Windows SharePoint Services 4.0 Wiki site.</span></span>  

  <span data-ttu-id="af6ff-107">用于 BizTalk Server 的 Windows SharePoint Services 适配器不支持在 Windows SharePoint Services 4.0 中可用的下列功能：</span><span class="sxs-lookup"><span data-stu-id="af6ff-107">The Windows SharePoint Services adapter for BizTalk Server does not provide support for the following features that are available in Windows SharePoint Services 4.0:</span></span>  

- <span data-ttu-id="af6ff-108">**回收站**:用于 BizTalk Server 适配器的 Windows SharePoint Services 适配器不支持接收，或显式将消息发送自/至回收站。</span><span class="sxs-lookup"><span data-stu-id="af6ff-108">**Recycle Bin**: The Windows SharePoint Services adapter for BizTalk Server adapter does not support receiving, or explicitly sending messages from/to the Recycle Bin.</span></span>  

- <span data-ttu-id="af6ff-109">**列出文件夹**:用于 BizTalk Server 的 Windows SharePoint Services 适配器可向列表发送消息，但它不能接收来自列表的消息。</span><span class="sxs-lookup"><span data-stu-id="af6ff-109">**Lists folders**: The Windows SharePoint Services adapter for BizTalk Server can send messages to lists but it cannot receive messages from lists.</span></span> <span data-ttu-id="af6ff-110">Windows SharePoint Services 4.0 支持在列表中的文件夹，但用于 BizTalk Server 的 Windows SharePoint Services 适配器不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="af6ff-110">Windows SharePoint Services 4.0 supports folders in lists but the Windows SharePoint Services adapter for BizTalk Server does not support this feature.</span></span> <span data-ttu-id="af6ff-111">因此，BizTalk Server 的 Windows SharePoint Services 适配器不能在根文件夹之外的列表文件夹中创建列表项。</span><span class="sxs-lookup"><span data-stu-id="af6ff-111">Therefore, the Windows SharePoint Services adapter for BizTalk Server cannot create list items in a list folder other than the root folder.</span></span>  

- <span data-ttu-id="af6ff-112">以下各节介绍了更详细地介绍如何使用 BizTalk Server 的 Windows SharePoint Services 适配器向 Windows SharePoint Services 4.0 博客网站发送消息以及如何将消息发送到和从 Windows SharePoint Services 接收消息4.0 Wiki 网站。</span><span class="sxs-lookup"><span data-stu-id="af6ff-112">The following sections describe in greater detail how to use the Windows SharePoint Services adapter for BizTalk Server to send messages to a Windows SharePoint Services 4.0 blog site and how to send messages to and receive messages from a Windows SharePoint Services 4.0 Wiki site.</span></span>  

## <a name="sending-to-a-windows-sharepoint-services-40-blog-site"></a><span data-ttu-id="af6ff-113">将发送到 Windows SharePoint Services 4.0 博客站点</span><span class="sxs-lookup"><span data-stu-id="af6ff-113">Sending to a Windows SharePoint Services 4.0 Blog Site</span></span>  
 <span data-ttu-id="af6ff-114">在 Windows SharePoint Services 4.0 博客网站中，发布内容存储在**发**中定义列表和 post 类别**类别**列表。</span><span class="sxs-lookup"><span data-stu-id="af6ff-114">In a Windows SharePoint Services 4.0 blog site, posts are stored in the **Posts** list and post categories are defined in the **Categories** list.</span></span>  

 <span data-ttu-id="af6ff-115">若要将消息发布到 Windows SharePoint Services 4.0 博客网站，可在适配器中输入以下值**传输属性**对话框中配置使用 Windows SharePoint Services 适配器的发送端口时：</span><span class="sxs-lookup"><span data-stu-id="af6ff-115">To post a message to a Windows SharePoint Services 4.0 blog site, enter the following values in the adapter **Transport Properties** dialog box when configuring a send port that uses the Windows SharePoint Services adapter:</span></span>  


|        <span data-ttu-id="af6ff-116">属性</span><span class="sxs-lookup"><span data-stu-id="af6ff-116">Property</span></span>        |                                                                                            <span data-ttu-id="af6ff-117">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="af6ff-117">Value</span></span>                                                                                            |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="af6ff-118">目标文件夹 URL</span><span class="sxs-lookup"><span data-stu-id="af6ff-118">Destination Folder URL</span></span> |                                            <span data-ttu-id="af6ff-119">发布内容列表，相对于 SharePoint 站点，例如"Lists/Posts"目标文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="af6ff-119">Destination folder URL of the Posts list, relative to the SharePoint site, for example "Lists/Posts".</span></span>                                            |
|  <span data-ttu-id="af6ff-120">SharePoint 站点 URL</span><span class="sxs-lookup"><span data-stu-id="af6ff-120">SharePoint Site URL</span></span>   | <span data-ttu-id="af6ff-121">Windows SharePoint Services 4.0 博客站点，例如 http:// URL<em>\<servername\></em>/站点/博客/位置*\<servername\>* 是Web 服务器的实际名称的占位符。</span><span class="sxs-lookup"><span data-stu-id="af6ff-121">URL of the Windows SharePoint Services 4.0 blog site, for example http://<em>\<servername\></em>/sites/blog/ where *\<servername\>* is a placeholder for the actual name of the Web server.</span></span> |

 <span data-ttu-id="af6ff-122">然后设置为值**类别**，**已发布**， **Title**，并**正文**属性设置相应发布的博客WSS 中的值。ConfigPropertiesXml 消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="af6ff-122">Then set the values for the **Category**, **Published**, **Title**, and **Body** properties for the blog posting by setting corresponding values in the WSS.ConfigPropertiesXml context property of the message.</span></span> <span data-ttu-id="af6ff-123">这可以使用自定义管道或业务流程中。</span><span class="sxs-lookup"><span data-stu-id="af6ff-123">This can be done with a custom pipeline or in an orchestration.</span></span> <span data-ttu-id="af6ff-124">例如，在业务流程中的以下表达式将 WSS 中设置值。ConfigPropertiesXml Message_Out 消息的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="af6ff-124">For example, the following expression in an orchestration would set values in the WSS.ConfigPropertiesXml context property of the Message_Out message.</span></span>  

```  
int_Category = 1;  
str_Published = Microsoft.SharePoint.Utilities.SPUtility.CreateISO8601DateTimeFromSystemDateTime(System.DateTime.Now);  
// requires a reference to Microsoft.SharePoint.dll  
str_Title = "This is the title of the post from the WSS adapter";  
str_Body = "This is the body of the post from the WSS adapter";  

Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Category</PropertyName1>  
<PropertySource1>” + int_Category + “</PropertySource1>  
<PropertyName2>Published</PropertyName2>  
<PropertySource2>” + str_Published + “</PropertySource2>  
<PropertyName3>Title</PropertyName3>  
<PropertySource3>” + str_Title + “</PropertySource3>  
<PropertyName4>Body</PropertyName4>  
<PropertySource4>” + str_Body + “</PropertySource4>  
</ConfigPropertiesXml>”;  
```  

 <span data-ttu-id="af6ff-125">在此表达式中的变量将使用以下类型：</span><span class="sxs-lookup"><span data-stu-id="af6ff-125">The variables in this expression would use the following types:</span></span>  

|<span data-ttu-id="af6ff-126">变量名称</span><span class="sxs-lookup"><span data-stu-id="af6ff-126">Variable name</span></span>|<span data-ttu-id="af6ff-127">类型</span><span class="sxs-lookup"><span data-stu-id="af6ff-127">Type</span></span>|  
|-------------------|----------|  
|<span data-ttu-id="af6ff-128">int_Category</span><span class="sxs-lookup"><span data-stu-id="af6ff-128">int_Category</span></span>|<span data-ttu-id="af6ff-129">System.Int32</span><span class="sxs-lookup"><span data-stu-id="af6ff-129">System.Int32</span></span>|  
|<span data-ttu-id="af6ff-130">str_Published</span><span class="sxs-lookup"><span data-stu-id="af6ff-130">str_Published</span></span>|<span data-ttu-id="af6ff-131">System.String</span><span class="sxs-lookup"><span data-stu-id="af6ff-131">System.String</span></span>|  
|<span data-ttu-id="af6ff-132">str_Title</span><span class="sxs-lookup"><span data-stu-id="af6ff-132">str_Title</span></span>|<span data-ttu-id="af6ff-133">System.String</span><span class="sxs-lookup"><span data-stu-id="af6ff-133">System.String</span></span>|  
|<span data-ttu-id="af6ff-134">str_Body</span><span class="sxs-lookup"><span data-stu-id="af6ff-134">str_Body</span></span>|<span data-ttu-id="af6ff-135">System.String</span><span class="sxs-lookup"><span data-stu-id="af6ff-135">System.String</span></span>|  

 <span data-ttu-id="af6ff-136">这种方法创建的帖子将设置为的状态**未获批准**，这将需要的博客所有者批准之前在站点上为可见。</span><span class="sxs-lookup"><span data-stu-id="af6ff-136">A post created this way will be set to a state of **not approved**, which will require approval by the blog owner before it is visible on the site.</span></span>  

 <span data-ttu-id="af6ff-137">可以在该列表的设置页上查看列表支持的列类型。</span><span class="sxs-lookup"><span data-stu-id="af6ff-137">The supported column types for the list can be viewed on the settings page for the list.</span></span> <span data-ttu-id="af6ff-138">有关 Windows SharePoint Services 适配器支持的 Windows SharePoint Services 列类型的详细信息，请参阅[Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="af6ff-138">For more information about the Windows SharePoint Services column types that are supported by the Windows SharePoint Services adapter, see [Windows SharePoint Services Adapter Properties Reference](../core/windows-sharepoint-services-adapter-properties-reference.md).</span></span>  

## <a name="sending-to-and-receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a><span data-ttu-id="af6ff-139">向发送和接收来自 Windows SharePoint Services 4.0 Wiki 文档库</span><span class="sxs-lookup"><span data-stu-id="af6ff-139">Sending to and Receiving from a Windows SharePoint Services 4.0 Wiki Document Library</span></span>  
 <span data-ttu-id="af6ff-140">在 Windows SharePoint Services 4.0 站点中，Wiki 网站使用**Wiki 页面**文档库。</span><span class="sxs-lookup"><span data-stu-id="af6ff-140">In a Windows SharePoint Services 4.0 site, a Wiki site uses the **Wiki Pages** document library.</span></span> <span data-ttu-id="af6ff-141">Wiki 网页文档库将 Wiki 网页中的文本存储**Wiki 内容**使用的 UI 类型的列**多行文本**。</span><span class="sxs-lookup"><span data-stu-id="af6ff-141">The Wiki Pages document library stores the text of the Wiki page in a **Wiki Content** column which uses a UI type of **Multiple lines of text**.</span></span> <span data-ttu-id="af6ff-142">**多行文本**UI 类型与相关联**SPFieldType.Note** SharePoint 对象模型类型。</span><span class="sxs-lookup"><span data-stu-id="af6ff-142">The **Multiple lines of text** UI type correlates to the **SPFieldType.Note** SharePoint object model type.</span></span> <span data-ttu-id="af6ff-143">有关 Windows SharePoint Services 适配器支持的 Windows SharePoint Services 列类型的详细信息请参阅[Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="af6ff-143">For more information about the Windows SharePoint Services column types that are supported by the Windows SharePoint Services adapter see [Windows SharePoint Services Adapter Properties Reference](../core/windows-sharepoint-services-adapter-properties-reference.md).</span></span>  

### <a name="sending-to-a-windows-sharepoint-services-40-wiki-document-library"></a><span data-ttu-id="af6ff-144">将发送到 Windows SharePoint Services 4.0 Wiki 文档库</span><span class="sxs-lookup"><span data-stu-id="af6ff-144">Sending to a Windows SharePoint Services 4.0 Wiki Document Library</span></span>  
 <span data-ttu-id="af6ff-145">将消息发送给 Windows SharePoint Services 4.0 Wiki 网站，Wiki 网页的内容将存储在名为 Windows SharePoint Services 适配器上下文属性**WSS。ConfigPropertiesXml**。</span><span class="sxs-lookup"><span data-stu-id="af6ff-145">When sending messages to a Windows SharePoint Services 4.0 Wiki site, the contents of the Wiki page are stored within the Windows SharePoint Services adapter context property named **WSS.ConfigPropertiesXml**.</span></span> <span data-ttu-id="af6ff-146">若要将消息发布到 Windows SharePoint Services 4.0 Wiki 网站，可在适配器中输入以下值**传输属性**对话框中配置使用 Windows SharePoint Services 适配器的发送端口时：</span><span class="sxs-lookup"><span data-stu-id="af6ff-146">To post a message to a Windows SharePoint Services 4.0 Wiki site, enter the following values in the adapter **Transport Properties** dialog box when configuring a send port that uses the Windows SharePoint Services adapter:</span></span>  


|        <span data-ttu-id="af6ff-147">属性</span><span class="sxs-lookup"><span data-stu-id="af6ff-147">Property</span></span>        |                                                                                            <span data-ttu-id="af6ff-148">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="af6ff-148">Value</span></span>                                                                                            |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="af6ff-149">目标文件夹 URL</span><span class="sxs-lookup"><span data-stu-id="af6ff-149">Destination Folder URL</span></span> |                                                   <span data-ttu-id="af6ff-150">Wiki 网站主页相对于 SharePoint 站点，如"wikiSP"的 URL。</span><span class="sxs-lookup"><span data-stu-id="af6ff-150">URL of the Wiki site home page, relative to the SharePoint site, for example "wikiSP".</span></span>                                                    |
|  <span data-ttu-id="af6ff-151">SharePoint 站点 URL</span><span class="sxs-lookup"><span data-stu-id="af6ff-151">SharePoint Site URL</span></span>   | <span data-ttu-id="af6ff-152">Windows SharePoint Services 4.0 Wiki 网站，例如 http:// URL<em>\<servername\></em>/站点/wiki/位置*\<servername\>* 是web 服务器的实际名称的占位符。</span><span class="sxs-lookup"><span data-stu-id="af6ff-152">URL of the Windows SharePoint Services 4.0 Wiki site, for example http://<em>\<servername\></em>/sites/wiki/ where *\<servername\>* is a placeholder for the actual name of the web server.</span></span> |

 <span data-ttu-id="af6ff-153">然后将设置为值**Wiki 内容**Wiki 页面通过 WSS 中设置相应的值的属性。ConfigPropertiesXml 消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="af6ff-153">Then set the value for the **Wiki Content** property for the Wiki page by setting the corresponding value in the WSS.ConfigPropertiesXml context property of the message.</span></span> <span data-ttu-id="af6ff-154">这可以使用自定义管道或业务流程中。</span><span class="sxs-lookup"><span data-stu-id="af6ff-154">This can be done with a custom pipeline or in an orchestration.</span></span> <span data-ttu-id="af6ff-155">例如，在业务流程中的以下表达式将 WSS 中设置值。ConfigPropertiesXml Message_Out 消息上下文属性：</span><span class="sxs-lookup"><span data-stu-id="af6ff-155">For example, the following expression in an orchestration would set values in the WSS.ConfigPropertiesXml context property of the Message_Out message:</span></span>  

```  
str_Wiki = "This is a sample Wiki page entry.";  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  

 <span data-ttu-id="af6ff-156">在此表达式中的 str_Wiki 变量将使用**System.String**数据类型。</span><span class="sxs-lookup"><span data-stu-id="af6ff-156">The str_Wiki variable in this expression would use the **System.String** data type.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="af6ff-157">Windows SharePoint Services 4.0 Wiki 文档库支持版本控制，但是，BizTalk Server 2010does 的 Windows SharePoint Services 适配器不支持版本控制。</span><span class="sxs-lookup"><span data-stu-id="af6ff-157">The Windows SharePoint Services 4.0 Wiki document library supports versioning, however, the Windows SharePoint Services adapter for BizTalk Server 2010does not support versioning.</span></span> <span data-ttu-id="af6ff-158">因此，为 BizTalk Server 更新的 Windows SharePoint Services 适配器的 Wiki 网页将丢失其以前的版本。</span><span class="sxs-lookup"><span data-stu-id="af6ff-158">Therefore, Wiki pages that are updated by the Windows SharePoint Services adapter for BizTalk Server will lose their previous versions.</span></span> <span data-ttu-id="af6ff-159">鉴于此限制的是 Windows SharePoint Services 适配器接收的 BizTalk Server 和在不同的 Wiki 文档库中存档的 Wiki 页将只保留其最后一个版本，并删除所有其他版本。</span><span class="sxs-lookup"><span data-stu-id="af6ff-159">Because of this limitation, a Wiki page that is received by the Windows SharePoint Services adapter for BizTalk Server and archived in a different Wiki document library will preserve only its last version, with all other versions being deleted.</span></span>  

### <a name="receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a><span data-ttu-id="af6ff-160">接收来自 Windows SharePoint Services 4.0 Wiki 文档库</span><span class="sxs-lookup"><span data-stu-id="af6ff-160">Receiving from a Windows SharePoint Services 4.0 Wiki Document Library</span></span>  
 <span data-ttu-id="af6ff-161">接收消息时从 Windows SharePoint Services 4.0 Wiki 站点，Wiki 网页的内容将存储在名为 Windows SharePoint Services 适配器上下文属性**WSS。InPropertiesXml**。</span><span class="sxs-lookup"><span data-stu-id="af6ff-161">When receiving messages from a Windows SharePoint Services 4.0 Wiki site, the contents of the Wiki page are stored within the Windows SharePoint Services adapter context property named **WSS.InPropertiesXml**.</span></span>  

 <span data-ttu-id="af6ff-162">若要从 Windows SharePoint Services 4.0 Wiki 页接收一条消息，可在适配器中输入以下值**传输属性**对话框中配置使用 Windows SharePoint Services 适配器的接收位置时：</span><span class="sxs-lookup"><span data-stu-id="af6ff-162">To receive a message from a Windows SharePoint Services 4.0 Wiki page, enter the following values in the adapter **Transport Properties** dialog box when configuring a receive location that uses the Windows SharePoint Services adapter:</span></span>  

|<span data-ttu-id="af6ff-163">属性</span><span class="sxs-lookup"><span data-stu-id="af6ff-163">Property</span></span>|<span data-ttu-id="af6ff-164">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="af6ff-164">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="af6ff-165">SharePoint 站点 URL</span><span class="sxs-lookup"><span data-stu-id="af6ff-165">SharePoint Site URL</span></span>|<span data-ttu-id="af6ff-166">Wiki 网站主页相对于 SharePoint 站点，例如"wiki"的 URL。</span><span class="sxs-lookup"><span data-stu-id="af6ff-166">URL of the Wiki site home page, relative to the SharePoint site, for example "wiki".</span></span>|  
|<span data-ttu-id="af6ff-167">源文档库 URL</span><span class="sxs-lookup"><span data-stu-id="af6ff-167">Source Document Library URL</span></span>|<span data-ttu-id="af6ff-168">Wiki 网站主页相对于 SharePoint 站点，如"wikiRL"的 URL。</span><span class="sxs-lookup"><span data-stu-id="af6ff-168">URL of the Wiki site home page, relative to the SharePoint site, for example "wikiRL".</span></span>|  

 <span data-ttu-id="af6ff-169">然后检索 wiki 网页的内容从**Wiki 内容**节点的**WSS。InPropertiesXml**接收到消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="af6ff-169">Then retrieve the wiki page contents from the **Wiki Content** node of the **WSS.InPropertiesXml** context property of the received message.</span></span> <span data-ttu-id="af6ff-170">这可以使用自定义管道或业务流程中。</span><span class="sxs-lookup"><span data-stu-id="af6ff-170">This can be done with a custom pipeline or in an orchestration.</span></span> <span data-ttu-id="af6ff-171">例如，在下面的业务流程表达式**str_Wiki**使用的值填充变量**Wiki 内容**节点从**WSS。InPropertiesXml**上下文属性**Message_In**消息。</span><span class="sxs-lookup"><span data-stu-id="af6ff-171">For example, in the following orchestration expression, the **str_Wiki** variable is populated with the value of the **Wiki Content** node from the **WSS.InPropertiesXml** context property of the **Message_In** message.</span></span> <span data-ttu-id="af6ff-172">然后，将**Wiki 内容**属性的**WSS。ConfigPropertiesXml**上下文属性**Message_Out**消息设置的值为**str_Wiki**变量：</span><span class="sxs-lookup"><span data-stu-id="af6ff-172">Then, the **Wiki Content** property of the **WSS.ConfigPropertiesXml** context property of the **Message_Out** message is set to the value of the **str_Wiki** variable:</span></span>  

```  
str_PropertiesXml = Message_In(WSS.InPropertiesXml);  
doc = doc.LoadXml(str_PropertiesXml);  
node = doc.SelectSingleNode("InPropertiesXml/Property[@name='Wiki Content']);  
str_Wiki = node.InnerText;  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  

 <span data-ttu-id="af6ff-173">在此表达式中的变量将使用以下类型：</span><span class="sxs-lookup"><span data-stu-id="af6ff-173">The variables in this expression would use the following types:</span></span>  

|<span data-ttu-id="af6ff-174">变量名称</span><span class="sxs-lookup"><span data-stu-id="af6ff-174">Variable name</span></span>|<span data-ttu-id="af6ff-175">类型</span><span class="sxs-lookup"><span data-stu-id="af6ff-175">Type</span></span>|  
|-------------------|----------|  
|<span data-ttu-id="af6ff-176">str_PropertiesXml</span><span class="sxs-lookup"><span data-stu-id="af6ff-176">str_PropertiesXml</span></span>|<span data-ttu-id="af6ff-177">System.Xml.XmlDocument</span><span class="sxs-lookup"><span data-stu-id="af6ff-177">System.Xml.XmlDocument</span></span>|  
|<span data-ttu-id="af6ff-178">doc</span><span class="sxs-lookup"><span data-stu-id="af6ff-178">doc</span></span>|<span data-ttu-id="af6ff-179">System.Xml.XmlDocument</span><span class="sxs-lookup"><span data-stu-id="af6ff-179">System.Xml.XmlDocument</span></span>|  
|<span data-ttu-id="af6ff-180">节点</span><span class="sxs-lookup"><span data-stu-id="af6ff-180">node</span></span>|<span data-ttu-id="af6ff-181">System.Xml.XmlNode</span><span class="sxs-lookup"><span data-stu-id="af6ff-181">System.Xml.XmlNode</span></span>|  
|<span data-ttu-id="af6ff-182">str_Wiki</span><span class="sxs-lookup"><span data-stu-id="af6ff-182">str_Wiki</span></span>|<span data-ttu-id="af6ff-183">System.String</span><span class="sxs-lookup"><span data-stu-id="af6ff-183">System.String</span></span>|  

## <a name="see-also"></a><span data-ttu-id="af6ff-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="af6ff-184">See Also</span></span>  
 [<span data-ttu-id="af6ff-185">Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="af6ff-185">Windows SharePoint Services Adapter</span></span>](../core/windows-sharepoint-services-adapter.md)