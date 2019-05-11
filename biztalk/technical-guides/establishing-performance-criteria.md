---
title: 建立性能标准 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 181011d1-aa74-43fe-b05a-30b043956d70
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6cd5c7b733ec85eb08acdc506d816d1a3fb1ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305656"
---
# <a name="establishing-performance-criteria"></a>建立性能标准
BizTalk Server 解决方案的性能目标通常划分为两个类别、 吞吐量或延迟之一。 本主题介绍评估吞吐量或延迟的 BizTalk Server 解决方案时应考虑的因素。  
  
> [!NOTE]  
>  优化吞吐量或延迟的 BizTalk Server 解决方案通常表示冲突的目标。 例如，可能会提高吞吐量的文件接收适配器的增加批大小，但这样做会减少延迟。 在此方案中，适配器长积累更大的批大小，这反过来将减少在某个给定消息的端到端延迟的消息。  
  
## <a name="factors-affecting-throughput-of-a-biztalk-server-solution"></a>因素会影响 BizTalk Server 解决方案的吞吐量  
 **吞吐量**-广泛测量作为 BizTalk Server 解决方案可以处理某个给定的时间间隔内的文档数。  
  
 会影响吞吐量的因素包括：  
  
-   **消息大小**– 更大的消息使用更多开销较小的消息，高于，尤其是使用映射转换和非常大，以便向文件系统映射操作期间缓冲消息。 消息大小如何影响 BizTalk Server 性能的详细信息，请参阅[如何 BizTalk Server 处理大消息](http://go.microsoft.com/fwlink/?LinkId=139293)(http://go.microsoft.com/fwlink/?LinkId=139293)。  
  
-   **消息格式**-消息接收到 BizTalk Server 在两种主要格式、 XML 文件或平面文件之一。 因为平面文件必须转换为要由 BizTalk 消息引擎处理的 XML 格式，额外的开销不会引起的平面文件处理。  
  
-   **适配器要求**– 不同适配器经常包含不同的性能功能。 例如，要求 MSDTC 事务支持的适配器将产生与不使用 MSDTC 事务的适配器相比其他开销/降低性能。 根据您的贸易合作伙伴的要求和/或内部的业务需求而异 BizTalk 解决方案所使用的适配器。  
  
-   **业务流程处理要求**– 业务流程提供用于封装极大的灵活性，并将业务流程应用于消息接收到 biztalk。 同时，业务流程使用估计的 BizTalk Server 解决方案的吞吐量时，必须考虑的开销。  
  
-   **峰值负载要求**– 大多数文档处理不一定会发生以测量的有序方式。 例如，BizTalk Server 解决方案而可能承受其在营业日结束位置的处理负荷很大百分比。 因此峰值负载要求和 BizTalk Server 解决方案的最大可承受吞吐量 (MST) 应考虑建立吞吐量条件时。 有关度量 MST 的 BizTalk Server 解决方案的详细信息，请参阅[测量最大可承受引擎吞吐量](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID=154388)和[测量最大可承受跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815).  
  
-   **文档跟踪要求**– 文档跟踪会产生在系统上的其他开销。 估计的 BizTalk 解决方案的吞吐量目标时，文档跟踪要求应为一个主要考虑因素。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 性能测试方法](../technical-guides/biztalk-server-performance-testing-methodology.md)