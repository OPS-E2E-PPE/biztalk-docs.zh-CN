---
title: ESB 解析程序和适配器提供程序框架 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c82c2247-1f0a-48bd-98c2-9c816f4d68d7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce6dfa24c1e5c6f17739be0ba266e302cb9d8667
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400339"
---
# <a name="esb-resolver-and-adapter-provider-framework"></a>ESB 解析程序和适配器提供程序框架
冲突解决程序和适配器提供程序框架提供全面、 可插入体系结构用于动态解析终结点信息和 BizTalk Server 映射类型。 它使用可扩展的组件，允许开发人员可以更改以适应其自己的要求，并扩展机制以支持备用解析和路由方法的行为。  
  
 冲突解决程序和适配器提供程序框架提供了支持通用描述、 发现和集成 (UDDI)、 业务规则引擎 (BRE) 和 XML 路径语言 (XPath)。 它还公开了开发人员接口 (**IResolveProvider**并**IAdapterProvider**) 以允许创建自定义冲突解决程序和适配器组件。 冲突解决程序和适配器提供程序框架的三个主要组件如下：  
  
- **冲突解决程序。** 这些定义一个架构，连接字符串，并通过实现**IResolveProvider**接口中的.NET Framework 程序集。 这些加载和缓存在运行时，支持一系列解析类型和连接字符串。  
  
- **适配器提供程序。** 这些定义通过实现**IAdapterProvider** .NET Framework 程序集内的接口。 这些均由其 BizTalk Server 传输类型，设置相应的 BizTalk Server 适配器上的冲突解决程序提供的终结点信息进行注册。  
  
- **路线的管道组件。** 这些分析解决方案说明从连接字符串或 ESB 路线 SOAP 标头，并提供终结点使用的冲突解决程序和适配器提供程序框架的解决方法或转换执行功能。 组件可以动态设置终结点属性的 BizTalk Server，或执行基于从连接字符串或 ESB 路线 SOAP 标头的解决方法说明 BizTalk Server 映射表转换。 这些组件负责管理、 更新和跨进程和服务边界保留路线。 可选的拆装器组件提供了 BizTalk Server 的消息并实现分析本机[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路由到多个终结点，而无需业务流程服务的功能。  
  
  有关动态解析和动态路由的详细信息，请参阅[使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)并[使用动态转换](../esb-toolkit/using-dynamic-transformation.md)。 有关解析和适配器提供程序框架的信息，请参阅[修改和扩展 BizTalk ESB 工具包](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)。