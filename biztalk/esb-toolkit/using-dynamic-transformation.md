---
title: 使用动态转换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1e4aac7-242a-41b6-8df4-4881371f44d1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81476c0bdcdbcf3d5647dd7bc83b37a70d6e7557
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396445"
---
# <a name="using-dynamic-transformation"></a>使用动态转换
## <a name="overview"></a>概述  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态转换为支持三种机制：  
  
- 作为业务流程实现了动态转换代理  
  
- 动态转换核心 Web 服务中包含的 Web 服务  
  
- ESB 管道组件执行的转换  
  
  本部分重点介绍作为业务流程实现的转换代理。 有关转换 Web 服务的信息，请参阅[使用 BizTalk ESB 工具包 Web 服务](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)。 ESB 调度程序管道组件的信息，请参阅[使用管道支持组件](../esb-toolkit/using-the-pipeline-support-components.md)。  
  
## <a name="how-it-works"></a>其工作原理  
 转换传递代理是指业务流程订阅消息的位置**名称**属性的当前**ServiceInstance**路线中的元素是**Microsoft.Practices.ESB.Services.Transform**。 代理将执行以下一系列操作：  
  
1.  收到非类型化的消息 (System.Xml.XmlDocument)。  
  
2.  如果可用作路线中的静态值的映射的名称，代理将尝试解析使用冲突解决程序管理器的映射的名称。  
  
3.  它适用于入站的源消息的适当的映射。  
  
4.  它将映射表输出发布到 BizTalk Messagebox 数据库。  
  
## <a name="how-to-configure-dynamic-transformation"></a>如何配置动态转换  
 有关如何配置使用路线设计器的动态转换的详细信息，请参阅[路线使用路线设计器创建](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)。  
  
## <a name="dynamic-transformation-errors"></a>动态转换错误  
 动态转换机制将创建并在以下情况下发布到 ESB 的错误消息：  
  
- 冲突解决程序组件无法确定要应用的映射。  
  
- 指定的映射不可用 （例如，您指定不正确的映射类型或映射在 BizTalk Server 2009 中尚不支持部署）。  
  
- 在映射期间发生故障 （例如，源文档不是正确的源类型或自定义函数中的外部程序集未部署到 BizTalk 映射引用的）。  
  
- 在实时 (JIT) 解析映射类型的过程中发生异常。  
  
- 没有订阅服务器上存在的输出消息。  
  
- 会发生任何系统异常。  
  
  它是开发人员负责提供用来填充异常消息和创建处理程序来对异常做出反应的上下文信息。 一些数据自动可用，并且一般处理程序将选取异常消息，如果没有目标处理程序指定了或可用。 有关处理动态转换异常的详细信息，请参阅[使用 ESB 异常管理](../esb-toolkit/using-esb-exception-management.md)。