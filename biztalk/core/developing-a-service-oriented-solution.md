---
title: 面向开发的服务解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, developing
- service solution tutorial, background information
- service solution tutorial, developing
- developing, tutorials
- developing, service solution tutorial
ms.assetid: 7979a05c-7fd3-4476-a623-55de8abdc493
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d8e33baa51a551d0f1f851410fda696abc96983
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239325"
---
# <a name="developing-a-service-oriented-solution"></a>面向开发的服务解决方案
面向服务的解决方案演示了 Woodgrove Bank 的信用帐户余额系统。 有关帐户的信息来自三个原有系统：提供信用限额的 SAP 系统、在大型机上运行的挂起事务系统、使用 MQSeries 的付款跟踪系统。 余额检查请求来自 Web 服务或交互式语音应答 (IVR) 系统。 有关方案的详细信息，请参阅[了解服务面向解决方案](../core/understanding-the-service-oriented-solution.md)。  
  
 本开发人员指南提供了生成用于 Woodgrove Bank 方案的面向服务的结构解决方案的方法。 该指南首先根据行业标准模式考虑可能的解决方案。 “面向服务的解决方案中的模式”首先介绍如何将该模式转换成 BizTalk 应用程序中的相应项目。 下一部分“面向服务的解决方案的组件”简要介绍了应用程序的各个组成部分以及相互之间的关系。 “实现重点”部分介绍了需要进行特定工作以满足方案条件的相关内容，例如使用企业单一登录。 “使用 BAM 监视面向服务的解决方案”介绍了解决方案如何使用 BAM API 来跟踪请求的进度和结果。 “面向服务的解决方案的版本控制”和“扩展面向服务的解决方案”部分提供了扩展或修改该解决方案的一些方法。 参考部分列出了解决方案中的文件并提供了消息的参考。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在服务中的模式面向解决方案](../core/patterns-in-the-service-oriented-solution.md)  
  
-   [服务组件面向解决方案](../core/components-of-the-service-oriented-solution.md)  
  
-   [服务实现重点介绍面向解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md)  
  
-   [监视服务面向与 BAM 解决方案](../core/monitoring-the-service-oriented-solution-with-bam.md)  
  
-   [版本控制服务面向解决方案](../core/versioning-the-service-oriented-solution.md)  
  
-   [缩放服务面向解决方案](../core/scaling-the-service-oriented-solution.md)  
  
-   [面向服务的解决方案引用](../core/service-oriented-solution-reference.md)