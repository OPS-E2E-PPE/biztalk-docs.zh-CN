---
title: 第 2 课： 提交无效的 MT103 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, invalid messages
- submitting, invalid messages
- submitting, MT103 messages
- MT103 messages
- messages, MT103 messages
ms.assetid: 4b070ae1-c400-421a-b2f6-b7b1f22c0e41
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cb8f0539f3a832e3b54a6fa45b300558a8e39a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014878"
---
# <a name="lesson-2-submitting-an-mt103-message-that-is-not-valid"></a>第 2 课： 提交无效的 MT103 消息
在本课中，提交是无效的 MT103 消息并您解决在使用系统工具所生成的错误。  
  
### <a name="to-submit-an-mt103-message-that-is-not-valid"></a>若要提交无效的 MT103 消息  
  
1. 将文件 MT103_Invalid_Sample.txt 复制从\<*驱动器：*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial 到\<*驱动器*\>: \Labs\Inbound\FlatFile 文件夹。 请注意该文件放到文件夹的时间。  
  
2. 打开\<*驱动器：*\>\Labs\Outbound 验证对应于 MT103_Invalid_Sample.txt 任何 XML 文件是否在文件夹中。 （对应于有效的 MT103_Sample.txt 消息的 XML 文件仍应在该文件夹中。）  
  
3. 在记事本中，打开文件 MT103_Invalid_Sample.txt 中\<*驱动器：*\>\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial。  
  
4. 启动**BizTalk Server 管理**。  
  
5. 在 BizTalk Server 管理控制台中，展开**事件查看器 （本地）**，然后单击**应用程序**。  
  
6. 查找具有的源 BizTalk Accelerator for SWIFT 和放置到无效的消息时，对应于时间的错误条目\<*驱动器*\>: \Labs\Inbound\FlatFile 文件夹。 双击该错误条目。  
  
7. 在错误事件属性对话框中，验证说明窗格中，失败的消息已发布到 MessageBox SWIFT 反汇编程序标记为**A4SWIFT_Failed**作为**True**。 关闭事件属性对话框。  
  
8. 在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，然后展开**BizTalk 组**。 在中**视图**菜单上，单击**组中心页**。  
  
9. 在中**组概述**窗格中，在**分组的挂起服务实例**窗格中，单击**应用程序分组存放**。  
  
10. 在中**为所选的查询结果的预览**窗格中，双击条目**MT103_FlatFile_ReceivePort**。  
  
11. 在服务详细信息对话框中，单击**消息**选项卡。双击服务名称是为其条目**MT103_FlatFile_ReceivePort**。  
  
12. 在消息详细信息对话框中，单击**正文**的左窗格中。  
  
13. 验证消息详细信息对话框中的正文窗格中显示该消息对应于 MT103_Invalid_Sample.txt 在记事本中打开。  
  
    请继续执行[第 3 课： 测试 XML 实例](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)。