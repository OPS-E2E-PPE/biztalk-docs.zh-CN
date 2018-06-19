---
title: 数据类型中 HL7 ID |Microsoft 文档
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
ms.openlocfilehash: 2c5778e772d21cb5f9c6759c127c92ebe74b6f5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204517"
---
# <a name="data-type-id-in-hl7"></a>HL7 中的数据类型 ID
对于 HL7 2.1 版，数据类型 ID 是未定义的数据类型的占位符。 其使用情况的示例如下：  
  
-   ST 字段的窗体中的数据类型是 SI (序列 ID)。  
  
-   NM 字段的窗体中的数据类型是复合字段。  
  
 专门定义的复合数据类型的示例如下：  
  
-   带校验位 CK： 复合 ID。 例如：  
  
    ```  
    |128952^6^M11|  
    ```  
  
-   CN： 复合 ID 号和名称。 例如：  
  
    ```  
    |12372^RIGGINS^JOHN^""^MD|  
    |12372|  
    |^RIGGINS^JOHN^""^MD|  
    ```  
  
-   使用的单位 CQ： 复合数量。 例如：  
  
    ```  
    |123.7^ML|  
    ```  
  
-   CE： 编码的元素。 例如：  
  
    ```  
    |54.21^Laparoscopy^I9C^42112^^AS4|  
    ```  
  
 此数据类型是本地化，且站点定义。 此外，HL7 2.1 版不提供此 HL7 访问数据库中的数据类型则覆盖率。 用于生成你的架构， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 假定 HL7 V2.2 数据类型有效，并使用此信息生成架构。 具体取决于架构中使用，相应的数据类型必须使用，这意味着，必须使用 CK、 CQ、 CE、 ST 替换的数据类型 ^ SI，依次类推。  
  
## <a name="see-also"></a>另请参阅  
 [数据类型](../../adapters-and-accelerators/accelerator-hl7/data-types.md)   
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)