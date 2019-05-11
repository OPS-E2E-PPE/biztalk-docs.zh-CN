---
title: Web 服务发布时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, planning
- Web services, schemas
- schemas, Web services
ms.assetid: 3ace0260-a1cb-4e59-a820-36ee7d5cceda
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72d45e269d091c2c39b44e260c10a96a3895706e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390338"
---
# <a name="considerations-when-publishing-web-services"></a><span data-ttu-id="46591-102">发布 Web 服务时的注意事项</span><span class="sxs-lookup"><span data-stu-id="46591-102">Considerations When Publishing Web Services</span></span>
<span data-ttu-id="46591-103">本主题提供信息发布你的 Web 服务之前，应考虑。</span><span class="sxs-lookup"><span data-stu-id="46591-103">This topic provides information that you should consider before you publish your Web services.</span></span>  
  
## <a name="publishing-schemas-and-the-include-element"></a><span data-ttu-id="46591-104">发布架构和 include 元素</span><span class="sxs-lookup"><span data-stu-id="46591-104">Publishing schemas and the include element</span></span>  
 <span data-ttu-id="46591-105">有几种方案其中所包含的架构**包括**元素不能发布为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="46591-105">There are a few scenarios where schemas that contain the **include** element cannot be published as a Web service.</span></span> <span data-ttu-id="46591-106">完成 BizTalk Web Services 发布向导时，将会出错。</span><span class="sxs-lookup"><span data-stu-id="46591-106">An error will occur when you complete the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="46591-107">这些限制包括：</span><span class="sxs-lookup"><span data-stu-id="46591-107">These restrictions include the following:</span></span>  
  
- <span data-ttu-id="46591-108">循环包含 (包含的架构具有**包括**包含架构的元素)</span><span class="sxs-lookup"><span data-stu-id="46591-108">Circular includes (the included schema has an **include** element to the including schema)</span></span>  
  
