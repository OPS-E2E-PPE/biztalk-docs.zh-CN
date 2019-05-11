---
title: EDI 结构验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87086614-5616-441d-915c-2979c63c6e2f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 422449a9720b78a65b4934fbf17d255e84678613
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350226"
---
# <a name="edi-structural-validation"></a>EDI 结构验证
X12 和 EDIFACT 编码的 EDI 规范定义的 EDI 交换结构的特定规则和约定。 EDIReceivePipeline 中的 EDI 拆装器将验证每个收到的消息的信封符合这些结构规则。 EDISendPipeline 生成要发送这些规则根据每个消息，并在发送前验证信封。  
  
 结构验证确保存在必需的标头和尾部。 结构完整性检查包括段、 循环排序和计数检查。 始终执行这些检查以确保该文档将分析或正确序列化。 执行此验证，即使**EDI 类型验证**和/或**扩展验证**选项处于禁用状态。 未通过基本结构验证的交换将挂起，即使**EDI 类型验证**和/或**扩展验证**选项处于禁用状态。  
  
 标头和尾部内的数据元素和如何分隔的标头/尾部与数据元素的值由协议确定。 这些架构验证通过验证。  
  
 有关信封以及其中每个组标头和尾部的内容的详细信息，请参阅[EDI 消息结构](../core/edi-message-structure.md)。  
  
## <a name="see-also"></a>请参阅  
 [EDI 消息验证](../core/edi-message-validation.md)