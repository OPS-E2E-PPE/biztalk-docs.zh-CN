---
title: 动态解析和路由概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9a32491-132b-4b25-ac8c-4a927052f0be
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ab158fe2bf16e4e03b2d4817a644d3e37e9567b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306256"
---
# <a name="dynamic-resolution-and-routing-overview"></a>动态解析和路由概述
ESB 解析程序类支持以下运行时解析：  

- 消息传递终结点  

- 用于转换的映射  

- 终结点配置  

- 自定义服务元数据  

- 服务器端的路线  

  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序的连接字符串用于在消息到达时尝试的映射和终结点解析。 到达时，或可能会设置它们的自定义管道使用以下管道组件之一时，可能在旅行计划的消息的 SOAP 标头中存在这些连接字符串：ESB 路线选择器、 ESB 调度程序或 ESB 调度程序反汇编。 使用 ESB 解析程序和适配器提供程序框架组件的"实时"(JIT) 解析功能在处理生命周期中稍后发生解析。  

  例如，如果动态转换代理收到一条消息必须映射，但尚未确定映射名称，它将尝试使用关联的冲突解决程序来执行解析。 如果 JIT 解析失败，这被归类为错误，则系统可以生成一条异常消息。  

  冲突解决程序和适配器提供程序框架可以查询以下数据存储或解决机制：  

- 硬编码映射或终结点，在其中写动态解析不会发生  

- 业务规则引擎 (BRE) 策略  

- 实现自定义程序集**IResolveProvider**接口  

- XPath 查询到消息  

- 通用描述、 发现和集成 (UDDI) 查找
