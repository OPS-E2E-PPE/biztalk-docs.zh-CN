---
title: 系统尾部 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: 2fd49be9-afe8-47c6-a613-fa469faa2126
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 995ed2a0214b9de3f50c7aac2298138da1d6df73
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529736"
---
# <a name="system-trailers"></a>系统尾部
系统尾部传达有关 SWIFT 消息的其他或特殊详细信息。 如果任何第三个系统尾部都存在，它们将按以下顺序发生。 其余系统尾部可以任何顺序出现。  
  
|尾部代码|“属性”|  
|------------------|----------|  
|**CHK**|校验和|  
|**SYS**|系统发起消息|  
|**TNG**|培训|  
|**PDM**|可能的重复消息|  
|**DLM**|延迟的消息|  
|**MRF**|消息引用|  
  
- **系统发起消息 (SYS) 尾部。** 系统消息或服务消息，生成系统 PLT，具有 SYS 尾部。 所有请求的服务标识符为 01 的系统消息、 包含该请求的 MIR 和可能包含的时间。  
  
   以下代码是 SYS 尾部格式示例：  
  
  ```  
  {SYS:[<time><mir>]}  
  ```  
  
- **测试和定型 (TNG) 消息尾部。** TNG 尾部是必需的 FIN 和 GPA 消息 （带 01 的服务标识符） 发送的或传递到测试和定型逻辑终端 (LT)。 此尾部具有一个标记，并没有值。  
  
   以下代码是 TNG 尾部格式示例：  
  
  ```  
  {TNG:}  
  ```  
  
- **可能重复发出 (PDE) 尾部。** 消息的目标使用 PDE 尾部。 它仅适用于查找用户的消息 （带 01 的服务标识符） 和保留对银行消息的消息类别。 系统可能包含多个 PDEs。 系统不验证的顺序也不限制 （除了最大消息长度） 的数量。  
  
   系统将接受格式正确 PDE 尾部应用于用户系统的消息，但不是处理它们。 这意味着，系统不会检查以查看原始消息是否存在。 因此，系统可能会处理两次发送 PDE 尾部的检索请求，如果系统接收到原始消息。  
  
   以下代码是 PDE 尾部格式示例：  
  
  ```  
  {PDE:[<time><mir>]}  
  where <time><mir> refers to the emission of the previous possible issue  
  ```  
  
- **延迟的消息 (DLM) 尾部。** DLM 尾部添加到已超过其过时期限内的所有查找用户的输出消息。 如果此尾部出现在 GPA 或 FIN 系统消息，您可以忽略它。 此尾部具有一个标记，并没有值。  
  
   过时段如下所示：  
  
  - U = 15 分钟  
  
  - N = 100 分钟  
  
    以下代码是 DLM 尾部格式示例：  
  
  ```  
  {DLM:}  
  ```  
  
- **可能的重复消息 (PDM) 尾部。** PDM 尾部由系统添加到任何输出消息 （GPA 和具有 01 服务标识符 FIN） 需要重新发送，因为以前的传递可能无效。 如果系统 PLT 收到报表请求 PDM 尾部时，响应的普通 PDM （不带可选传递引用）。 其他 pdm 联系可能由于未成功传送尝试添加到用户。  
  
   以下代码是 PDM 尾部格式示例：  
  
  ```  
  {PDM:[<time><mor>]}  
  where <time> and the Message Output Reference <mor> are that of the previous attempt  
  ```  
  
- **消息引用 (MRF) 尾部。** MRF 尾部 MT 096 FIN 复制到中央机构消息中指定原始用户消息的消息的引用。  
  
   以下代码是 MRF 尾部格式示例：  
  
  ```  
  {MRF:<date><full-time><mir>}  
  where <mir> is that of the original user message whose fields are copied in the MT 096 FIN  
  Copy to Central Institution Message  
  ```  
  
  > [!NOTE]
  >  MRF 尾部是特定于 FIN 复制和自动生成在 MT 096 FIN 复制到中央机构消息中。 您只能使用此尾部字段中 109 MT 096 FIN 复制到中央机构消息来标识 MT 097 是响应 MT 096。 MRF 格式会发生变化。  
  
## <a name="see-also"></a>请参阅  
 [处理架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)