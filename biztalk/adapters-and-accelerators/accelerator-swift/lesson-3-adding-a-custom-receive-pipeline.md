---
title: 第 3 课： 添加自定义接收管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating custom pipelines
- custom pipelines
ms.assetid: 1917b8e2-4f1c-4c20-abe4-ea18a406eeeb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5238dac95df214a25c130369b134bc155212516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993742"
---
# <a name="lesson-3-adding-a-custom-receive-pipeline"></a>第 3 课： 添加自定义接收管道
在本课程中创建自定义接收管道使用 BizTalk 管道设计器。 自定义接收管道是一种管道之后适配器收到消息之后，之前对消息运行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]将其发布到 MessageBox 数据库。  
  
 配置自定义管道以使用 SWIFT 反汇编程序 (DASM) 组件。 SWIFT 反汇编程序采用 SWIFT 格式的平面文件并将转换时或分析，为基于 XML 的表示形式，SWIFT 消息的内容的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以使用。  
  
 在上一步中添加的 MT103 运行时架构 ([第 2 课： 添加项目引用](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) 是用于转换的格式。  
  
### <a name="to-create-a-new-custom-receive-pipeline"></a>若要创建新的自定义接收管道  
  
1. 在解决方案资源管理器中右键单击**SWIFTPipelines**项目，指向**添加**，然后单击**新项**。  
  
2. 在添加新项-SWIFTPipelines 对话框中，单击**管道文件**在类别窗格中，然后选择**接收管道**从模板窗格。  
  
3. 在中**名称**框中，键入**MT103ReceivePipeline.btp**。  
  
4. 单击**添加**若要在 BizTalk 管道设计器中打开空白的管道。  
  
   BizTalk 管道设计器中显示空管道。 Visual Studio 还会向解决方案资源管理器的新管道 SWIFTPipelines 项目下添加。  
  
   请继续执行[第 4 课： 将 SWIFT 汇编程序和反汇编程序添加到工具箱](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)。