---
title: "规划使用 Web 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24863069-929b-4b0b-9643-073965fb5532
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4a13151a5dd76b20b70872b963dc6a688370444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-consuming-web-services"></a><span data-ttu-id="cfc42-102">规划使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="cfc42-102">Planning for Consuming Web Services</span></span>
<span data-ttu-id="cfc42-103">规划 Web 服务可以划分为两个类别，规划用于发布 Web 服务和规划使用 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="cfc42-103">Planning for Web services can be divided into two categories, planning for publishing Web services and planning for consuming Web services.</span></span> <span data-ttu-id="cfc42-104">本主题介绍有关使用 Web 服务的注意事项。</span><span class="sxs-lookup"><span data-stu-id="cfc42-104">This topic describes the considerations for consuming Web services.</span></span> <span data-ttu-id="cfc42-105">有关发布 Web 服务的信息，请参阅[规划发布 Web Services1](../technical-guides/planning-for-publishing-web-services1.md)。</span><span class="sxs-lookup"><span data-stu-id="cfc42-105">For information about publishing Web services, see [Planning for Publishing Web Services1](../technical-guides/planning-for-publishing-web-services1.md).</span></span>  
  
 <span data-ttu-id="cfc42-106">创建你的计划，请记住以下：</span><span class="sxs-lookup"><span data-stu-id="cfc42-106">Keep the following in mind as you create your plan:</span></span>  
  
-   <span data-ttu-id="cfc42-107">**在参数名称中使用两个下划线字符**</span><span class="sxs-lookup"><span data-stu-id="cfc42-107">**Using Two Underscore Characters in a Parameter Name**</span></span>  
  
     <span data-ttu-id="cfc42-108">Web 方法的参数名称不能以“__”（两条下划线）开始。</span><span class="sxs-lookup"><span data-stu-id="cfc42-108">Parameter names for Web methods cannot begin with "__" (two underscore characters).</span></span> <span data-ttu-id="cfc42-109">以两条下划线开始的名称可以创建 XLANG/s 不支持（无法使用）的 Web 消息部分。</span><span class="sxs-lookup"><span data-stu-id="cfc42-109">Names that begin with two underscore characters may create Web message parts that are unsupported (unusable) by XLANG/s.</span></span>  
  
-   <span data-ttu-id="cfc42-110">**任何元素和 anyAttribute Web 方法中不支持的特性**</span><span class="sxs-lookup"><span data-stu-id="cfc42-110">**The Any Element and the anyAttribute Attributes Are Not Supported in Web Methods**</span></span>  
  
     <span data-ttu-id="cfc42-111">不能使用**任何**元素或**anyAttribute** Web 方法的架构中的属性。</span><span class="sxs-lookup"><span data-stu-id="cfc42-111">You cannot use the **any** element or **anyAttribute** attribute in the schema for a Web method.</span></span>  
  
