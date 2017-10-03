---
title: "第 6 课： 创建自定义发送管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom pipelines
- send pipelines, custom pipelines
ms.assetid: 73a3a546-1e43-4b93-87d3-9bfb32685a57
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a82801b0084f2d1b82a2c25cfc0fa2a9f8f1376c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-6-creating-a-custom-send-pipeline"></a>第 6 课： 创建自定义发送管道
在本课程中，你可以创建自定义发送管道使用 BizTalk 管道设计器。 发送管道是你在之前的消息运行的管道[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息发送到其目标。  
  
 配置自定义管道将该 SWIFT 汇编程序 (ASM) 组件。 ASM 采用 XML 格式的消息和将转换或序列化到 SWIFT 平面文件的内容。 此转换基于中创建的 MT103 架构[第 3 课： 添加自定义接收管道](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)。  
  
### <a name="to-create-a-custom-send-pipeline"></a>若要创建自定义，将发送管道  
  
1.  在解决方案资源管理器，右键单击**SWIFTPipelines**项目，指向**添加**，然后单击**新项**。  
  
2.  在添加新项-SWIFTPipelines 对话框中，确认**管道文件**是否选择在类别窗格中，然后选择**发送管道**从模板窗格。  
  
3.  在**名称**框中，键入**MT103SendPipeline.btp**。  
  
4.  单击**添加**以 BizTalk 管道设计器中打开空白的管道。  
  
    > [!NOTE]
    >  在 BizTalk 管道设计器中显示空的管道。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]将新管道 SWIFTPipelines 项目下添加到解决方案资源管理器中。  
  
 继续执行[第 7 课： 添加自定义 SWIFT 汇编程序发送管道](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)。