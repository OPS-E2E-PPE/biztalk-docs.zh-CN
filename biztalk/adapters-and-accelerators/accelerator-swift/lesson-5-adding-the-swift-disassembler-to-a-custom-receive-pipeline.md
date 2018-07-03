---
title: 第 5 课： 将 SWIFT 反汇编程序添加到自定义接收管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, adding disassembler
- custom pipelines
- disassembler, custom pipelines
- disassembler, adding to pipelines
ms.assetid: 96e26d97-bfab-448f-b7b6-3bc2ec3ccebf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0af7635b424a74b160991b1d6cfdeb53bfb7f23f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971294"
---
# <a name="lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline"></a>第 5 课： 将 SWIFT 反汇编程序添加到自定义接收管道
在本课中，您将自定义 SWIFT 反汇编程序 (DASM) 添加到你的管道。 DASM 管道组件是将分批消息划分为各个文档的管道组件。  
  
 MicrosoftBizTalk 服务器中提供的 DASM 管道组件包括：  
  
- 平面文件拆装器  
  
- BizTalk 框架拆装器  
  
- XML 拆装器  
  
  Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]添加其他的 SWIFT 反汇编程序。  
  
### <a name="to-add-the-swift-custom-disassembler-to-your-pipeline"></a>若要将 SWIFT 的自定义拆装器添加到你的管道  
  
1. 从视图菜单中，单击**工具箱**。  
  
2. 从**BizTalk 管道组件工具箱**，单击**SWIFT 反汇编程序**将其拖到**拖至此处**下面的框**拆装**阶段中的形状**BizTalk 管道设计器**。 将保留**SWIFT 反汇编程序**中所选的形状**BizTalk 管道设计器**。  
  
3. 在中**属性**窗格中，选择**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**有关**SWIFT 标头架构**属性。  
  
   > [!NOTE]
   >  不要混淆**SWIFT 标头架构**和消息标头架构。 必须设置**SWIFT 标头架构**步骤 3 中。  
  
4. 在中**属性**窗格中，确保**BRE 验证**属性设置为**True**。  
  
   > [!NOTE]
   >  本教程后面跟有解释的业务规则引擎 (BRE)。  
  
5. 在中**属性**窗格中，确保**XML 验证**属性设置为**True**。  
  
6. 在中**属性**窗格中，确保**入站解除批处理**属性设置为**False**。  
  
7. 上**文件**菜单中，选择**全部保存**以保存所做的更改。  
  
   请继续执行[第 6 课： 创建自定义发送管道](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)。