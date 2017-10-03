---
title: "ESB 调度程序组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 85655b5f-4717-42d1-b005-0a5592d5653b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe377221034637eab23b70c50ccf48a8454a23bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-dispatcher-component"></a>ESB 调度程序组件
ESB 调度程序组件内执行了基于消息的路线服务。 调度程序组件可以还可以动态地设置出站消息的终结点位置属性，并动态转换消息。  
  
## <a name="component-properties"></a>组件属性  
 调度程序组件具有六个属性：  
  
-   **RoutingServiceName**。 此属性指定基于消息的路由服务注册的名称。 默认值是**Microsoft.Practices.ESB.Services.Routing**。  
  
-   **TransformServiceName**。 此属性指定为基于消息的转换服务注册的名称。 默认值是**Microsoft.Practices.ESB.Services.Transform**。  
  
-   **验证**。 此属性指定是否需要验证消息。  
  
-   **启用**。 此属性启用或禁用该组件。  
  
-   **终结点**。 此属性是一种格式注册 BizTalk ESB 工具包中的冲突解决程序连接字符串。  
  
-   **映射名称**。 此属性为映射的完全限定的名称或连接字符串格式向注册[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
    -   下面是映射名称的示例：  
  
        ```  
        GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN, GlobalBank.ESB.DynamicResolution.Transforms, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a  
        ```