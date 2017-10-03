---
title: "使用动态转换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1e4aac7-242a-41b6-8df4-4881371f44d1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d7f6bc57d009e558188950d9bcb0387f808f835
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-dynamic-transformation"></a>使用动态转换
## <a name="overview"></a>概述  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态转换支持三种机制：  
  
-   作为业务流程实现动态转换代理  
  
-   动态转换核心 Web 服务中包含的 Web 服务  
  
-   由 ESB 管道组件执行的转换  
  
 本部分重点介绍实现按业务流程的转换代理。 有关转换 Web 服务的信息，请参阅[使用 BizTalk ESB 工具包 Web 服务](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)。 有关 ESB 调度程序管道组件的信息，请参阅[使用管道支持组件](../esb-toolkit/using-the-pipeline-support-components.md)。  
  
## <a name="how-it-works"></a>它是如何工作  
 转换传递代理是订阅的消息的业务流程其中**名称**属性的当前**服务实例**路线中的元素是**Microsoft.Practices.ESB.Services.Transform**。 代理可执行以下操作序列：  
  
1.  接收非类型化的消息 (System.Xml.XmlDocument)。  
  
2.  如果为路线中的静态值可用映射的名称，代理将尝试解析映射使用解析程序管理器的名称。  
  
3.  它适用于入站的源消息的适当的映射。  
  
4.  它将映射表输出发布到 BizTalk 消息框数据库。  
  
## <a name="how-to-configure-dynamic-transformation"></a>如何配置动态转换  
 有关如何配置使用路线设计器的动态转换的详细信息，请参阅[创建路线使用路线设计器](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)。  
  
## <a name="dynamic-transformation-errors"></a>动态转换错误  
 动态转换机制将创建并在以下情况下发布 ESB 错误消息：  
  
-   无法确定冲突解决程序组件，它们将分别映射。  
  
-   指定的地图不可用 （例如，你指定为不正确的地图类型或地图尚未部署 BizTalk Server 2009 年）。  
  
-   映射过程中出现故障 （例如，源文档的不是正确的源类型或自定义函数的外部程序集中未部署到 BizTalk 映射引用）。  
  
-   映射类型的解析 — 在实时 (JIT) 过程中发生异常。  
  
-   没有任何订户存在输出消息。  
  
-   会发生任何系统异常。  
  
 它由开发人员负责提供用来填充异常消息和创建处理程序来响应该异常的上下文信息。 某些数据会自动提供，和泛型处理程序会选取异常消息，如果没有目标处理指定了或可用。 有关处理动态转换异常的详细信息，请参阅[使用 ESB 异常管理](../esb-toolkit/using-esb-exception-management.md)。