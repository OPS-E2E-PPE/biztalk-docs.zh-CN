---
title: 面向服务的实现重点推荐的解决方案 |Microsoft Docs
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
ms.openlocfilehash: 47cc270e442964d46307a81c097df18085696107
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332497"
---
# <a name="implementation-highlights-of-the-service-oriented-solution"></a>面向服务的实现重点推荐的解决方案
解决方案用于解决特定的上下文中的特定问题。 面向服务的解决方案也不例外，特定于 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和方案。 有关 Woodgrove Bank 方案的详细信息，请参阅[了解面向服务的解决方案](../core/understanding-the-service-oriented-solution.md)。  
  
 在开发该方案，几个方面被证明是响应时间降低到可接受级别的瓶颈。 将消息发送到后端系统使用的适配器有明显的延迟在获取响应。 一般情况下，适配器本身提供延迟非常低。 但是，BizTalk 的分布式的结构要求适配器与使用 messagebox 的业务流程主机实例进行通信。 这给数据库带来了往返行程，从而影响延迟时间。 出于此原因，解决方案 （最快的版本） 生成的内联版本中的业务流程本身的适配器功能的后端系统直接调用。 使用三个不同的后端系统，这意味着可能三个不同的机制与后端系统进行通信。  
  
 事实证明，性能问题的另一个区域从企业单一登录 (SSO) 检索配置数据。 若要在缩短检索时间的同时保留方便使用和 SSO 的通用性，该解决方案时，可使用本地缓存的配置值。 使用 SSO 还允许更方便地管理配置数据。 添加其他主机实例以满足延迟和性能要求不需要更改运行主机实例的服务器上的设置。  
  
 另一个不同寻常的解决方案直接从代码调用管道。 这允许重复使用的自定义管道组件。  
  
 最后，有多个 BizTalk Server 设置，可以更改最大限度的最后一从解决方案的速度。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [内联后端调用](../core/inlining-back-end-invocation.md)  
  
-   [在服务中有效使用 SSO 面向解决方案](../core/using-sso-efficiently-in-the-service-oriented-solution.md)  
  
-   [使用该服务中的管道面向解决方案](../core/using-pipelines-from-the-service-oriented-solution.md)  
  
-   [优化面向服务的解决方案](../core/tuning-the-service-oriented-solution.md)  
  
-   [分离传输类型和处理](../core/decoupling-transport-type-and-processing.md)