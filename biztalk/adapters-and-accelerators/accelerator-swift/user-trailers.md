---
title: "用户拖车安排 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: 340d9fc8-467b-4cba-b69f-eb761767deaa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dc2d7f2a3dd21d35bb33fa625f59aa27c04e656
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="user-trailers"></a>用户拖车安排
用户预告片除外，选项尾端是可选的当存在时，将按以下顺序发生：  
  
|电影预告片代码|Name|  
|------------------|----------|  
|MAC|消息验证代码|  
|PAC|专有身份验证代码|  
|选项|Checksum|  
|TNG|培训|  
|PDE|可能的重复发出|  
  
-   **消息身份验证代码 (MAC) 预告片。** 允许接收用户的身份验证。 MAC 预告片跟身份验证结果。 此预告片是 FIN 应用程序中的大多数用户和用户消息类别必需的。  
  
     当使用 FIN 复制服务时，PAC 尾部 （如果有） 将遵循 MAC 预告片。 下面的代码演示了 MAC 尾部：  
  
    ```  
    {MAC:<authentication-result>}  
    where <authentication-result> = 8!h  
    ```  
  
-   **专有身份验证代码 (PAC) 预告片。** 仅在使用双重身份验证选项时，将 FIN 复制服务中使用 PAC 预告片。 如果存在，块 5 的 FIN 用户和用户消息后，MAC 尾端立即包括 PAC 预告片。 如果存在，此结果的消息，115，字段的值的块 4 的提取字段计算和\<身份验证结果 > 的 MAC 电影预告片复制服务以使用双重身份验证。  
  
     因此，PAC 计算中包含的结束块指示器 （CrLf-） 和字段的定义如下：  
  
    -   前四个字符都是 CrLf:  
  
    -   字段和分隔符都存在，即 32A: 20，:，依次类推。  
  
    -   所有的子字段和其分隔符存在。  
  
     下面的代码演示了 PAC 预告片格式：  
  
    ```  
    {PAC:[<authentication-result>]}  
    where <authentication-result> is mandatory on input messages only and  
    <authentication-result> = 8!h  
    ```  
  
-   **选项 （校验和） 预告片 （对于所有 FIN 消息是必需的）**  
  
     选项电影预告片对于所有 FIN 消息是必需的和计算根据接收方的地址 (第 9 个字符的 12 个字符替换为*X* plus 文本块)。 此预告片允许系统以及 CBT 以检查该消息未损坏，由于系统故障或未检测到的传输错误。  
  
     下面的代码演示了选项预告片格式：  
  
    ```  
    {CHK:<checksum-result>}  
    where <checksum-result> = 12!h  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [使用架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)