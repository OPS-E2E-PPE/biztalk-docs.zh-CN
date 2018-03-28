---
title: 发布时的注意事项 Web 服务 |Microsoft 文档
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 825a16555f0b0c82282ae4d85592567d2a19c073
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="considerations-when-publishing-web-services"></a><span data-ttu-id="d0953-102">发布 Web Services 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="d0953-102">Considerations When Publishing Web Services</span></span>
<span data-ttu-id="d0953-103">本主题介绍你在发布 Web Services 之前应考虑的信息。</span><span class="sxs-lookup"><span data-stu-id="d0953-103">This topic provides information that you should consider before you publish your Web services.</span></span>  
  
## <a name="publishing-schemas-and-the-include-element"></a><span data-ttu-id="d0953-104">发布架构和 include 元素</span><span class="sxs-lookup"><span data-stu-id="d0953-104">Publishing schemas and the include element</span></span>  
 <span data-ttu-id="d0953-105">有几个方案中，包含的架构 **包括** 元素不能发布，作为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="d0953-105">There are a few scenarios where schemas that contain the **include** element cannot be published as a Web service.</span></span> <span data-ttu-id="d0953-106">在你完成 BizTalk Web Services 发布向导时，会出现错误。</span><span class="sxs-lookup"><span data-stu-id="d0953-106">An error will occur when you complete the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="d0953-107">包含如下这些限制：</span><span class="sxs-lookup"><span data-stu-id="d0953-107">These restrictions include the following:</span></span>  
  
-   <span data-ttu-id="d0953-108">圆形包括 (包含的架构具有 **包括** 到包括架构元素)</span><span class="sxs-lookup"><span data-stu-id="d0953-108">Circular includes (the included schema has an **include** element to the including schema)</span></span>  
  
