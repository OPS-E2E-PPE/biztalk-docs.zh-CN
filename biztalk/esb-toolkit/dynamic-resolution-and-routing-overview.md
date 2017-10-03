---
title: "动态解析和路由概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9a32491-132b-4b25-ac8c-4a927052f0be
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 341b8389530ac85fdc459816f5691f3b814fbd56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-resolution-and-routing-overview"></a>动态解析和路由概述
ESB 解析程序类支持以下运行时解决方法：  
  
-   消息传递终结点  
  
-   转换的的映射  
  
-   终结点配置  
  
-   自定义的服务元数据  
  
-   服务器端路线  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用解析程序连接字符串以在消息到达时尝试解析地图以及终结点。 这些连接字符串中可能存在路线的 SOAP 标头的消息到达时，或它们可能在使用一个以下管道组件的自定义管道中设置时： ESB 路线选择器、 ESB 调度程序或 ESB 调度程序反汇编。 解决方法是更高版本在使用 ESB 解析程序和适配器提供程序框架组件的"实时"(JIT) 解析功能处理生命周期中。  
  
 例如，如果动态转换代理收到一条消息必须映射，但尚未确定映射名称，它将尝试使用关联的冲突解决程序执行解析。 如果 JIT 解析失败，这划分为错误，系统将生成一条异常消息。  
  
 以下数据存储区或解析机制，可以查询中的冲突解决程序和适配器提供程序框架：  
  
-   硬编码的地图或终结点，在其中案例动态解决不会发生  
  
-   业务规则引擎 (BRE) 策略  
  
-   实现自定义程序集**IResolveProvider**接口  
  
-   在消息上 XPath 查询  
  
-   通用、 描述、 发现和集成 (UDDI) 查找