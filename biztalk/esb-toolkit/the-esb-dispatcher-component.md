---
title: ESB 调度程序组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85655b5f-4717-42d1-b005-0a5592d5653b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16281ff49da6470212e9e8396a051270adf1eef7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982126"
---
# <a name="the-esb-dispatcher-component"></a>ESB 调度程序组件
ESB 调度程序组件内执行基于消息传送的路线服务。 调度程序组件可以动态地设置终结点的出站消息的位置属性，并动态转换消息。  
  
## <a name="component-properties"></a>组件属性  
 调度程序组件具有六个属性：  
  
- **RoutingServiceName**。 此属性指定的基于消息的路由服务的注册的名称。 默认值是**Microsoft.Practices.ESB.Services.Routing**。  
  
- **TransformServiceName**。 此属性指定的基于消息的转换服务的注册的名称。 默认值是**Microsoft.Practices.ESB.Services.Transform**。  
  
- **验证**。 此属性指定是否需要验证一条消息。  
  
- **启用**。 此属性启用或禁用该组件。  
  
- **终结点**。 此属性是注册到 BizTalk ESB 工具包的格式中的冲突解决程序连接字符串。  
  
- **将名称映射**。 此属性为映射的完全限定的名称或连接字符串格式向注册[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
  -   下面是映射名称的一个示例：  
  
      ```  
      GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN, GlobalBank.ESB.DynamicResolution.Transforms, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a  
      ```