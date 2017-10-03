---
title: "建立性能条件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 181011d1-aa74-43fe-b05a-30b043956d70
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5317445a5cf7e1e0b3fc07ab6ac301c764501460
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="establishing-performance-criteria"></a>建立性能条件
BizTalk Server 解决方案的性能目标通常分为两个类别、 吞吐量或延迟之一。 本主题介绍评估吞吐量或延迟的 BizTalk Server 解决方案时应考虑的因素。  
  
> [!NOTE]  
>  优化吞吐量或 BizTalk Server 解决方案的延迟通常表示有冲突的目标。 例如，您可能会提高的文件的吞吐量接收适配器通过增加批大小，但这样做将减少延迟。 在此方案中适配器需要更长的累积更大的批处理大小，这反过来将减少给定消息的端到端延迟的消息。  
  
## <a name="factors-affecting-throughput-of-a-biztalk-server-solution"></a>BizTalk Server 解决方案的吞吐量的影响因素  
 **吞吐量**-广泛衡量的 BizTalk Server 解决方案可在给定的时间间隔内处理的文档数。  
  
 影响吞吐量的因素包括：  
  
-   **消息大小**– 更大的消息使用多个开销低于较小的邮件，尤其是在消息转换使用映射和都足够大，以便到文件系统映射操作期间缓冲。 有关消息大小如何影响 BizTalk Server 性能的详细信息，请参阅[如何 BizTalk 服务器进程大消息](http://go.microsoft.com/fwlink/?LinkId=139293)(http://go.microsoft.com/fwlink/?LinkId=139293)。  
  
-   **消息格式**-到 BizTalk Server 中两个主格式、 XML 文件或平面文件之一接收消息。 平面文件必须转换为要由 BizTalk 消息传送引擎处理的 XML 格式，因为其他系统开销不会引起平面文件处理。  
  
-   **适配器要求**– 不同适配器经常采用不同的性能功能。 例如，需要 MSDTC 事务的支持的适配器将产生与不使用 MSDTC 事务的适配器相比其他/低开销的性能。 根据你贸易合作伙伴的要求和/或内部的业务需求而异 BizTalk 解决方案所使用的适配器。  
  
-   **业务流程处理要求**– 业务流程提供用于封装极大的灵活性和业务流程应用到消息接收的 BizTalk。 同时，业务流程使用估计的 BizTalk Server 解决方案的吞吐量时，必须考虑的开销。  
  
-   **最大负载要求**– 大多数文档处理不一定会发生测得的有序地中。 例如，BizTalk Server 解决方案可能维持其处理负载在营业日结束对很大百分比。 因此峰值负载要求和 BizTalk Server 解决方案的最大可持续吞吐量 (MST) 应考虑建立吞吐量条件时。 有关测量 MST BizTalk Server 解决方案的详细信息，请参阅[测量最大可持续引擎吞吐量](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID = 154388) 和[衡量最大可持续跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID = 153815)。  
  
-   **文档跟踪要求**– 文档跟踪会产生系统上的其他开销。 估计 BizTalk 解决方案的吞吐量目标时，文档跟踪要求应为一个主要考虑因素。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 性能测试方法](../technical-guides/biztalk-server-performance-testing-methodology.md)