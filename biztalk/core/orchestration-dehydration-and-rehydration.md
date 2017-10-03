---
title: "业务流程冻结和 Rehydration |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57d7c0bf-a707-4ebd-afab-e75dd80c3c34
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23ec36d960173c9ce912bb89a38b1df9590f84e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-dehydration-and-rehydration"></a>业务流程冻结和 Rehydration
在同时运行大量长期业务流程时，内存和性能可能存在问题。 业务流程引擎通过“冻结”和“解除冻结”业务流程实例来解决这些问题。  
  
 冻结是将业务流程的状态序列化到 SQL Server 数据库中的过程。 Rehydration 是此过程的反向： 反序列化从数据库的业务流程的上次运行状态。 冻结用于通过减少必须在内存中同时实例化的业务流程数来最大程度地降低系统资源的使用。  
  
## <a name="dehydration"></a>冻结  
 业务流程引擎可以确定某个业务流程实例已经空闲了相当长的一段时间。 它计算阈值来确定它将在多长时间等待各种操作做好准备，并超出这些阈值，如果它 dehydrates 实例。 在以下情况下会发生冻结：  
  
-   如果业务流程正在等待接收消息，并且等待的时间超过了引擎所确定的阈值。  
  
-   当业务流程"侦听"一条消息，你使用时的表现**侦听**形状，并没有分支触发之前由引擎确定的阈值。 唯一的例外是当**侦听**形状包含激活接收。  
  
-   当业务流程中的延迟超过引擎所确定的阈值时。  
  
 引擎 dehydrates 实例的保存状态，并释放的实例所需的内存。 通过冻结休眠业务流程实例过程中，引擎使大量的长时间运行业务流程，以同时在同一台计算机上运行。  
  
 你可以设置 12 属性来配置 BizTalk Server 中的冻结工作原理。 此部分中的主题列出并描述了这些属性和其默认值，并且会讨论如何各种不同的值影响冻结行为。  
  
## <a name="rehydration"></a>Rehydration  
 可以触发业务流程引擎，以便在消息接收后或在延迟形状中指定的超时到期后解除冻结某一业务流程实例。 然后将已保存业务流程实例加载到内存，将还原其状态，并从它暂停的点运行它。 有关使用形状中业务流程的详细信息，请参阅[Orchestration 形状](../core/orchestration-shapes.md)。  
  
 可以配置业务流程以便在多台服务器上运行。 在冻结某一业务流程实例后，可以在其中任何服务器上解除对该实例的冻结。 如果一台服务器出现故障，引擎将继续在不同服务器上，在从以前的状态继续运行业务流程。 该引擎还可利用此功能，以实现跨服务器的负载平衡。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [从 BizTalk Server 2004 冻结策略中的更改](../core/changes-in-dehydration-policy-from-biztalk-server-2004.md)  
  
-   [冻结默认属性](../core/dehydration-default-properties.md)  
  
-   [如何计算冻结](../core/how-to-calculate-dehydration.md)  
  
-   [示例冻结计算](../core/sample-dehydration-calculation.md)  
  
-   [业务流程冻结性能计数器](../core/orchestration-dehydration-performance-counters.md)  
  
-   [BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)  
  
-   [其他活动可以影响冻结行为](../core/other-activities-that-can-affect-dehydration-behavior.md)