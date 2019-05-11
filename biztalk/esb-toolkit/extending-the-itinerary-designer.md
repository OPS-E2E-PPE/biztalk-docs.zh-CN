---
title: 扩展路线设计器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f26b825b-ebab-4dac-b7ed-0608c79e146a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a853328e955f017a370b3025adb52d8f8706f796
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249922"
---
# <a name="extending-the-itinerary-designer"></a><span data-ttu-id="32033-102">扩展路线设计器</span><span class="sxs-lookup"><span data-stu-id="32033-102">Extending the Itinerary Designer</span></span>
<span data-ttu-id="32033-103">路线设计器是 Microsoft Visual Studio，以用于路线图形建模 visual 域特定语言 (DSL) [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="32033-103">The Itinerary Designer is a visual domain-specific language (DSL) for Microsoft Visual Studio that enables the graphical modeling of itineraries for use with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="32033-104">在设计器公开各种开发人员可以为其编写自定义扩展插件来启用新功能和/或新的配置选项的扩展点。</span><span class="sxs-lookup"><span data-stu-id="32033-104">The designer exposes various extension points for which developers can write custom extensions to enable new functionality and/or new configuration options.</span></span>  
  

  
 <span data-ttu-id="32033-105">**创建自定义路线导出程序**</span><span class="sxs-lookup"><span data-stu-id="32033-105">**Creating a Custom Itinerary Exporter**</span></span>  
  
 <span data-ttu-id="32033-106">路线设计器的体系结构允许创建自定义模型导出程序的序列化和保持路线模型中的数据。</span><span class="sxs-lookup"><span data-stu-id="32033-106">The architecture of the Itinerary Designer allows for the creation of custom model exporters that serialize and persist the data in an Itinerary model.</span></span>  
  
 <span data-ttu-id="32033-107">**为消息传送服务创建自定义扩展程序**</span><span class="sxs-lookup"><span data-stu-id="32033-107">**Creating a Custom Extender for a Messaging Service**</span></span>  
  
 <span data-ttu-id="32033-108">路线设计器的体系结构，可创建自定义扩展程序可用于将属性添加到使用的属性包的消息传送服务的路线服务模型元素。</span><span class="sxs-lookup"><span data-stu-id="32033-108">The architecture of the Itinerary Designer allows you to create custom extenders for Itinerary Service model elements that can be used to add properties to the property bag for use by Messaging Services.</span></span>  
  
 <span data-ttu-id="32033-109">有关如何创建此类扩展器的示例，请参阅[安装和运行设计器扩展性示例](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="32033-109">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="32033-110">**为基于业务流程的路线服务创建自定义扩展程序**</span><span class="sxs-lookup"><span data-stu-id="32033-110">**Creating a Custom Extender for an Orchestration-Based Itinerary Service**</span></span>  
  
 <span data-ttu-id="32033-111">路线设计器的体系结构，可创建自定义扩展程序可用于将属性添加到使用的属性包的基于业务流程的路线服务的路线服务模型元素。</span><span class="sxs-lookup"><span data-stu-id="32033-111">The architecture of the Itinerary Designer allows you to create custom extenders for Itinerary Service model elements that can be used to add properties to the property bag for use by orchestration-based itinerary services.</span></span>  
  
 <span data-ttu-id="32033-112">有关如何创建此类扩展器的示例，请参阅[安装和运行设计器扩展性示例](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="32033-112">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="32033-113">**创建自定义解析程序扩展程序**</span><span class="sxs-lookup"><span data-stu-id="32033-113">**Creating a Custom Resolver Extender**</span></span>  
  
 <span data-ttu-id="32033-114">路线设计器的体系结构，可创建自定义扩展程序的自定义冲突解决程序的配置。</span><span class="sxs-lookup"><span data-stu-id="32033-114">The architecture of the Itinerary Designer allows you to create custom extenders for the configuration of custom resolvers.</span></span> <span data-ttu-id="32033-115">这些扩展程序提供的图形界面用于配置的名称-值对在冲突解决程序连接字符串中，映射到特定的冲突解决程序扩展程序类中的属性。</span><span class="sxs-lookup"><span data-stu-id="32033-115">These extenders provide a graphical interface for configuring the name-value pairs in the resolver connection string, which map to properties in the specific resolver extender class.</span></span>  
  
 <span data-ttu-id="32033-116">有关如何创建此类扩展器的示例，请参阅[安装和运行设计器扩展性示例](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="32033-116">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="32033-117">**为自定义适配器属性创建一个清单文件**</span><span class="sxs-lookup"><span data-stu-id="32033-117">**Creating a Manifest File for Custom Adapter Properties**</span></span>  
  
 <span data-ttu-id="32033-118">在创建自定义适配器提供程序，还必须为适配器提供程序对这些终结点配置属性显示的冲突解决程序扩展程序提供的设计器支持。</span><span class="sxs-lookup"><span data-stu-id="32033-118">When creating a custom adapter provider, you must also provide designer support for the adapter provider to those resolver extenders that display an endpoint configuration property.</span></span> <span data-ttu-id="32033-119">若要启用设计器支持，就需要创建适配器提供程序清单文件。</span><span class="sxs-lookup"><span data-stu-id="32033-119">To enable designer support, it is necessary to create an adapter provider manifest file.</span></span>  
  
 <span data-ttu-id="32033-120">适配器提供程序清单文件定义与特定的适配器提供程序、 其类型、 说明和可以找到该程序集关联的属性。</span><span class="sxs-lookup"><span data-stu-id="32033-120">The adapter provider manifest file defines the properties associated with a specific adapter provider, their types, descriptions, and the assembly in which they can be found.</span></span> <span data-ttu-id="32033-121">这些清单文件应置于具有唯一名称 (例如，FTPPropertyManifest.xml) 的路线设计器二进制文件 (例如，Microsoft.Practices.Itineary.DslPackage.dll) 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="32033-121">These manifest files should be placed in the same folder as the Itinerary Designer binaries (for example, Microsoft.Practices.Itineary.DslPackage.dll) with a unique name (for example, FTPPropertyManifest.xml).</span></span>  
  
 <span data-ttu-id="32033-122">下面是适配器提供程序清单文件; 的引用实例同样应该结构化自定义清单文件。</span><span class="sxs-lookup"><span data-stu-id="32033-122">The following is a reference instance of an adapter provider manifest file; custom manifest files should be structured likewise.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<adapterPropertyManifest adapterName="FTP">  
     <aliases>  
          <alias name="globalPropertySchemas" value="Microsoft.BizTalk.GlobalPropertySchemas, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
     </aliases>  
     <properties>  
          <property name="UserName" type="FTP.UserName" description="The user name for the connection." encrypted="true" assembly="globalPropertySchemas" />  
          <property name="Password" type="FTP.Password" description="The password for the conection." encrypted="true" assembly="globalPropertySchemas" />  
          <property name="MaxConnections" type="FTP.MaxConnections" description="The maximun number of connections." assembly="globalPropertySchemas" />  
          <property name="EventArgs" type="System.EventArgs" assembly="mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
     </properties>  
</adapterPropertyManifest>  
```  
  
 <span data-ttu-id="32033-123">**创建自定义筛选器扩展程序**</span><span class="sxs-lookup"><span data-stu-id="32033-123">**Creating a Custom Filter Extender**</span></span>  
  
 <span data-ttu-id="32033-124">路线设计器的体系结构，可创建自定义筛选器的配置的自定义扩展器。</span><span class="sxs-lookup"><span data-stu-id="32033-124">The architecture of the Itinerary Designer allows you to create custom extenders for the configuration of custom filters.</span></span> <span data-ttu-id="32033-125">这些扩展程序提供一个图形界面，在筛选器连接字符串中配置的名称-值对的映射到特定筛选器扩展程序类中的属性。</span><span class="sxs-lookup"><span data-stu-id="32033-125">These extenders provide a graphical interface for configuring the name-value pairs in the filter connection string, which map to properties in the specific filter extender class.</span></span>  
  
- <span data-ttu-id="32033-126">/ 示例/设计器扩展性 Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample</span><span class="sxs-lookup"><span data-stu-id="32033-126">/Samples/Designer Extensibility Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample</span></span>  
  
- <span data-ttu-id="32033-127">/ 示例/设计器扩展性 Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample</span><span class="sxs-lookup"><span data-stu-id="32033-127">/Samples/Designer Extensibility Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample</span></span>  
  
  <span data-ttu-id="32033-128">**创建自定义验证规则**</span><span class="sxs-lookup"><span data-stu-id="32033-128">**Creating Custom Validation Rules**</span></span>  
  
  <span data-ttu-id="32033-129">引入的路线设计器的最后一个重大扩展是允许您从外部看，对于特定于域的语言 (DSL)，指定和实现模型验证规则的验证机制。</span><span class="sxs-lookup"><span data-stu-id="32033-129">The last significant extension introduced by the Itinerary Designer is a validation mechanism that allows you to externally, with respect to a domain-specific language (DSL), specify and implement the model validation rules.</span></span> <span data-ttu-id="32033-130">该机制"挂接到"DSL 验证框架，它在用户单击时，将激活**Validate**或**验证所有**模型的快捷菜单上。</span><span class="sxs-lookup"><span data-stu-id="32033-130">The mechanism "hooks into" the DSL validation framework and is activated when the user clicks **Validate** or **Validate all** on the shortcut menu of a model.</span></span> <span data-ttu-id="32033-131">这将调用 DSL framework **DslCommandSet**对象，该路线设计器中都依次调用验证引擎对象。</span><span class="sxs-lookup"><span data-stu-id="32033-131">This invokes the DSL framework's **DslCommandSet** object that, in turn, calls the validation engine in the Itinerary Designer.</span></span>  
  
  <span data-ttu-id="32033-132">**ValidationEngine**类执行模型元素验证使用企业库验证应用程序块，并将验证错误记录到 Microsoft Visual Studio IDE 中的错误列表窗口。</span><span class="sxs-lookup"><span data-stu-id="32033-132">The **ValidationEngine** class performs the model element validation using the Enterprise Library Validation Application Block and logs the validation errors to the Error List window in Microsoft Visual Studio IDE.</span></span> <span data-ttu-id="32033-133">在企业库配置文件中定义了应为每种类型的模型中的元素执行验证。</span><span class="sxs-lookup"><span data-stu-id="32033-133">The validation that should be performed for each type of element in a model is defined in the Enterprise Library configuration file.</span></span> <span data-ttu-id="32033-134">文件名为 Ruleset.config 并且位于路线设计器的所有二进制文件所在的二进制文件夹。</span><span class="sxs-lookup"><span data-stu-id="32033-134">The file is named Ruleset.config and is located in the binary folder where all the Itinerary Designer binaries are located.</span></span> <span data-ttu-id="32033-135">下面的示例是配置文件的片段，并包括两个验证规则 （名为验证程序） **UddiResolver**扩展程序、 一个用于**ServerUrl**属性，另一个用于**ServiceKey**属性。</span><span class="sxs-lookup"><span data-stu-id="32033-135">The following example is a fragment of the configuration file and includes two validation rules (named validators) for the **UddiResolver** extender, one for the **ServerUrl** property and one for the **ServiceKey** property.</span></span>  
  
```  
<!--   
UddiResolver  
-->  
<type assemblyName="Microsoft.Practices.Services.Extenders.Resolvers.UDDI"  
 name="Microsoft.Practices.Services.Extenders.Resolvers.UDDI.UddiResolver">  
<ruleset name="Menu">  
<properties>  
<property name="ServerUrl">  
<validator type="Microsoft.Practices.Modeling.Validation.NotEmptyStringValidator, Microsoft.Practices.Modeling.Validation"  
          messageTemplate="The '{1}' property value should not be empty or null."  
          name="UddiResolver.ServerUrl not null validator"/>  
</property>  
<property name="ServiceKey">  
<validator type="Microsoft.Practices.Modeling.Validation.NotEmptyStringValidator, Microsoft.Practices.Modeling.Validation"  
          messageTemplate="The '{1}' property value should not be empty or null."  
          name="UddiResolver.ServiceKey not null validator"/>  
</property>  
</properties>  
</ruleset>  
</type>  
```  
  
 <span data-ttu-id="32033-136">每个规则标识实现该规则的验证程序。</span><span class="sxs-lookup"><span data-stu-id="32033-136">Each rule identifies the validator that implements the rule.</span></span> <span data-ttu-id="32033-137">路线设计器附带了大量的验证程序类。</span><span class="sxs-lookup"><span data-stu-id="32033-137">The Itinerary Designer comes with a large set of validator classes.</span></span> <span data-ttu-id="32033-138">它们是所有在 Microsoft.Practices.Modeling.Validation 项目设计器二进制文件夹中。</span><span class="sxs-lookup"><span data-stu-id="32033-138">They are all in the Microsoft.Practices.Modeling.Validation project in the Designer binary folder.</span></span>  
  
 <span data-ttu-id="32033-139">使用此验证机制的最终结果是用户可以修改模型如何通过更改提供的规则和验证程序或通过添加自己的规则和验证程序验证该路线设计器。</span><span class="sxs-lookup"><span data-stu-id="32033-139">The final result of using this validation mechanism is that Itinerary Designer users can modify how the models are validated by changing the provided rules and validators or by adding their own rules and validators.</span></span> <span data-ttu-id="32033-140">这可以完成而无需打开、 修改、 重新生成和重新部署 Dsl，请执行以下两个步骤：</span><span class="sxs-lookup"><span data-stu-id="32033-140">This can be done without opening, modifying, rebuilding, and re-deploying the DSLs by performing the following two steps:</span></span>  
  
1.  <span data-ttu-id="32033-141">创建验证程序类，并将其放入二进制文件夹内的库位置**Microsoft.Practices.Modeling.Validation.dll**所在的库。</span><span class="sxs-lookup"><span data-stu-id="32033-141">Create a validator class and put it in a library inside the binary folder where the **Microsoft.Practices.Modeling.Validation.dll** library is located.</span></span>  
  
2.  <span data-ttu-id="32033-142">将条目添加到 Rules.config 文件以定义验证程序应应用哪些模型元素类的哪些属性。</span><span class="sxs-lookup"><span data-stu-id="32033-142">Add entries to the Rules.config file to define what property of what model element class the validator should be applied.</span></span>