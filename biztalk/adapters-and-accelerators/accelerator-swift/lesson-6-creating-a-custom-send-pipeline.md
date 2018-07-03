---
title: 第 6 课： 创建自定义发送管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom pipelines
- send pipelines, custom pipelines
ms.assetid: 73a3a546-1e43-4b93-87d3-9bfb32685a57
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12afba9368554dc85cf57658f674a088db7580d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973717"
---
# <a name="lesson-6-creating-a-custom-send-pipeline"></a>第 6 课： 创建自定义发送管道
在本课中，您可以创建自定义发送管道使用 BizTalk 管道设计器。 发送管道是一个管道，对消息之前运行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息发送到其目标。  
  
 配置自定义管道以使用 SWIFT 汇编程序 (ASM) 组件。 ASM 采用 XML 格式的消息并将转换或将内容序列化到 SWIFT 的平面文件。 此转换基于中创建的 MT103 架构[第 3 课： 添加自定义接收管道](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)。  
  
### <a name="to-create-a-custom-send-pipeline"></a>若要创建自定义发送管道  
  
1. 在解决方案资源管理器中右键单击**SWIFTPipelines**项目，指向**添加**，然后单击**新项**。  
  
2. 在添加新项-SWIFTPipelines 对话框中，验证是否**管道文件**所选的类别窗格中，并选择**发送管道**从模板窗格。  
  
3. 在中**名称**框中，键入**MT103SendPipeline.btp**。  
  
4. 单击**添加**若要在 BizTalk 管道设计器中打开空白的管道。  
  
   > [!NOTE]
   >  BizTalk 管道设计器中显示空管道。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 将新的管道添加到解决方案资源管理器中，SWIFTPipelines 项目下。  
  
   请继续执行[第 7 课： 将 SWIFT 汇编程序添加到自定义发送管道](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)。