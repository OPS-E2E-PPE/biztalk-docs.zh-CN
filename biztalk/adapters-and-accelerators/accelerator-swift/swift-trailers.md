---
title: "SWIFT 拖车安排 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SWIFT Trailer schema
- schemas, SWIFT
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: b6d64584-0514-4c87-98c0-33755efc4695
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc3155ac21f55e7c61483b9287429f9b722f6a84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swift-trailers"></a>SWIFT 拖车安排
每个 SWIFT 消息具有所需的消息交换和安全要求的一个或多个拖车安排。 系统尾部如果适用，请按照用户拖车安排。 每个预告片预告片块中的将显示在由进一步对大括号分隔 subblock。 每个 subblock 开头表示跟一个冒号的电影预告片类型的三个字母。  
  
 SWIFT 尾部架构 (SWIFT Trailer.xsd) 包含以下格式：  
  
-   文本块结束分隔符  
  
-   用户拖车安排 （用户和系统信息）  
  
-   系统拖车安排  
  
 结束分隔符的文本块是"-}"。 电影预告片块开头"{5:"。 电影预告片块的内容包括用户信息 （校验和、 消息身份验证、 专有身份验证等） 和系统信息 （延迟的消息、 消息引用、 可能的重复消息和等等）。 拖车安排添加 SWIFT 还提供分隔的第三个块"{s:"。 *SWIFT 用户手册*，"FIN 服务说明"主题详细地介绍了块 5 的内容。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不会验证内容块 s。  
  
 实际的 FIN 接口或 SWIFT 网络追加拖车安排。 当消息中包含尾部时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收消息时，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]传送消息的尾部。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]如果消息不包含尾部不引发错误时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收消息。 作为标头，与所有预告片项，包括块本身，在中是可选[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。  
  
 本部分包含：  
  
-   [用户拖车安排](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
-   [系统拖车安排](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a>另请参阅  
 [使用架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)