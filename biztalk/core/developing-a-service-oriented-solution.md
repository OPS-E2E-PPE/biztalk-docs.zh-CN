---
title: 开发面向服务的解决方案 |Microsoft Docs
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
ms.openlocfilehash: 62bac2f534b5f542f65b316faef7ecbad976dfee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351464"
---
# <a name="developing-a-service-oriented-solution"></a>开发面向服务的解决方案
面向服务的解决方案演示了 Woodgrove bank 的信用帐户余额系统。 有关帐户的信息来自三个旧系统： 提供信用限额的 SAP 系统、 在大型机上运行的挂起事务系统和使用 MQSeries 的付款跟踪系统。 余额检查请求来自 Web 服务或交互式语音应答 (IVR) 系统。 有关方案的详细信息，请参阅[了解面向服务的解决方案](../core/understanding-the-service-oriented-solution.md)。  
  
 此开发人员指南提供了构建面向服务的体系结构解决方案的 Woodgrove Bank 方案的一种方法。 该指南首先考虑行业标准的模式方面可能的解决方案。 "面向服务的解决方案中的模式"开始该模式的翻译为 BizTalk 应用程序的相应的项目。 下一步的部分中，"组件的面向服务的解决方案，"汇总了应用程序和它们之间的关系的各个组成部分。 实现重点部分讨论了区域-例如，使用企业单一登录，这是必需的特定工作以满足方案的条件。 "监视面向服务的解决方案使用 BAM"介绍了该解决方案如何使用 BAM API 来跟踪请求的进度和结果。 在"版本控制面向服务的解决方案"和"扩展面向服务的解决方案"部分建议的扩展或修改该解决方案的方法。 参考部分列出了解决方案中的文件，并提供对消息的引用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [面向服务的解决方案中的模式](../core/patterns-in-the-service-oriented-solution.md)  
  
-   [面向服务的解决方案的组件](../core/components-of-the-service-oriented-solution.md)  
  
-   [面向服务的解决方案的实施要点](../core/implementation-highlights-of-the-service-oriented-solution.md)  
  
-   [监视面向服务的解决方案使用 BAM](../core/monitoring-the-service-oriented-solution-with-bam.md)  
  
-   [版本控制服务面向解决方案](../core/versioning-the-service-oriented-solution.md)  
  
-   [扩展面向服务的解决方案](../core/scaling-the-service-oriented-solution.md)  
  
-   [面向服务的解决方案参考](../core/service-oriented-solution-reference.md)