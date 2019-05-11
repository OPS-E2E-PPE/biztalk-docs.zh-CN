---
title: 转换和一条消息路由到多个终结点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 544db12c-95fc-4321-b397-ec9e7410e37d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c05d76c9f964ccfd326ed5091152545ee647a64
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399615"
---
# <a name="transforming-and-routing-a-message-to-multiple-endpoints"></a>转换和一条消息路由到多个终结点
在此用例，ESB 路线 Web 服务的途径，通过提交对消息执行的转换。 动态解析查找确定映射名称，并将入站的消息转换。 此外，路线指定 n 个目标终结点的路线服务将动态解析并会将已转换的消息路由。 所有操作都发生在消息传送层上，如图 1 中所示。  
  
 ![转换多个终结点](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3-TransformingMultipleEndpoints")  
  
 **图 1**  
  
 **转换和消息路由到多个终结点**  
  
 动态解析示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何使用 ESB 管道组件，具体而言，ESB 调度拆装器组件、 动态解析终结点位置、 设置路由属性，并解析和执行 BizTalk Server 映射在消息级别，而无需使用业务流程。 它还演示了单向和双向消息传送模式。  
  
 有关详细信息，请参阅[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)并[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。