- <span data-ttu-id="46591-109">无法解析**schemaLocation**属性会导致错误</span><span class="sxs-lookup"><span data-stu-id="46591-109">An unresolved **schemaLocation** attribute will cause an error</span></span>  
  
  <span data-ttu-id="46591-110">有关限制的详细信息包括元素，请参阅"Include 元素绑定支持"，网址[ http://go.microsoft.com/fwlink/?LinkId=62312 ](http://go.microsoft.com/fwlink/?LinkId=62312)。</span><span class="sxs-lookup"><span data-stu-id="46591-110">For more information about the limitation of include element, see "Include Element Binding Support" at [http://go.microsoft.com/fwlink/?LinkId=62312](http://go.microsoft.com/fwlink/?LinkId=62312).</span></span>  
  
## <a name="publishing-schemas-and-the-import-element"></a><span data-ttu-id="46591-111">发布架构和导入元素</span><span class="sxs-lookup"><span data-stu-id="46591-111">Publishing schemas and the import element</span></span>  
 <span data-ttu-id="46591-112">BizTalk Web Services 发布向导已在.NET Framework 中包含的 XSD.exe 相同的限制。</span><span class="sxs-lookup"><span data-stu-id="46591-112">BizTalk Web Services Publishing Wizard has the same limitation as XSD.exe included in .NET Framework.</span></span> <span data-ttu-id="46591-113">有关详细信息，请参阅"导入元素绑定支持"网址[ http://go.microsoft.com/fwlink/?LinkId=62311 ](http://go.microsoft.com/fwlink/?LinkId=62311)。</span><span class="sxs-lookup"><span data-stu-id="46591-113">For more information, see "Import Element Binding Support" at [http://go.microsoft.com/fwlink/?LinkId=62311](http://go.microsoft.com/fwlink/?LinkId=62311).</span></span>  
  
## <a name="publishing-schemas-and-the-redefine-element"></a><span data-ttu-id="46591-114">发布架构和 redefine 元素</span><span class="sxs-lookup"><span data-stu-id="46591-114">Publishing schemas and the redefine element</span></span>  
 <span data-ttu-id="46591-115">BizTalk Web Services 发布向导已在.NET Framework 中包含的 XSD.exe 相同的限制。</span><span class="sxs-lookup"><span data-stu-id="46591-115">BizTalk Web Services Publishing Wizard has the same limitation as XSD.exe included in .NET Framework.</span></span> <span data-ttu-id="46591-116">详细信息，请参阅"Redefine 元素绑定支持"处[ http://go.microsoft.com/fwlink/?LinkId=62313 ](http://go.microsoft.com/fwlink/?LinkId=62313)。</span><span class="sxs-lookup"><span data-stu-id="46591-116">For more information, see "Redefine Element Binding Support" at [http://go.microsoft.com/fwlink/?LinkId=62313](http://go.microsoft.com/fwlink/?LinkId=62313).</span></span>  
  
## <a name="publishing-schemas-that-specify-values-for-minoccurs-or-maxoccurs-attributes"></a><span data-ttu-id="46591-117">指定的 minOccurs 或 maxOccurs 属性值的发布架构</span><span class="sxs-lookup"><span data-stu-id="46591-117">Publishing schemas that specify values for minOccurs or maxOccurs attributes</span></span>  
 <span data-ttu-id="46591-118">如果发布包含的架构**minOccurs**或**maxOccurs**具有特定值的属性，这些值可能是由已发布的 Web 服务公开的架构中不同。</span><span class="sxs-lookup"><span data-stu-id="46591-118">If you publish a schema that contains **minOccurs** or **maxOccurs** attributes with specific values, these values may be different in schema exposed by the published Web service.</span></span> <span data-ttu-id="46591-119">作为常规经验，所有 minOccurs 属性都转换为 0 (minOccurs = 0) 而 maxOccurs 属性则都转换为 1 或不受限制 (maxOccurs = 1 或 maxOccurs = unbounded)。</span><span class="sxs-lookup"><span data-stu-id="46591-119">As a general rule of thumb, all minOccurs attributes are converted to 0 (minOccurs=0) and maxOccurs attributes are converted to either 1 or unbounded (maxOccurs=1 or maxOccurs=unbounded).</span></span>  
  
## <a name="publishing-envelope-schemas"></a><span data-ttu-id="46591-120">发布信封架构</span><span class="sxs-lookup"><span data-stu-id="46591-120">Publishing envelope schemas</span></span>  
 <span data-ttu-id="46591-121">如果必须要发布为 Web 服务的信封架构，您需要手动修改生成的 Web 项目。</span><span class="sxs-lookup"><span data-stu-id="46591-121">If you have an envelop schema that you are publishing as a Web service, you need to manually modify the generated Web project.</span></span>  
  
#### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a><span data-ttu-id="46591-122">若要修改的信封架构生成的 Web 项目</span><span class="sxs-lookup"><span data-stu-id="46591-122">To modify the generated Web project for envelope schemas</span></span>  
  
1.  <span data-ttu-id="46591-123">打开 <`myWebService`>。 asmx.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="46591-123">Open the <`myWebService`>.asmx.cs file.</span></span>  
  
2.  <span data-ttu-id="46591-124">编辑文件，并更改`bodyTypeAssemblyQualifiedName = <dll.name.version.>`到`bodyTypeAssemblyQualifiedName = null`。</span><span class="sxs-lookup"><span data-stu-id="46591-124">Edit the file and change `bodyTypeAssemblyQualifiedName = <dll.name.version.>` to `bodyTypeAssemblyQualifiedName = null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46591-125">您可能需要重置 Internet 信息服务 (IIS)，如果先前的.dll 文件仍然在 ASPNET 辅助进程中。</span><span class="sxs-lookup"><span data-stu-id="46591-125">You may need to reset Internet Information Services (IIS) if the previous .dll file is still in the ASPNET worker process.</span></span>  
  
## <a name="web-service-and-web-method-attributes"></a><span data-ttu-id="46591-126">Web 服务和 Web 方法属性</span><span class="sxs-lookup"><span data-stu-id="46591-126">Web service and Web method attributes</span></span>  
 <span data-ttu-id="46591-127">BizTalk Web Services 发布向导不允许你自定义 Web 服务或 Web 方法属性在 ASP.NET 中使用。</span><span class="sxs-lookup"><span data-stu-id="46591-127">The BizTalk Web Services Publishing Wizard does not allow you to customize the Web service or Web method attributes you use in ASP.NET.</span></span> <span data-ttu-id="46591-128">某些属性会自动设置基于该向导提供的信息。</span><span class="sxs-lookup"><span data-stu-id="46591-128">Some attributes are automatically set based upon information that the wizard provides.</span></span> <span data-ttu-id="46591-129">该向导不使用其他属性。</span><span class="sxs-lookup"><span data-stu-id="46591-129">The wizard does not use the other attributes.</span></span>  
  
 <span data-ttu-id="46591-130">修改现有属性或将新属性添加到 BizTalk Web Services 发布向导生成的 Web 服务可能会导致 Web 服务无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="46591-130">Modifying the existing attributes or adding new attributes to Web services that the BizTalk Web Services Publishing Wizard generates may cause the Web service to function incorrectly.</span></span>  
  
 <span data-ttu-id="46591-131">有关 Web 服务和 Web 方法属性的详细信息，请参阅**WebServiceAttribute**并**WebMethodAttribute**的.NET Framework SDK 文档中的类。</span><span class="sxs-lookup"><span data-stu-id="46591-131">For more information about Web services and Web method attributes, see the **WebServiceAttribute** and **WebMethodAttribute** classes in the .NET Framework SDK documentation.</span></span>  
  
## <a name="web-method-required"></a><span data-ttu-id="46591-132">所需的 web 方法</span><span class="sxs-lookup"><span data-stu-id="46591-132">Web method required</span></span>  
 <span data-ttu-id="46591-133">Web 服务必须具有至少一个 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="46591-133">A Web service must have at least one Web method.</span></span> <span data-ttu-id="46591-134">如果没有至少一个 Web 方法，端口类型将不会创建其操作。</span><span class="sxs-lookup"><span data-stu-id="46591-134">Without at least one Web method, port types will not have their operations created.</span></span> <span data-ttu-id="46591-135">XLANG/s 不支持没有操作的端口类型。</span><span class="sxs-lookup"><span data-stu-id="46591-135">XLANG/s does not support port types that do not have operations.</span></span>  
  
## <a name="dbcs-character-support"></a><span data-ttu-id="46591-136">DBCS 字符支持</span><span class="sxs-lookup"><span data-stu-id="46591-136">DBCS character support</span></span>  
 <span data-ttu-id="46591-137">Web 服务不支持中文/Japanese/Korean (CJK) Unified Ideograph Extension A 字符。</span><span class="sxs-lookup"><span data-stu-id="46591-137">Web services do not support Chinese/Japanese/Korean (CJK) Unified Ideograph Extension A characters.</span></span>  
  
## <a name="republishing-web-services-using-the-biztalk-web-services-publishing-wizard"></a><span data-ttu-id="46591-138">使用 BizTalk Web Services 发布向导重新发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="46591-138">Republishing Web services using the BizTalk Web Services Publishing Wizard</span></span>  
 <span data-ttu-id="46591-139">可以使用 BizTalk Web Services 发布向导重新发布已发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="46591-139">You can use the BizTalk Web Services Publishing Wizard to republish a published Web service.</span></span> <span data-ttu-id="46591-140">上**Web**<strong>服务</strong>**项目**页上，可以选择**覆盖**<strong>Web</strong> **服务**选项。</span><span class="sxs-lookup"><span data-stu-id="46591-140">On the **Web**<strong>Service</strong>**Project** page, you can select the **Overwrite**<strong>Web</strong>**Service** option.</span></span>  
  
 <span data-ttu-id="46591-141">该向导将执行不存储先前所用的设置。</span><span class="sxs-lookup"><span data-stu-id="46591-141">The wizard does not store previously used settings.</span></span> <span data-ttu-id="46591-142">如果在设置中进行更改时重新运行该向导，使用 （调用） 的任何 Web 客户端可能会失败的已发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="46591-142">If you make changes in the settings when you rerun the wizard, any Web clients that consume (call) the published Web service may fail.</span></span> <span data-ttu-id="46591-143">应使用 （调用） 的任何客户端的 Web 引用更新重新发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="46591-143">You should update the Web references of any clients that consume (call) a republished Web service.</span></span>  
  
## <a name="clients-of-published-web-services-may-not-receive-server-script-timeout-errors"></a><span data-ttu-id="46591-144">已发布 Web services 的客户端可能不会收到服务器脚本超时错误</span><span class="sxs-lookup"><span data-stu-id="46591-144">Clients of published Web services may not receive Server script timeout errors</span></span>  
 <span data-ttu-id="46591-145">Web 服务使用 Web Services 发布向导中生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]默认情况下，使用的脚本超时值配置**110**秒。</span><span class="sxs-lookup"><span data-stu-id="46591-145">Web services generated with the Web Services Publishing Wizard in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are configured by default with a script timeout value of **110** seconds.</span></span> <span data-ttu-id="46591-146">这是.NET Framework 的默认值。</span><span class="sxs-lookup"><span data-stu-id="46591-146">This is the default value for the .NET Framework.</span></span> <span data-ttu-id="46591-147">**HttpServerUtility.ScriptTimeout**属性。</span><span class="sxs-lookup"><span data-stu-id="46591-147">**HttpServerUtility.ScriptTimeout** property.</span></span> <span data-ttu-id="46591-148">使用.NET Framework 的 web 客户端配置请求超时值为默认情况下**100**秒。</span><span class="sxs-lookup"><span data-stu-id="46591-148">Web clients that use .NET Framework are configured by default with a request timeout value of **100** seconds.</span></span> <span data-ttu-id="46591-149">这是.NET Framework 的默认值**HttpWebRequest.Timeout**属性。</span><span class="sxs-lookup"><span data-stu-id="46591-149">This is the default value for the .NET Framework **HttpWebRequest.Timeout** property.</span></span>  
  
 <span data-ttu-id="46591-150">如果使用.NET framework 的 Web 客户端调用 Web 服务生成具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web Services 发布向导，它是可能在客户端无法收到服务器脚本超时错误，因为默认情况下会首先发生客户端请求超时。</span><span class="sxs-lookup"><span data-stu-id="46591-150">If Web clients that use .NET framework are calling a Web Service generated with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services Publishing Wizard, it is possible that the client cannot receive server script timeout errors because the client request timeout occurs first by default.</span></span> <span data-ttu-id="46591-151">若要解决此问题可以执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="46591-151">To resolve this problem you can do one of the following:</span></span>  
  
-   <span data-ttu-id="46591-152">通过增加的值来提高客户端请求超时值大于服务器脚本超时**HttpWebRequest.Timeout**客户端上的属性。</span><span class="sxs-lookup"><span data-stu-id="46591-152">Increase the client request timeout to a value greater than the server script timeout by increasing the value for the **HttpWebRequest.Timeout** property on the client.</span></span>  
  
-   <span data-ttu-id="46591-153">降低服务器脚本超时小于客户端请求超时的值的值**HttpServerUtility.ScriptTimeout**在服务器上的属性。</span><span class="sxs-lookup"><span data-stu-id="46591-153">Reduce the server script timeout to a value less than the client request timeout by reducing the value for the **HttpServerUtility.ScriptTimeout** property on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46591-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="46591-154">See Also</span></span>  
 [<span data-ttu-id="46591-155">发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="46591-155">Publishing Web Services</span></span>](../core/publishing-web-services.md)