---
title: HL7 中的数据类型 ID |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, data type ID
- data types, messages
- messages, data types
ms.assetid: d1412886-ff0b-4333-b01e-1c3ae45240e2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d7251ce1c041ebfd2f523e3304bd253fec22fb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983006"
---
# <a name="data-type-id-in-hl7"></a>HL7 中的数据类型 ID
HL7 2.1 版，对于数据类型 ID 是未定义的数据类型的占位符。 其用法的示例如下：  
  
- ST 字段的窗体中的数据类型为 SI (序列 ID)。  
  
- NM 字段的窗体中的数据类型是复合域。  
  
  以下是专门定义的复合数据类型的示例：  
  
- CK： 复合 ID 为数字。 例如：  
  
  ```  
  |128952^6^M11|  
  ```  
  
- CN： 复合 ID 号和名称。 例如：  
  
  ```  
  |12372^RIGGINS^JOHN^""^MD|  
  |12372|  
  |^RIGGINS^JOHN^""^MD|  
  ```  
  
- 个单位的 CQ： 复合数量。 例如：  
  
  ```  
  |123.7^ML|  
  ```  
  
- CE： 编码的元素。 例如：  
  
  ```  
  |54.21^Laparoscopy^I9C^42112^^AS4|  
  ```  
  
  此数据类型是本地化和站点定义。 此外，HL7 2.1 版不提供此 HL7 Access 数据库中的数据类型的覆盖率。 用于生成您的架构，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 假定 HL7 V2.2 数据类型是否有效，并使用此信息来生成架构。 具体取决于架构中的使用情况，相应的数据类型必须使用，这意味着，数据类型必须替换为 CK、 CQ、 CE、 ST ^ SI，依次类推。  
  
## <a name="see-also"></a>请参阅  
 [数据类型](../../adapters-and-accelerators/accelerator-hl7/data-types.md)   
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)