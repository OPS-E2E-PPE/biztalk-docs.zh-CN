---
title: "转换和路由到多个终结点的一条消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 544db12c-95fc-4321-b397-ec9e7410e37d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99e30c2d7b095d0b075b98a48f9263abd361b6cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transforming-and-routing-a-message-to-multiple-endpoints"></a>转换和路由到多个终结点的一条消息
在此用例，ESB 上执行转换，通过路线 Web 服务上的负载增加提交一条消息。 动态解析查找确定映射名称，并将转换入站的消息。 此外，路线指定 n 数动态解析路线服务和它会将已转换的消息路由到的目标终结点。 所有操作都发生在消息层上，如图 1 中所示。  
  
 ![转换多个终结点](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3 TransformingMultipleEndpoints")  
  
 **图 1**  
  
 **将转换以及消息路由到多个终结点**  
  
 包含动态解析示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何使用 ESB 管道组件，具体而言 ESB 调度反汇编程序组件，来动态解析终结点的位置、 设置路由的属性，并解决，并执行[!INCLUDE[prague](../includes/prague-md.md)]在消息级别，而无需使用映射业务流程。 它还演示了单向和双向消息模式。  
  
 有关详细信息，请参阅[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)和[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。