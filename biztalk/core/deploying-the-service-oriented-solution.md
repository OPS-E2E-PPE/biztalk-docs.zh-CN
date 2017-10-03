---
title: "部署服务面向解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, service solution tutorial
- deploying, tutorials
- service solution tutorial, deploying
- service solution tutorial, background information
- tutorials, deploying
ms.assetid: 88d4d28d-9031-4fb8-ab62-04ee27949673
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7246635c4e0d55fd424fd0052eee91e118c8cb17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-the-service-oriented-solution"></a>部署服务面向解决方案
面向服务的结构 (SOA) 是一种用于构建分布式系统的方法。 面向服务的解决方案演示了如何将使用不同协议的几种后端系统聚合为客户端可以使用的单个服务。 此解决方案将服务与可确保送达和性能特征的方法相集成。  
  
 面向服务的解决方案以服务级别协议方案为蓝图构建而成，在服务级别协议方案中，BizTalk Server 以及与其连接的业务 (LOB) 应用程序服务器可以有三秒钟的时间响应服务请求。 这三秒中的一秒可由 BizTalk Server 占用。  
  
 本部分中的主题介绍了如何在单台计算机上以及多台生产服务器上安装和测试面向服务的解决方案。  
  
> [!NOTE]
>  有三种版本的面向服务解决方案： 适配器、 嵌入式和存根 （stub）。 有关面向服务的解决方案的三个版本之间的差异的详细信息，请参阅[了解服务面向解决方案](../core/understanding-the-service-oriented-solution.md)。  
  
 **读取器指南**  
  
 本文档假定您熟悉 BizTalk Server、Windows Server 和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 它还假定你已了解有关企业应用程序集成和 Web 服务的基本概念。 此外，我们建议你熟悉如何使用生成应用程序[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和你熟悉创建项目、 设置引用，以及使用调试模式下调试和测试你的解决方案。 有关先决条件的技能和知识 IT 专业人员和开发人员的详细信息，请参阅[先决条件技能和知识](../core/prerequisite-skills-and-knowledge5.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [服务开发人员计算机设置面向解决方案](../core/developer-machine-setup-for-the-service-oriented-solution.md)