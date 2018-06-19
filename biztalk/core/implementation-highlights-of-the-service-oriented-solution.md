---
title: 服务实现重点介绍面向解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, performance
- performance, service solutions
- service solution tutorial, implementing
ms.assetid: 3dbd8dfd-45b7-4290-ba07-b0c5e6264629
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c593c24c72e5666525001e6a52e2b0bf6eac2de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257749"
---
# <a name="implementation-highlights-of-the-service-oriented-solution"></a>服务实现重点介绍面向解决方案
解决方案用于解决特定环境中的具体问题。 面向服务的解决方案也不例外和特定于 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和方案。 Woodgrove Bank 方案有关的详细信息，请参阅[了解服务面向解决方案](../core/understanding-the-service-oriented-solution.md)。  
  
 在开发该方案时，有几个方面证明是阻碍将响应时间降低到可接受程度的瓶颈。 使用适配器将消息发送到后端系统会导致在获取返回的响应时有明显的延迟。 通常，适配器本身只会造成很短的延迟。 但是，BizTalk 的分布式结构要求适配器使用 MessageBox 与业务流程主机实例进行通信。 这会导致消息在适配器与该数据库之间往返，从而影响延迟时间。 因此，该解决方案的内联版本（速度最快的版本）在业务流程本身中生成直接调用后端系统的适配器功能。 如果有三种不同的后端系统，这意味着可能有三种不同的机制与后端系统进行通信。  
  
 确认会造成性能问题的另一个方面是从企业单一登录 (SSO) 检索配置数据。 为了在缩短检索时间的同时保持 SSO 的易用性和通用性，该解决方案为配置值使用了本地缓存。 通过使用 SSO，还可以简化配置数据的管理。 添加其他主机实例以满足延迟和性能要求并不需要更改运行主机实例的服务器的设置。  
  
 该解决方案的另一个不同寻常的方面是直接从代码调用管道。 这允许重复使用自定义管道组件。  
  
 最后，还提供了一些可更改的 BizTalk Server 设置，从而可最大限度提高解决方案的速度。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [内联的后端调用](../core/inlining-back-end-invocation.md)  
  
-   [在服务中有效地使用 SSO 面向解决方案](../core/using-sso-efficiently-in-the-service-oriented-solution.md)  
  
-   [使用从服务的管道面向解决方案](../core/using-pipelines-from-the-service-oriented-solution.md)  
  
-   [优化服务面向解决方案](../core/tuning-the-service-oriented-solution.md)  
  
-   [分离传输类型和处理](../core/decoupling-transport-type-and-processing.md)