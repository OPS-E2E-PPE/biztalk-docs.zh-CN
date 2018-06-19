---
title: 系统拖车安排 |Microsoft 文档
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
ms.openlocfilehash: a0a8c5b7be12a90aa2d31e828298cf7b95834036
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214077"
---
# <a name="system-trailers"></a>系统拖车安排
系统拖车安排传达有关 SWIFT 消息的其他或特殊的详细信息。 如果任一第三个系统拖车安排都存在，它们将按以下顺序发生。 剩余系统拖车安排可以按任意顺序出现。  
  
|电影预告片代码|Name|  
|------------------|----------|  
|**选项**|Checksum|  
|**SYS**|系统发起消息|  
|**TNG**|培训|  
|**PDM**|可能的重复消息|  
|**DLM**|延迟的消息|  
|**MRF**|消息引用|  
  
-   **系统将产生消息 (SYS) 预告片。** 该系统消息或服务消息，系统 PLT 的生成，具有 SYS 预告片。 所有请求的系统具有 01 的服务标识符的消息、 包含在请求 MIR 和可能包含的时间。  
  
     下面的代码是 SYS 预告片格式的示例：  
  
    ```  
    {SYS:[<time><mir>]}  
    ```  
  
-   **测试和定型消息 (TNG) 预告片。** TNG 预告片是 FIN 和 GPA 消息 （具有 01 的服务标识符） 发送的或传递到的测试和定型逻辑终端 (LT) 必需的。 此预告片具有仅，一个标记和任何值。  
  
     下面的代码演示了 TNG 预告片格式：  
  
    ```  
    {TNG:}  
    ```  
  
-   **可能重复发出 (PDE) 预告片。** 消息的目标使用 PDE 预告片。 它仅适用于 FIN 用户和用户消息 （01 服务标识符），并为银行消息保留消息类别。 系统可能包含多个 PDEs。 系统不验证顺序也不限制 （除外最大消息长度） 数。  
  
     系统接受格式正确 PDE 拖车安排应用于用户与系统的消息，但不是处理它们。 这意味着，系统不会检查以查看原始消息是否存在。 因此，系统可能会处理两次发送 PDE 预告片检索请求 — 如果系统接收原始消息。  
  
     下面的代码演示了 PDE 预告片格式：  
  
    ```  
    {PDE:[<time><mir>]}  
    where <time><mir> refers to the emission of the previous possible issue  
    ```  
  
-   **延迟的消息 (DLM) 预告片。** DLM 预告片将添加到已超过其过时期限内的所有 FIN 用户和用户输出消息。 如果此预告片出现在 GPA 或 FIN 系统消息，则可以忽略它。 此预告片具有仅，一个标记和任何值。  
  
     过时段如下所示：  
  
    -   U = 15 分钟  
  
    -   N = 100 分钟  
  
     下面的代码是的 DLM 预告片格式示例：  
  
    ```  
    {DLM:}  
    ```  
  
-   **可能的重复消息 (PDM) 预告片。** PDM 预告片由系统添加到任何输出消息 （GPA 和具有 01 的服务标识符 FIN） 因为以前的传递可能不是有效重新发送。 如果系统 PLT 收到报表请求 PDM 尾端时，该响应包括纯 PDM （不带可选传递参考中）。 可以将其他 PDMs 由于未成功传送尝试添加到用户。  
  
     下面的代码演示了 PDM 预告片格式：  
  
    ```  
    {PDM:[<time><mor>]}  
    where <time> and the Message Output Reference <mor> are that of the previous attempt  
    ```  
  
-   **消息引用 (MRF) 预告片。** MRF 预告片 MT 096 FIN 复制至中央机构消息中指定原始用户消息的消息的引用。  
  
     下面的代码演示了 MRF 预告片格式：  
  
    ```  
    {MRF:<date><full-time><mir>}  
    where <mir> is that of the original user message whose fields are copied in the MT 096 FIN  
    Copy to Central Institution Message  
    ```  
  
    > [!NOTE]
    >  MRF 预告片特定于 FIN 副本，并在 MT 096 FIN 复制到中央机构消息中自动生成。 你只能使用此预告片字段中 109 MT 096 FIN 复制到中央机构消息以确定向其 MT 097 是一种响应 MT 096。 MRF 的格式进行更改。  
  
## <a name="see-also"></a>另请参阅  
 [使用架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)