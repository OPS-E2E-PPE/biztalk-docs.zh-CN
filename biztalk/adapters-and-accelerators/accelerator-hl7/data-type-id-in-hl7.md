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
ms.openlocfilehash: f90b215857f0d0fea5e1bd899e1101b117b8ecbe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255595"
---
# <a name="data-type-id-in-hl7"></a>HL7 中的数据类型 ID
HL7 2.1 版，对于数据类型 ID 是未定义的数据类型的占位符。 其用法的示例如下：  
  
- ST 字段的窗体中的数据类型为 SI (序列 ID)。  
  
- NM 字段的窗体中的数据类型是复合域。  
  
  以下是专门定义的复合数据类型的示例：  
  
- CK:使用数字的复合 ID。 例如：  
  
  ```  
  |128952^6^M11|  
  ```  
  
- CN:复合 ID 号和名称。 例如：  
  
  ```  
  |12372^RIGGINS^JOHN^""^MD|  
  |12372|  
  |^RIGGINS^JOHN^""^MD|  
  ```  
  
- CQ:个单位的复合数量。 例如：  
  
  ```  
  |123.7^ML|  
  ```  
  
- CE:编码的元素。 例如：  
  
  ```  
  |54.21^Laparoscopy^I9C^42112^^AS4|  
  ```  
  
  此数据类型是本地化和站点定义。 此外，HL7 2.1 版不提供此 HL7 Access 数据库中的数据类型的覆盖率。 用于生成您的架构，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 假定 HL7 V2.2 数据类型是否有效，并使用此信息来生成架构。 具体取决于架构中的使用情况，相应的数据类型必须使用，这意味着，数据类型必须替换为 CK、 CQ、 CE、 ST ^ SI，依次类推。  
  
## <a name="see-also"></a>请参阅  
 [数据类型](../../adapters-and-accelerators/accelerator-hl7/data-types.md)   
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)