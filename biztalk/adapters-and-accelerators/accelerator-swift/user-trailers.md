---
title: 用户尾部 |Microsoft Docs
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
ms.assetid: 340d9fc8-467b-4cba-b69f-eb761767deaa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10bc0d4d0fcdb36311e0590d9ae04239db168ed7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010214"
---
# <a name="user-trailers"></a>用户尾部
用户尾部，除了 CHK 尾部是可选的当存在时，将按以下顺序发生：  
  
|尾部代码|“属性”|  
|------------------|----------|  
|MAC|消息身份验证代码|  
|PAC|专有身份验证代码|  
|CHK|Checksum|  
|TNG|培训|  
|PDE|可能的重复发出|  
  
- **消息身份验证代码 (MAC) 尾部。** 允许接收的用户进行身份验证。 MAC 尾部后跟一个身份验证结果。 此尾部是必需的 FIN 应用程序中的大多数用户的消息类别。  
  
   当使用 FIN 复制服务时，PAC 尾部 （如果存在） 遵循 MAC 尾部。 下面的代码是 MAC 尾部的示例：  
  
  ```  
  {MAC:<authentication-result>}  
  where <authentication-result> = 8!h  
  ```  
  
- **专有身份验证代码 (PAC) 尾部。** 仅当使用两次身份验证选项时，将 FIN 复制服务中使用 PAC 尾部。 如果存在，块 5 的 FIN 用户和用户消息 MAC 尾部后立即包含 PAC 尾部。 此结果进行计算的消息，第 115，字段的值的块 4 提取的字段 （如果存在） 和\<身份验证结果\>MAC 尾部的复制服务使用两次身份验证。  
  
   因此，结束块指示符 （CrLf-） 包含在 PAC 计算和的字段定义，如下所示：  
  
  - 前四个字符是 CrLf:  
  
  - 字段和分隔符都存在，即 32A:，20:，依此类推。  
  
  - 所有子字段和分隔符存在。  
  
    以下代码是 PAC 尾部格式示例：  
  
  ```  
  {PAC:[<authentication-result>]}  
  where <authentication-result> is mandatory on input messages only and  
  <authentication-result> = 8!h  
  ```  
  
- **CHK （校验和） 尾部 （对于所有 FIN 消息是必需的）**  
  
   CHK 尾部是必需的所有 FIN 消息的根据接收方的地址计算得出 (第 9 个字符的 12 个字符替换为*X*以及文本块)。 此尾部允许系统和 CBT 检查由于系统工作不正常或未检测到的传输错误消息不已损坏。  
  
   以下代码是 CHK 尾部格式示例：  
  
  ```  
  {CHK:<checksum-result>}  
  where <checksum-result> = 12!h  
  ```  
  
## <a name="see-also"></a>请参阅  
 [处理架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)