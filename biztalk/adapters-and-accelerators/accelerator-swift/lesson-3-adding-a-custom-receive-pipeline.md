---
title: "第 3 课： 添加自定义接收管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, creating custom pipelines
- custom pipelines
ms.assetid: 1917b8e2-4f1c-4c20-abe4-ea18a406eeeb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76abee50cce743dde6c62ea078f5ef9dada0c998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-3-adding-a-custom-receive-pipeline"></a>第 3 课： 添加自定义接收管道
在本课中，你将创建使用 BizTalk 管道设计器的自定义接收管道。 自定义接收管道是一种适配器之前接收消息之后, 在消息运行的管道[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]将其发布到 MessageBox 数据库。  
  
 配置自定义管道将该 SWIFT 反汇编程序 (DASM) 组件。 SWIFT 反汇编程序采用 SWIFT 格式的平面文件和将转换时或解析，为基于 XML 的表示形式，SWIFT 消息的内容的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以使用。  
  
 在上一步中添加 MT103 运行时架构 ([第 2 课： 添加项目引用](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) 是使用用于转换的格式。  
  
### <a name="to-create-a-new-custom-receive-pipeline"></a>若要创建新的自定义接收管道  
  
1.  在解决方案资源管理器，右键单击**SWIFTPipelines**项目，指向**添加**，然后单击**新项**。  
  
2.  在添加新项-SWIFTPipelines 对话框中，单击**管道文件**在类别窗格中，然后选择**接收管道**从模板窗格。  
  
3.  在**名称**框中，键入**MT103ReceivePipeline.btp**。  
  
4.  单击**添加**以 BizTalk 管道设计器中打开空白的管道。  
  
 在 BizTalk 管道设计器中显示空的管道。 Visual Studio 还会向解决方案资源管理器的新管道 SWIFTPipelines 项目下添加。  
  
 继续执行[第 4 课： 向工具箱添加 SWIFT 汇编程序和反汇编程序](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)。