-   <span data-ttu-id="cfc42-112">**使用 XLANG/s 关键字**</span><span class="sxs-lookup"><span data-stu-id="cfc42-112">**Using XLANG/s Keywords**</span></span>  
  
     <span data-ttu-id="cfc42-113">Web 服务名称或 Web 方法名称不能为 XLANG/s 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="cfc42-113">A Web service name or a Web method name cannot be a keyword in an XLANG/s.</span></span> <span data-ttu-id="cfc42-114">如果在使用中的 Web 服务名称或 Web 方法名称 XLANG/s 关键字，你将收到编译错误，当你将添加 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="cfc42-114">If you use an XLANG/s keyword in the Web service name or Web method name, you will get a compilation error when you add the Web service.</span></span> <span data-ttu-id="cfc42-115">有关保留字 XLANG/s 语言的列表，请参阅[XLANG/s 保留字](http://go.microsoft.com/fwlink/?LinkId=155765)(http://go.microsoft.com/fwlink/?LinkId=155765)。</span><span class="sxs-lookup"><span data-stu-id="cfc42-115">For a list of reserved words for the XLANG/s language, see the [XLANG/s Reserved Words](http://go.microsoft.com/fwlink/?LinkId=155765) (http://go.microsoft.com/fwlink/?LinkId=155765).</span></span>  
  
-   <span data-ttu-id="cfc42-116">**参数类型的所需的 XLANG s 支持**</span><span class="sxs-lookup"><span data-stu-id="cfc42-116">**Required XLANG/s Support for Parameter Types**</span></span>  
  
     <span data-ttu-id="cfc42-117">使用非 XLANG/s 支持的 Web 方法参数类型将导致编译错误。</span><span class="sxs-lookup"><span data-stu-id="cfc42-117">Using non-XLANG/s supported Web method parameter types will cause compilation errors.</span></span> <span data-ttu-id="cfc42-118">例如，BizTalk Server 不支持由架构类型的一维数组组成的参数。</span><span class="sxs-lookup"><span data-stu-id="cfc42-118">For example, BizTalk Server does not support a parameter that consists of a single dimensional array of schema types.</span></span> <span data-ttu-id="cfc42-119">此外，BizTalk Server 不支持多维数组。</span><span class="sxs-lookup"><span data-stu-id="cfc42-119">In addition, BizTalk Server does not support multidimensional arrays.</span></span> <span data-ttu-id="cfc42-120">XLANG/s 语言保留在 BizTalk Server 中的单词列表，请参阅[XLANG/s 保留字](http://go.microsoft.com/fwlink/?LinkId=155765)(http://go.microsoft.com/fwlink/?LinkId=155765)。</span><span class="sxs-lookup"><span data-stu-id="cfc42-120">For a list of words that XLANG/s language reserves in BizTalk Server, see [XLANG/s Reserved Words](http://go.microsoft.com/fwlink/?LinkId=155765) (http://go.microsoft.com/fwlink/?LinkId=155765).</span></span>  
  
-   <span data-ttu-id="cfc42-121">**避免由添加 Web 引用包含 C# 关键字或标识符导致的编译错误**</span><span class="sxs-lookup"><span data-stu-id="cfc42-121">**Avoiding Compilation Errors Caused by Adding Web References Containing C# Keywords or Identifiers**</span></span>  
  
     <span data-ttu-id="cfc42-122">当你使用**添加 Web 引用**若要添加到 BizTalk 项目的 Web 引用，BizTalk Server，将转换所需调用到架构的每个 Web 方法的架构类型。</span><span class="sxs-lookup"><span data-stu-id="cfc42-122">When you use the **Add Web Reference**to add Web references to BizTalk projects, BizTalk Server converts the schema types that are required to call each Web method to schemas.</span></span> <span data-ttu-id="cfc42-123">BizTalk Server 将这些架构添加到 Reference.xsd。</span><span class="sxs-lookup"><span data-stu-id="cfc42-123">BizTalk Server adds these schemas to Reference.xsd.</span></span> <span data-ttu-id="cfc42-124">如果你的架构包含都是 C# 关键字的元素名称或元素名称与 C# 标识符无效，则可能获得运行时错误。</span><span class="sxs-lookup"><span data-stu-id="cfc42-124">If your schemas contain element names that are C# keywords or the element name is not valid as a C# identifier, you may get a run-time error.</span></span> <span data-ttu-id="cfc42-125">要避免运行时错误，请确保您使用的 Web Services 不包含属于 C# 关键字或无效 C# 标识符的元素名称。</span><span class="sxs-lookup"><span data-stu-id="cfc42-125">To avoid run-time errors, ensure that the Web service you consume does not contain element names that are C# keywords or invalid C# identifiers.</span></span>  
  
-   <span data-ttu-id="cfc42-126">**不支持多个服务/端口类型定义**</span><span class="sxs-lookup"><span data-stu-id="cfc42-126">**Multiple Service/Port Type Definitions Are Unsupported**</span></span>  
  
     <span data-ttu-id="cfc42-127">BizTalk Server 支持添加具有单个服务和端口类型定义的 Web Services 文件。</span><span class="sxs-lookup"><span data-stu-id="cfc42-127">BizTalk Server supports adding a Web service file with a single service and port type definition.</span></span> <span data-ttu-id="cfc42-128">若要添加具有多个服务或端口类型定义的 WSDL 文件，则可能产生下列错误：</span><span class="sxs-lookup"><span data-stu-id="cfc42-128">If you add a WSDL file with multiple service or port type definitions, you may receive the following error:</span></span>  
  
     `Could not generate BizTalk files. Object reference not set to an instance of an object.`  
  
-   <span data-ttu-id="cfc42-129">**对使用 Web 服务公开的数组的支持**</span><span class="sxs-lookup"><span data-stu-id="cfc42-129">**Support for Consuming Arrays Exposed by Web Services**</span></span>  
  
     <span data-ttu-id="cfc42-130">BizTalk Server 可以使用一个维度数组和交错数组不是 BizTalk 服务器 Web 服务的 Web 服务公开。</span><span class="sxs-lookup"><span data-stu-id="cfc42-130">BizTalk Server can consume one dimensional and jagged arrays exposed by Web services that are not BizTalk Server Web services.</span></span> <span data-ttu-id="cfc42-131">有关如何使用 Web 服务数组的详细信息，请参阅[如何使用 Web 服务数组](http://go.microsoft.com/fwlink/?LinkId=155766)(http://go.microsoft.com/fwlink/?LinkId=155766)。</span><span class="sxs-lookup"><span data-stu-id="cfc42-131">For more information about how to consume Web service arrays, see [How to Consume Web Service Arrays](http://go.microsoft.com/fwlink/?LinkId=155766) (http://go.microsoft.com/fwlink/?LinkId=155766).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cfc42-132">不支持多维数组语法。</span><span class="sxs-lookup"><span data-stu-id="cfc42-132">Multi dimensional array syntax is not supported.</span></span> <span data-ttu-id="cfc42-133">例如， *MyArray [1.5]*。</span><span class="sxs-lookup"><span data-stu-id="cfc42-133">For example, *MyArray[1,5]*.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cfc42-134">BizTalk Server 不支持使用的数组**数据集**由 Web 服务公开的对象。</span><span class="sxs-lookup"><span data-stu-id="cfc42-134">BizTalk Server does not support consuming an array of **DataSet** objects exposed by a Web service.</span></span> <span data-ttu-id="cfc42-135">XLANG/s 子服务以本机方式支持的.NET 数据集类，但如果你创建 BizTalk 项目包含对公开.NET 数据集对象的数组的 Web 服务的 Web 引用时尝试以编译该项目，你会收到错误。</span><span class="sxs-lookup"><span data-stu-id="cfc42-135">The XLANG/s subservice does natively support the .NET DataSet class, but if you create a BizTalk project that contains a Web reference to a Web service that exposes an array of .NET DataSet objects you will get errors when you attempt to compile the project.</span></span>  
  
-   <span data-ttu-id="cfc42-136">**Web 方法参数必须是 Xml 可序列化**</span><span class="sxs-lookup"><span data-stu-id="cfc42-136">**Web Method Parameters Must be Xml Serializable**</span></span>  
  
     <span data-ttu-id="cfc42-137">已使用的 Web Services 中的所有参数都必须执行 Xml 序列化。</span><span class="sxs-lookup"><span data-stu-id="cfc42-137">All parameters in a consumed Web service must be Xml Serializable.</span></span> <span data-ttu-id="cfc42-138">若所添加的 Web 方法包含未执行 Xml 序列化的参数，则可能会收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="cfc42-138">If you add a Web method that contains a parameter that is not Xml Serializable, you may receive the following error message:</span></span>  
  
     <span data-ttu-id="cfc42-139">必须对 System.Xml.Element 执行 Xml 序列化，才能使其成为消息部分类型。</span><span class="sxs-lookup"><span data-stu-id="cfc42-139">System.Xml.Element must be Xml Seralizeable to be a message part type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cfc42-140">数据类型， **XmlDocument**和**数据集**，同时不 Xml 可序列化，支持。</span><span class="sxs-lookup"><span data-stu-id="cfc42-140">The data types, **XmlDocument** and **DataSet**, while not Xml Serializable, are supported.</span></span>  
  
-   <span data-ttu-id="cfc42-141">**使用仅限消息传送的 Web 服务**</span><span class="sxs-lookup"><span data-stu-id="cfc42-141">**Consuming Messaging-Only Web Services**</span></span>  
  
     <span data-ttu-id="cfc42-142">时使用的仅限消息传送的 Web 服务，则所有 BizTalk Server 消息正文部分的名称必须与 Web 方法参数名称都匹配。</span><span class="sxs-lookup"><span data-stu-id="cfc42-142">When consuming messaging-only Web services, all BizTalk Server message body part names must match the Web method parameter names.</span></span> <span data-ttu-id="cfc42-143">例如，如果 Web 服务的签名是`WebMethod(MyType1 type1, MyType2 type2)`，部分组成的名称必须是 type1 和 type2，可能会收到以下运行时错误：</span><span class="sxs-lookup"><span data-stu-id="cfc42-143">For example, if the signature of the Web service is `WebMethod(MyType1 type1, MyType2 type2)`, the part name must be type1 and type2, you may get the following runtime error:</span></span>  
  
     `Failed to retrieve the message part for parameter %1`  
  
     <span data-ttu-id="cfc42-144">有关详细信息，请参阅[如何在 Messaging-Only 方案中使用 Web 服务](http://go.microsoft.com/fwlink/?LinkId=155767)(http://go.microsoft.com/fwlink/?LinkId=155767)。</span><span class="sxs-lookup"><span data-stu-id="cfc42-144">For more information, see [How to Consume Web Services in a Messaging-Only Scenario](http://go.microsoft.com/fwlink/?LinkId=155767) (http://go.microsoft.com/fwlink/?LinkId=155767).</span></span>  
  
-   <span data-ttu-id="cfc42-145">**以编程方式配置 SOAP 发送端口**</span><span class="sxs-lookup"><span data-stu-id="cfc42-145">**Configuring a SOAP Send Port Programmatically**</span></span>  
  
     <span data-ttu-id="cfc42-146">可以在消息上下文中以编程方式设置配置属性。</span><span class="sxs-lookup"><span data-stu-id="cfc42-146">It is possible to set configuration properties programmatically on the message context.</span></span> <span data-ttu-id="cfc42-147">发送端口是静态还是动态，你可以在业务流程或自定义管道组件中设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="cfc42-147">You can set these properties in an orchestration or a custom pipeline component whether the send port is static or dynamic.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cfc42-148">若要配置**MethodName**静态 SOAP 属性以编程方式发送端口，你需要设置**方法名称**到**[指定更高版本]**中**Web服务**选项卡**SOAP 传输属性**BizTalk Server 管理控制台中的对话框。</span><span class="sxs-lookup"><span data-stu-id="cfc42-148">To configure the **MethodName** property for the static SOAP send port programmatically, you need to set **Method name** to **[Specify Later]** in the **Web Service** tab of the **SOAP Transport Properties** dialog box in the BizTalk Server Administration console.</span></span>  
  
     <span data-ttu-id="cfc42-149">有关详细信息**MethodName**属性，请参阅[如何动态设置使用的 Web 服务的 URI](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768)。</span><span class="sxs-lookup"><span data-stu-id="cfc42-149">For more information about the **MethodName** property, see [How to Dynamically Set the URI of a Consumed Web Service](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768).</span></span>  
  
-   <span data-ttu-id="cfc42-150">**属性规则**</span><span class="sxs-lookup"><span data-stu-id="cfc42-150">**Property Rules**</span></span>  
  
     <span data-ttu-id="cfc42-151">如果在业务流程或接收管道的自定义管道组件中设置配置属性，则需遵循下列规则：</span><span class="sxs-lookup"><span data-stu-id="cfc42-151">If the configuration property is set in an orchestration or in a custom pipeline component in a receive pipeline, then the following rules are applied:</span></span>  
  
    -   <span data-ttu-id="cfc42-152">如果消息发送到一个静态发送端口，将被覆盖发送端口的值为配置的属性值。</span><span class="sxs-lookup"><span data-stu-id="cfc42-152">If a message is sent to a static send port, the property value will be overwritten with the value configured for that send port.</span></span>  
  
    -   <span data-ttu-id="cfc42-153">如果一条消息发送到动态发送端口，则属性值不会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="cfc42-153">If a message is sent to a dynamic send port, the property value will not be overwritten.</span></span>  
  
     <span data-ttu-id="cfc42-154">如果在发送管道的自定义管道组件中设置配置属性，则需遵循下列规则：</span><span class="sxs-lookup"><span data-stu-id="cfc42-154">If a configuration property is set in a custom pipeline component in a send pipeline, then the following rule is applied:</span></span>  
  
    -   <span data-ttu-id="cfc42-155">无论将消息发送到静态发送端口还是动态发送端口，都不会覆盖属性值。</span><span class="sxs-lookup"><span data-stu-id="cfc42-155">The value will not be overwritten regardless of whether the message is sent to a static or dynamic send port.</span></span> <span data-ttu-id="cfc42-156">换言之，无论在哪里设置配置属性，发送管道组件都会将其覆盖。</span><span class="sxs-lookup"><span data-stu-id="cfc42-156">In other words, send pipeline components overwrite the configuration property no matter where it was set.</span></span>  
  
    -   <span data-ttu-id="cfc42-157">有关自定义管道组件的详细信息，请参阅[开发自定义管道组件](http://go.microsoft.com/fwlink/?LinkId=155769)(http://go.microsoft.com/fwlink/?LinkId=155769)。</span><span class="sxs-lookup"><span data-stu-id="cfc42-157">For more information about custom pipeline components, see [Developing Custom Pipeline Components](http://go.microsoft.com/fwlink/?LinkId=155769) (http://go.microsoft.com/fwlink/?LinkId=155769).</span></span>  
  
    -   <span data-ttu-id="cfc42-158">有关 SOAP 发送适配器的配置属性的详细信息，请参阅[如何动态设置使用的 Web 服务的 URI](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768)。</span><span class="sxs-lookup"><span data-stu-id="cfc42-158">For more information about the configuration properties of the SOAP send adapter, see [How to Dynamically Set the URI of a Consumed Web Service](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768).</span></span>  
  
-   <span data-ttu-id="cfc42-159">**添加对使用的 Web 服务包含多取得 root 权限的架构将导致编译错误的 Web 引用**</span><span class="sxs-lookup"><span data-stu-id="cfc42-159">**Adding a Web Reference to a Consumed Web Service That Contains a Multi-Rooted Schema Will Cause a Compilation Error**</span></span>  
  
     <span data-ttu-id="cfc42-160">如果你添加到你的项目，从已发布的 BizTalk 业务流程派生的 Web 服务的 Web 引用和业务流程包含具有多个根的架构，然后编译项目时也将会出错。</span><span class="sxs-lookup"><span data-stu-id="cfc42-160">If you add a Web reference to your project for a Web service that was derived from a published BizTalk orchestration and the orchestration contains a schema with multiple roots, then an error will occur when the project is compiled.</span></span> <span data-ttu-id="cfc42-161">如果给项目添加的 Web 引用派生自已发布的 BizTalk 业务流程，需确保业务流程不包含任何多根架构。</span><span class="sxs-lookup"><span data-stu-id="cfc42-161">If you add a Web reference to your project that was derived from a published BizTalk orchestration, ensure that the orchestration does not contain any multi-rooted schemas.</span></span>  
  
-   <span data-ttu-id="cfc42-162">**使用 TypedDataSets 作为 Web 方法的参数**</span><span class="sxs-lookup"><span data-stu-id="cfc42-162">**Using TypedDataSets as Parameters to Web Methods**</span></span>  
  
     <span data-ttu-id="cfc42-163">为支持将 TypedDataSets 用作 Web 方法的参数，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cfc42-163">The following is what you need to do to support using TypedDataSets as parameters to Web methods:</span></span>  
  
    1.  <span data-ttu-id="cfc42-164">将 Web 引用添加到 C# 项目，然后生成代理。</span><span class="sxs-lookup"><span data-stu-id="cfc42-164">Add the Web reference to a C# project and then generate the proxy.</span></span>  
  
    2.  <span data-ttu-id="cfc42-165">创建 SOAP 发送端口并在发送端口上指定该代理，然后选择方法。</span><span class="sxs-lookup"><span data-stu-id="cfc42-165">Create a SOAP send port and specify the proxy on the send port and choose the method.</span></span>  
  
    3.  <span data-ttu-id="cfc42-166">在业务流程中定义后期绑定端口和消息类型。</span><span class="sxs-lookup"><span data-stu-id="cfc42-166">In the orchestration, define a late bound port and define the message types.</span></span> <span data-ttu-id="cfc42-167">有关其中任何属性提升或可分辨的字段访问所需的大多数情况下，类型可以定义为**XMLDocument**。</span><span class="sxs-lookup"><span data-stu-id="cfc42-167">For most cases where no property promotion or distinguished field access is needed, the type can be defined as **XMLDocument**.</span></span> <span data-ttu-id="cfc42-168">为该类型选择直通管道。</span><span class="sxs-lookup"><span data-stu-id="cfc42-168">Select PassThrough pipelines with this type.</span></span>  
  
    4.  <span data-ttu-id="cfc42-169">在 BizTalk Server 管理控制台中，在**Web 服务**选项卡中**SOAP 传输属性**对话框中的 SOAP 发送端口，指定你想要使用你创建该代理。</span><span class="sxs-lookup"><span data-stu-id="cfc42-169">In the BizTalk Server Administration console, in the **Web Service** tab in the **SOAP Transport Properties** dialog box of the SOAP send port, specify that you want to use that proxy that you created.</span></span> <span data-ttu-id="cfc42-170">您还需要指定程序集、类型和方法。</span><span class="sxs-lookup"><span data-stu-id="cfc42-170">You will also need to specify assembly, type, and method.</span></span>  
  
-   <span data-ttu-id="cfc42-171">**添加对包含应基于一般的参数将导致编译错误的 Web 方法的使用的 Web 服务的 Web 引用**</span><span class="sxs-lookup"><span data-stu-id="cfc42-171">**Adding a Web Reference to a Consumed Web Service that Contains a Web Method Expecting Generic-Based Parameters Will Cause a Compilation Error**</span></span>  
  
     <span data-ttu-id="cfc42-172">如果你添加到你的项目包含应基于一般的参数，如可以为 null 的参数的 Web 方法的 Web 服务的 Web 引用，编译项目时，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="cfc42-172">If you add a Web reference to your project for a Web service that contains a Web method expecting generic-based parameters such as nullable parameters, an error will occur when the project is compiled.</span></span> <span data-ttu-id="cfc42-173">不支持此设置。</span><span class="sxs-lookup"><span data-stu-id="cfc42-173">This is not supported.</span></span> <span data-ttu-id="cfc42-174">您必须使用显式专用化从 XLANG/s 中调用泛型类。</span><span class="sxs-lookup"><span data-stu-id="cfc42-174">You must use explicit specialization to call the generic class from XLANG/s.</span></span>  
  
-   <span data-ttu-id="cfc42-175">**使用添加 Web 引用 BizTalk 架构生成**</span><span class="sxs-lookup"><span data-stu-id="cfc42-175">**BizTalk Schema Generation Using the Add Web Reference**</span></span>  
  
     <span data-ttu-id="cfc42-176">当你使用**添加 Web 引用**若要添加到 BizTalk 项目的 Web 引用，BizTalk Server，将转换所需调用到架构的每个 Web 方法的架构类型。</span><span class="sxs-lookup"><span data-stu-id="cfc42-176">When you use the **Add Web Reference**to add Web references to BizTalk projects, BizTalk Server converts the schema types that are required to call each Web method to schemas.</span></span> <span data-ttu-id="cfc42-177">BizTalk Server 将这些架构添加到 Reference.xsd。</span><span class="sxs-lookup"><span data-stu-id="cfc42-177">BizTalk Server adds these schemas to Reference.xsd.</span></span> <span data-ttu-id="cfc42-178">若要确保**添加 Web 引用**生成 BizTalk 架构是否正确，Web 服务必须遵循以下指导原则：</span><span class="sxs-lookup"><span data-stu-id="cfc42-178">To ensure that the **Add Web Reference** generates the BizTalk schemas correctly, the Web services must conform to the following guidelines:</span></span>  
  
    -   <span data-ttu-id="cfc42-179">Web 方法应具有**SoapDocumentMethodAttribute**而不是**SoapRpcMethodAttribute**。</span><span class="sxs-lookup"><span data-stu-id="cfc42-179">Web methods should have **SoapDocumentMethodAttribute** instead of **SoapRpcMethodAttribute**.</span></span>  
  
    -   <span data-ttu-id="cfc42-180">Web 服务和方法必须使用**文本**绑定而不**编码**如**[SoapDocumentMethod(Use=SoapBindingUse.Literal)]**。</span><span class="sxs-lookup"><span data-stu-id="cfc42-180">Web services and methods must use the **Literal** binding instead of **Encoded** such as **[SoapDocumentMethod(Use=SoapBindingUse.Literal)]**.</span></span>  
  
    -   <span data-ttu-id="cfc42-181">Web 方法参数和返回类型必须具有**XmlRootAttribute**使用一个有效**Namespace**属性除非它们是本机的 XSD 类型和 XmlNode 类型。</span><span class="sxs-lookup"><span data-stu-id="cfc42-181">Web method parameters and return types must have **XmlRootAttribute** with a valid **Namespace** property unless they are native XSD types and the XmlNode type.</span></span>  
  
    -   <span data-ttu-id="cfc42-182">Web 方法不得使用**RequestNamespace**和**ResponseNamespace**中的属性**SoapDocumentMethodAttribute**。</span><span class="sxs-lookup"><span data-stu-id="cfc42-182">Web methods must not use the **RequestNamespace** and **ResponseNamespace** properties in **SoapDocumentMethodAttribute**.</span></span>  
  
    -   <span data-ttu-id="cfc42-183">Web Services 必须符合 Web Services 互操作性 (WSI) 基本配置文件版本 1.1。</span><span class="sxs-lookup"><span data-stu-id="cfc42-183">Web services must be compliant with the Web services interoperability (WSI) Basic Profile version 1.1.</span></span>  
  
-   <span data-ttu-id="cfc42-184">**添加 Web 引用不支持 Web 服务描述语言 (WSDL) 导入元素**</span><span class="sxs-lookup"><span data-stu-id="cfc42-184">**The Add Web Reference Does Not Support the Web Services Description Language (WSDL) Import Element**</span></span>  
  
     <span data-ttu-id="cfc42-185">在为具有导入元素的 WSDL 文件添加 Web 引用时，“添加 Web 引用”会失败。</span><span class="sxs-lookup"><span data-stu-id="cfc42-185">The Add Web Reference fails when you add Web references for the WSDL file with the import element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc42-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfc42-186">See Also</span></span>  
 [<span data-ttu-id="cfc42-187">规划 BizTalk 服务器层</span><span class="sxs-lookup"><span data-stu-id="cfc42-187">Planning the BizTalk Server Tier</span></span>](../technical-guides/planning-the-biztalk-server-tier.md)