---
title: 失败消息和 ErrorCollection 对象 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- failed messages, ErrorCollection objects
- ErrorCollection objects
ms.assetid: 8a2ff3b5-d7a0-4595-8b74-3133e9e3a821
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4f9fd17807d9bc1b92b1eae1ac75662843c8e17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993158"
---
# <a name="failed-messages-and-errorcollection-objects"></a>失败的消息和 ErrorCollection 对象
除了修饰具有升级属性，Microsoft 的失败的消息[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]将失败的消息发布到 MessageBox 数据库使用的其他消息*一部分*称为**ErrorSegment**. 此错误的部分包含表示 XML **ErrorCollection**对象。 A4SWIFT 拆装器填充**ErrorCollection**在每个阶段中的消息处理 （分析，XML 验证和业务规则引擎 (BRE) 验证） 的对象。  
  
 **ErrorCollection**对象是一系列*错误对象*，其中每个表示特定错误或失败消息处理过程。 利用各种错误对象包含有关单个故障 （例如消息和失败的描述中的位置） 的详细信息。  
  
 有关详细信息**ErrorCollection**应用程序编程接口 (API) 和使用情况详细信息，请参阅 ErrorCollection 类。 有关各个错误的对象的详细信息，请参阅 ErrorBase 类 （错误对象的基类）、 BreValidationError 类、 ParseError 类和 XmlValidationError 类。  
  
 本部分包含：  
  
-   [扩展捕获和消息修复的解决方案](../../adapters-and-accelerators/accelerator-swift/extending-the-solution-for-capture-and-message-repair.md)