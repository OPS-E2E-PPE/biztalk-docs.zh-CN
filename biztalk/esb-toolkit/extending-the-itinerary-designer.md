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
# <a name="extending-the-itinerary-designer"></a>扩展路线设计器
路线设计器是 Microsoft Visual Studio，以用于路线图形建模 visual 域特定语言 (DSL) [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 在设计器公开各种开发人员可以为其编写自定义扩展插件来启用新功能和/或新的配置选项的扩展点。  
  

  
 **创建自定义路线导出程序**  
  
 路线设计器的体系结构允许创建自定义模型导出程序的序列化和保持路线模型中的数据。  
  
 **为消息传送服务创建自定义扩展程序**  
  
 路线设计器的体系结构，可创建自定义扩展程序可用于将属性添加到使用的属性包的消息传送服务的路线服务模型元素。  
  
 有关如何创建此类扩展器的示例，请参阅[安装和运行设计器扩展性示例](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)。  
  
 **为基于业务流程的路线服务创建自定义扩展程序**  
  
 路线设计器的体系结构，可创建自定义扩展程序可用于将属性添加到使用的属性包的基于业务流程的路线服务的路线服务模型元素。  
  
 有关如何创建此类扩展器的示例，请参阅[安装和运行设计器扩展性示例](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)。  
  
 **创建自定义解析程序扩展程序**  
  
 路线设计器的体系结构，可创建自定义扩展程序的自定义冲突解决程序的配置。 这些扩展程序提供的图形界面用于配置的名称-值对在冲突解决程序连接字符串中，映射到特定的冲突解决程序扩展程序类中的属性。  
  
 有关如何创建此类扩展器的示例，请参阅[安装和运行设计器扩展性示例](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)。  
  
 **为自定义适配器属性创建一个清单文件**  
  
 在创建自定义适配器提供程序，还必须为适配器提供程序对这些终结点配置属性显示的冲突解决程序扩展程序提供的设计器支持。 若要启用设计器支持，就需要创建适配器提供程序清单文件。  
  
 适配器提供程序清单文件定义与特定的适配器提供程序、 其类型、 说明和可以找到该程序集关联的属性。 这些清单文件应置于具有唯一名称 (例如，FTPPropertyManifest.xml) 的路线设计器二进制文件 (例如，Microsoft.Practices.Itineary.DslPackage.dll) 所在的文件夹。  
  
 下面是适配器提供程序清单文件; 的引用实例同样应该结构化自定义清单文件。  
  
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
  
 **创建自定义筛选器扩展程序**  
  
 路线设计器的体系结构，可创建自定义筛选器的配置的自定义扩展器。 这些扩展程序提供一个图形界面，在筛选器连接字符串中配置的名称-值对的映射到特定筛选器扩展程序类中的属性。  
  
- / 示例/设计器扩展性 Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample  
  
- / 示例/设计器扩展性 Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample  
  
  **创建自定义验证规则**  
  
  引入的路线设计器的最后一个重大扩展是允许您从外部看，对于特定于域的语言 (DSL)，指定和实现模型验证规则的验证机制。 该机制"挂接到"DSL 验证框架，它在用户单击时，将激活**Validate**或**验证所有**模型的快捷菜单上。 这将调用 DSL framework **DslCommandSet**对象，该路线设计器中都依次调用验证引擎对象。  
  
  **ValidationEngine**类执行模型元素验证使用企业库验证应用程序块，并将验证错误记录到 Microsoft Visual Studio IDE 中的错误列表窗口。 在企业库配置文件中定义了应为每种类型的模型中的元素执行验证。 文件名为 Ruleset.config 并且位于路线设计器的所有二进制文件所在的二进制文件夹。 下面的示例是配置文件的片段，并包括两个验证规则 （名为验证程序） **UddiResolver**扩展程序、 一个用于**ServerUrl**属性，另一个用于**ServiceKey**属性。  
  
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
  
 每个规则标识实现该规则的验证程序。 路线设计器附带了大量的验证程序类。 它们是所有在 Microsoft.Practices.Modeling.Validation 项目设计器二进制文件夹中。  
  
 使用此验证机制的最终结果是用户可以修改模型如何通过更改提供的规则和验证程序或通过添加自己的规则和验证程序验证该路线设计器。 这可以完成而无需打开、 修改、 重新生成和重新部署 Dsl，请执行以下两个步骤：  
  
1.  创建验证程序类，并将其放入二进制文件夹内的库位置**Microsoft.Practices.Modeling.Validation.dll**所在的库。  
  
2.  将条目添加到 Rules.config 文件以定义验证程序应应用哪些模型元素类的哪些属性。