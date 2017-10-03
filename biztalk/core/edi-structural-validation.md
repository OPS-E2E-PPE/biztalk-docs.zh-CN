---
title: "EDI 结构验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87086614-5616-441d-915c-2979c63c6e2f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505b9ac55eff0b6adb249d11788308f03902f1d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-structural-validation"></a>EDI 结构验证
X12 和 EDIFACT 编码的 EDI 规范为 EDI 交换的结构定义了特定规则和约定。 EDIReceivePipeline 中的 EDI 拆装器将验证每条接收的消息的信封是否符合这些结构规则。 EDISendPipeline 根据这些规则生成要发送的每个消息并在发送前验证信封。  
  
 结构验证可确保存在所需的标头和尾部。 结构完整性检查包括段检查、循环排序检查和计数检查。 将始终执行这些检查以确保正确解析或序列化文档。 执行此验证即使**EDI 类型验证**和/或**扩展验证**将禁用这些选项。 将挂起的交换中失败的基本结构验证，即使**EDI 类型验证**和/或**扩展验证**将禁用这些选项。  
  
 标头和尾部内数据元素的值以及标头/尾部与数据元素的分隔方式均由协议确定。 它们是通过架构验证进行验证的。  
  
 有关信封和标头和拖车安排每个集内的内容的详细信息，请参阅[EDI 消息结构](../core/edi-message-structure.md)。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 消息验证](../core/edi-message-validation.md)