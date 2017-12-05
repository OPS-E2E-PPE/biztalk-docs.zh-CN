---
title: "第 5 课： 将 SWIFT 反汇编程序添加到自定义接收管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, adding disassembler
- custom pipelines
- disassembler, custom pipelines
- disassembler, adding to pipelines
ms.assetid: 96e26d97-bfab-448f-b7b6-3bc2ec3ccebf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0616c4adddc6e2d096624d02b968a21012ccd93b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline"></a>第 5 课： 添加自定义接收管道的 SWIFT 反汇编程序
在本课程中，你可以将自定义 SWIFT 反汇编程序 (DASM) 添加到管道。 DASM 管道组件是将一批中的消息划分为各个文档的管道组件。  
  
 中提供的 DASM 管道组件[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server 是：  
  
-   平面文件反汇编程序  
  
-   BizTalk Framework 反汇编程序  
  
-   XML 拆装器  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]添加其他的 SWIFT 反汇编程序。  
  
### <a name="to-add-the-swift-custom-disassembler-to-your-pipeline"></a>要添加到管道的 SWIFT 自定义反汇编程序  
  
1.  从视图菜单中，单击**工具箱**。  
  
2.  从**BizTalk 管道组件工具箱**，单击**SWIFT 反汇编程序**将其拖到**拖至此处**下面框**拆卸**阶段中的形状**BizTalk 管道设计器**。 保留**SWIFT 反汇编程序**中选择的形状**BizTalk 管道设计器**。  
  
3.  在**属性**窗格中，选择**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**为**SWIFT 标头架构**属性。  
  
    > [!NOTE]
    >  不要混淆**SWIFT 标头架构**和消息标头的架构。 必须设置**SWIFT 标头架构**步骤 3 中。  
  
4.  在**属性**窗格中，确保**BRE 验证**属性设置为**True**。  
  
    > [!NOTE]
    >  说明的业务规则引擎 (BRE) 遵循本教程的后面。  
  
5.  在**属性**窗格中，确保**XML 验证**属性设置为**True**。  
  
6.  在**属性**窗格中，确保**入站 Debatching**属性设置为**False**。  
  
7.  上**文件**菜单上，选择**保存所有**以保存所做的更改。  
  
 继续执行[第 6 课： 创建自定义发送管道](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)。