-   <span data-ttu-id="d0953-109">无法解析 **schemaLocation** 属性会导致错误</span><span class="sxs-lookup"><span data-stu-id="d0953-109">An unresolved **schemaLocation** attribute will cause an error</span></span>  
  
 <span data-ttu-id="d0953-110">有关限制的详细信息包含元素，请参阅"包括元素绑定支持"，网址[ http://go.microsoft.com/fwlink/?LinkId=62312 ](http://go.microsoft.com/fwlink/?LinkId=62312)。</span><span class="sxs-lookup"><span data-stu-id="d0953-110">For more information about the limitation of include element, see "Include Element Binding Support" at [http://go.microsoft.com/fwlink/?LinkId=62312](http://go.microsoft.com/fwlink/?LinkId=62312).</span></span>  
  
## <a name="publishing-schemas-and-the-import-element"></a><span data-ttu-id="d0953-111">发布架构和 import 元素</span><span class="sxs-lookup"><span data-stu-id="d0953-111">Publishing schemas and the import element</span></span>  
 <span data-ttu-id="d0953-112">BizTalk Web Services 发布向导与 .NET Framework 中包含的 XSD.exe 具有相同的限制。</span><span class="sxs-lookup"><span data-stu-id="d0953-112">BizTalk Web Services Publishing Wizard has the same limitation as XSD.exe included in .NET Framework.</span></span> <span data-ttu-id="d0953-113">详细信息，请参阅"导入元素绑定支持"在[ http://go.microsoft.com/fwlink/?LinkId=62311 ](http://go.microsoft.com/fwlink/?LinkId=62311)。</span><span class="sxs-lookup"><span data-stu-id="d0953-113">For more information, see "Import Element Binding Support" at [http://go.microsoft.com/fwlink/?LinkId=62311](http://go.microsoft.com/fwlink/?LinkId=62311).</span></span>  
  
## <a name="publishing-schemas-and-the-redefine-element"></a><span data-ttu-id="d0953-114">发布架构和 redefine 元素</span><span class="sxs-lookup"><span data-stu-id="d0953-114">Publishing schemas and the redefine element</span></span>  
 <span data-ttu-id="d0953-115">BizTalk Web Services 发布向导与 .NET Framework 中包含的 XSD.exe 具有相同的限制。</span><span class="sxs-lookup"><span data-stu-id="d0953-115">BizTalk Web Services Publishing Wizard has the same limitation as XSD.exe included in .NET Framework.</span></span> <span data-ttu-id="d0953-116">详细信息，请参阅"重新定义元素绑定支持"在[ http://go.microsoft.com/fwlink/?LinkId=62313 ](http://go.microsoft.com/fwlink/?LinkId=62313)。</span><span class="sxs-lookup"><span data-stu-id="d0953-116">For more information, see "Redefine Element Binding Support" at [http://go.microsoft.com/fwlink/?LinkId=62313](http://go.microsoft.com/fwlink/?LinkId=62313).</span></span>  
  
## <a name="publishing-schemas-that-specify-values-for-minoccurs-or-maxoccurs-attributes"></a><span data-ttu-id="d0953-117">发布指定了 minOccurs 或 maxOccurs 属性值的架构</span><span class="sxs-lookup"><span data-stu-id="d0953-117">Publishing schemas that specify values for minOccurs or maxOccurs attributes</span></span>  
 <span data-ttu-id="d0953-118">如果发布包含架构 **minOccurs** 或 **maxOccurs** 具有特定值的属性，这些值可能是由已发布的 Web 服务公开的架构中不同。</span><span class="sxs-lookup"><span data-stu-id="d0953-118">If you publish a schema that contains **minOccurs** or **maxOccurs** attributes with specific values, these values may be different in schema exposed by the published Web service.</span></span> <span data-ttu-id="d0953-119">通常，所有 minOccurs 属性被转换为 0 (minOccurs=0) 而 maxOccurs 属性则转换为 1 或 unbounded（maxOccurs=1 或 maxOccurs=unbounded）。</span><span class="sxs-lookup"><span data-stu-id="d0953-119">As a general rule of thumb, all minOccurs attributes are converted to 0 (minOccurs=0) and maxOccurs attributes are converted to either 1 or unbounded (maxOccurs=1 or maxOccurs=unbounded).</span></span>  
  
## <a name="publishing-envelope-schemas"></a><span data-ttu-id="d0953-120">发布信封架构</span><span class="sxs-lookup"><span data-stu-id="d0953-120">Publishing envelope schemas</span></span>  
 <span data-ttu-id="d0953-121">如果你有一个要发布为 Web Services 的信封架构，则需要手动修改生成的 Web 项目。</span><span class="sxs-lookup"><span data-stu-id="d0953-121">If you have an envelop schema that you are publishing as a Web service, you need to manually modify the generated Web project.</span></span>  
  
#### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a><span data-ttu-id="d0953-122">为信封架构修改生成的 Web 项目</span><span class="sxs-lookup"><span data-stu-id="d0953-122">To modify the generated Web project for envelope schemas</span></span>  
  
1.  <span data-ttu-id="d0953-123">打开 <`myWebService`>.asmx.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="d0953-123">Open the <`myWebService`>.asmx.cs file.</span></span>  
  
2.  <span data-ttu-id="d0953-124">编辑文件，并更改 `bodyTypeAssemblyQualifiedName = <dll.name.version.>` 到 `bodyTypeAssemblyQualifiedName = null`。</span><span class="sxs-lookup"><span data-stu-id="d0953-124">Edit the file and change `bodyTypeAssemblyQualifiedName = <dll.name.version.>` to `bodyTypeAssemblyQualifiedName = null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0953-125">如果先前的 .dll 文件仍然在 ASPNET 辅助进程中，你可能需要重置 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="d0953-125">You may need to reset Internet Information Services (IIS) if the previous .dll file is still in the ASPNET worker process.</span></span>  
  
## <a name="web-service-and-web-method-attributes"></a><span data-ttu-id="d0953-126">Web Services 和 Web 方法属性</span><span class="sxs-lookup"><span data-stu-id="d0953-126">Web service and Web method attributes</span></span>  
 <span data-ttu-id="d0953-127">BizTalk Web Services 发布向导不允许您自定义在 ASP.NET 中使用的 Web Services 或 Web 方法属性。</span><span class="sxs-lookup"><span data-stu-id="d0953-127">The BizTalk Web Services Publishing Wizard does not allow you to customize the Web service or Web method attributes you use in ASP.NET.</span></span> <span data-ttu-id="d0953-128">某些属性会基于该向导提供的信息自动进行设置。</span><span class="sxs-lookup"><span data-stu-id="d0953-128">Some attributes are automatically set based upon information that the wizard provides.</span></span> <span data-ttu-id="d0953-129">该向导不使用其他属性。</span><span class="sxs-lookup"><span data-stu-id="d0953-129">The wizard does not use the other attributes.</span></span>  
  
 <span data-ttu-id="d0953-130">修改现有属性或者向 BizTalk Web Services 发布向导生成的 Web Services 添加新属性可能导致该 Web Services 无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="d0953-130">Modifying the existing attributes or adding new attributes to Web services that the BizTalk Web Services Publishing Wizard generates may cause the Web service to function incorrectly.</span></span>  
  
 <span data-ttu-id="d0953-131">有关 Web 服务和 Web 方法特性的详细信息，请参阅 **WebServiceAttribute** 和 **WebMethodAttribute** .NET Framework SDK 文档中的类。</span><span class="sxs-lookup"><span data-stu-id="d0953-131">For more information about Web services and Web method attributes, see the **WebServiceAttribute** and **WebMethodAttribute** classes in the .NET Framework SDK documentation.</span></span>  
  
## <a name="web-method-required"></a><span data-ttu-id="d0953-132">必需的 Web 方法</span><span class="sxs-lookup"><span data-stu-id="d0953-132">Web method required</span></span>  
 <span data-ttu-id="d0953-133">Web Services 必须具有至少一个 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="d0953-133">A Web service must have at least one Web method.</span></span> <span data-ttu-id="d0953-134">如果不是至少具有一个 Web 方法，端口类型将不创建其操作。</span><span class="sxs-lookup"><span data-stu-id="d0953-134">Without at least one Web method, port types will not have their operations created.</span></span> <span data-ttu-id="d0953-135">XLANG/s 不支持没有操作的端口类型。</span><span class="sxs-lookup"><span data-stu-id="d0953-135">XLANG/s does not support port types that do not have operations.</span></span>  
  
## <a name="dbcs-character-support"></a><span data-ttu-id="d0953-136">DBCS 字符支持</span><span class="sxs-lookup"><span data-stu-id="d0953-136">DBCS character support</span></span>  
 <span data-ttu-id="d0953-137">Web Services 不支持 Chinese/Japanese/Korean (CJK) Unified Ideograph Extension A 字符。</span><span class="sxs-lookup"><span data-stu-id="d0953-137">Web services do not support Chinese/Japanese/Korean (CJK) Unified Ideograph Extension A characters.</span></span>  
  
## <a name="republishing-web-services-using-the-biztalk-web-services-publishing-wizard"></a><span data-ttu-id="d0953-138">使用 Web Services 发布向导重新发布 Web Services</span><span class="sxs-lookup"><span data-stu-id="d0953-138">Republishing Web services using the BizTalk Web Services Publishing Wizard</span></span>  
 <span data-ttu-id="d0953-139">可以使用 BizTalk Web Services 发布向导重新发布已发布的 Web Services。</span><span class="sxs-lookup"><span data-stu-id="d0953-139">You can use the BizTalk Web Services Publishing Wizard to republish a published Web service.</span></span> <span data-ttu-id="d0953-140">上 **Web * * * 服务 * * * 项目** 页上，你可以选择 **覆盖 * * * Web * * * 服务** 选项。</span><span class="sxs-lookup"><span data-stu-id="d0953-140">On the **Web****Service****Project** page, you can select the **Overwrite****Web****Service** option.</span></span>  
  
 <span data-ttu-id="d0953-141">该向导不存储先前所用的设置。</span><span class="sxs-lookup"><span data-stu-id="d0953-141">The wizard does not store previously used settings.</span></span> <span data-ttu-id="d0953-142">如果在重新运行向导时更改了设置，使用（调用）已发布的 Web Services 的任何 Web 客户端都可能失败。</span><span class="sxs-lookup"><span data-stu-id="d0953-142">If you make changes in the settings when you rerun the wizard, any Web clients that consume (call) the published Web service may fail.</span></span> <span data-ttu-id="d0953-143">你应该更新使用（调用）某个重新发布的 Web Services 的任何客户端的 Web 引用。</span><span class="sxs-lookup"><span data-stu-id="d0953-143">You should update the Web references of any clients that consume (call) a republished Web service.</span></span>  
  
## <a name="clients-of-published-web-services-may-not-receive-server-script-timeout-errors"></a><span data-ttu-id="d0953-144">已发布 Web Services 的客户端可能不会收到服务器脚本超时错误。</span><span class="sxs-lookup"><span data-stu-id="d0953-144">Clients of published Web services may not receive Server script timeout errors</span></span>  
 <span data-ttu-id="d0953-145">Web 服务使用 Web 服务发布向导在生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]脚本超时值为默认配置是**110**秒。</span><span class="sxs-lookup"><span data-stu-id="d0953-145">Web services generated with the Web Services Publishing Wizard in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are configured by default with a script timeout value of **110** seconds.</span></span> <span data-ttu-id="d0953-146">这是 .NET Framework 的默认值。</span><span class="sxs-lookup"><span data-stu-id="d0953-146">This is the default value for the .NET Framework.</span></span> <span data-ttu-id="d0953-147">**HttpServerUtility.ScriptTimeout** 属性。</span><span class="sxs-lookup"><span data-stu-id="d0953-147">**HttpServerUtility.ScriptTimeout** property.</span></span> <span data-ttu-id="d0953-148">使用.NET Framework 的 web 客户端配置默认情况下，请求超时值为 **100** 秒。</span><span class="sxs-lookup"><span data-stu-id="d0953-148">Web clients that use .NET Framework are configured by default with a request timeout value of **100** seconds.</span></span> <span data-ttu-id="d0953-149">这是.NET Framework 的默认值 **HttpWebRequest.Timeout** 属性。</span><span class="sxs-lookup"><span data-stu-id="d0953-149">This is the default value for the .NET Framework **HttpWebRequest.Timeout** property.</span></span>  
  
 <span data-ttu-id="d0953-150">如果使用 .NET framework 的 Web 客户端调用某个使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services 发布向导生成的 Web Services，客户端可能无法收到服务器脚本超时错误，因为默认情况下会首先发生客户端请求超时。</span><span class="sxs-lookup"><span data-stu-id="d0953-150">If Web clients that use .NET framework are calling a Web Service generated with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services Publishing Wizard, it is possible that the client cannot receive server script timeout errors because the client request timeout occurs first by default.</span></span> <span data-ttu-id="d0953-151">若要解决该问题，可执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="d0953-151">To resolve this problem you can do one of the following:</span></span>  
  
-   <span data-ttu-id="d0953-152">客户端请求超时增加到大于服务器脚本超时的值通过增加值 **HttpWebRequest.Timeout** 客户端上的属性。</span><span class="sxs-lookup"><span data-stu-id="d0953-152">Increase the client request timeout to a value greater than the server script timeout by increasing the value for the **HttpWebRequest.Timeout** property on the client.</span></span>  
  
-   <span data-ttu-id="d0953-153">通过减少的值减小为小于客户端请求超时的值的服务器脚本超时 **HttpServerUtility.ScriptTimeout** 服务器上的属性。</span><span class="sxs-lookup"><span data-stu-id="d0953-153">Reduce the server script timeout to a value less than the client request timeout by reducing the value for the **HttpServerUtility.ScriptTimeout** property on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0953-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0953-154">See Also</span></span>  
 [<span data-ttu-id="d0953-155">发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="d0953-155">Publishing Web Services</span></span>](../core/publishing-web-services.md)