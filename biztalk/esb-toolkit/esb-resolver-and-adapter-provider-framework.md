---
title: "ESB 冲突解决程序和适配器提供程序框架 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c82c2247-1f0a-48bd-98c2-9c816f4d68d7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c23fa8aca6def654b594d8b4fccf5d584e12fed4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="esb-resolver-and-adapter-provider-framework"></a>ESB 冲突解决程序和适配器提供程序框架
冲突解决程序和适配器提供程序框架提供一个全面的、 可插入体系结构来动态解析终结点信息和 BizTalk Server 映射类型。 它使用可扩展的组件，允许开发人员更改行为，以便根据其自己的需求和扩展以支持备选解决方案和路由方法的机制。  
  
 冲突解决程序和适配器提供程序框架提供的支持通用的说明，发现和集成 (UDDI)、 业务规则引擎 (BRE) 和 XML 路径语言 (XPath)。 它还使开发人员接口 (**IResolveProvider**和**IAdapterProvider**) 以允许创建自定义冲突解决程序和适配器组件。 冲突解决程序和适配器提供程序框架的三个主要组件如下：  
  
-   **冲突解决程序。** 这些定义同一个架构，连接字符串，并通过实现**IResolveProvider** .NET Framework 程序集中的接口。 这些加载和缓存在运行时并支持一系列的解决方法类型和连接字符串。  
  
-   **适配器提供程序。** 这些定义的实现通过**IAdapterProvider** .NET Framework 程序集内的接口。 这些注册由其 BizTalk Server 传输类型，它设置相应的 BizTalk Server 适配器上的冲突解决程序提供的终结点信息。  
  
-   **路线管道组件。** 这些分析解决方案说明从连接字符串或 ESB 路线 SOAP 标头，并提供终结点解析或转换执行功能使用解析程序和适配器提供程序框架。 组件可以动态设置终结点属性的 BizTalk Server 或执行基于从连接字符串或 ESB 路线 SOAP 标头的解决方案说明 BizTalk Server 映射表转换。 这些组件负责管理、 更新和跨进程和服务边界保留路线。 可选的反汇编程序组件提供的消息和实现的本地 BizTalk Server 解析[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]的路由到多个终结点，而无需业务流程服务的功能。  
  
 有关动态解析和动态路由的详细信息，请参阅[使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)和[使用动态转换](../esb-toolkit/using-dynamic-transformation.md)。 有关解析和适配器提供程序框架的信息，请参阅[修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)。