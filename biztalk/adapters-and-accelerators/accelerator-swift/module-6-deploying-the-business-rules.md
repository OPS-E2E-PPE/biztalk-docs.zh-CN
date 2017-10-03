---
title: "模块 6： 部署业务规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tutorial, deploying business rules
- deploying, business rules
- business rules
ms.assetid: e8fb8993-3450-4795-80fd-ff28bff8fe97
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e890456b7ff3e467a0f513a261d12a52f92689f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="module-6-deploying-the-business-rules"></a>模块 6： 部署业务规则
在此模块中，你部署的业务规则，确认你的安装日志，并确认使用业务规则编辑器工具部署。  
  
 使用业务规则以确保[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]消息遵循格式规范、 字段规范和验证的网络规则全球 Interbank 财务电信 (SWIFT) 标准互联网协会中定义。 格式规范适用于整个消息的结构和字段规范详细信息消息中的每个字段。 网络验证规则应用于跨字段验证和复杂本质。  
  
 A4SWIFT 提供 XSD 架构规范，为每个消息。 A4SWIFT 反汇编程序 (DASM) 和汇编程序 (ASM) 使用架构来分析或序列化和验证本机平面文件消息。 验证仅限于格式规范和字段规范架构进行编码。 但是，不能对某些格式进行编码，并且字段相关的规则，架构中。  
  
 A4SWIFT 还包括一套按照 SWIFT 标准版本指南 (SRG) 的业务规则。 BizTalk Server 业务规则引擎 (BRE) 调用 A4SWIFT 策略，并强制执行 A4SWIFT 业务规则。  
  
 这些业务规则是包含由于复杂的验证与格式和字段，和将超出架构的自然功能的网络验证规则。 在接收或发送管道中的 SWIFT DASM 或 ASM 组件调用 BRE。  
  
 通过更改将验证打开或关闭**BREValidation** DASM 在你的管道中的属性。  
  
 本部分包含：  
  
-   [第 1 课： 部署相关的业务规则](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)  
  
-   [第 2 课： 确认使用业务规则 Composer 工具部署](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)