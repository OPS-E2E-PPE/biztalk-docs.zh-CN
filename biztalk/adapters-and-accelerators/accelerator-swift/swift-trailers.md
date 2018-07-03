---
title: SWIFT 尾部 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT Trailer schema
- schemas, SWIFT
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: b6d64584-0514-4c87-98c0-33755efc4695
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1457c05b37c3f5b1dfcc5887c1a3f6ce27fcb0d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004838"
---
# <a name="swift-trailers"></a>SWIFT 尾部
每个 SWIFT 消息具有所需的消息交换和安全要求的一个或多个尾部。 系统尾部，如果适用，请按照用户尾部。 每个尾部尾部块中的将显示在由进一步对大括号分隔 subblock。 每个 subblock 开头指示后接一个冒号的尾部类型的三个字母。  
  
 SWIFT 尾部架构 (SWIFT Trailer.xsd) 包含以下格式：  
  
- 文本块的结束分隔符  
  
- 用户尾部 （用户和系统信息）  
  
- 系统尾部  
  
  文本块的结束分隔符是"--}"。 尾部块开头"{5:"。 尾部块的内容包括用户信息 （校验和、 消息身份验证、 专有身份验证等） 和系统信息 （延迟的消息、 消息引用，可能的重复消息等）。 添加的 SWIFT 尾部还提供第三个块中，分隔"{s:"。 *SWIFT 用户手册*，"查找服务说明"主题，详细介绍块 5 的内容。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 不会验证内容块 s。  
  
  实际 FIN 接口或 SWIFT 网络将追加尾部。 如果消息中包含尾部时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收消息，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]携带消息尾部。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 如果消息不包含尾部不会引发错误时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收的消息。 作为使用标头，所有尾部项，包括块本身，都是可选中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。  
  
  本部分包含：  
  
- [用户尾部](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
- [系统尾部](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a>请参阅  
 [处理架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)