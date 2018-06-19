---
title: 第 2 课： 提交无效 MT103 消息 |Microsoft 文档
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
ms.openlocfilehash: d064c06aec2698da1be3824ec709dac1702f8e40
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961291"
---
# <a name="lesson-2-submitting-an-mt103-message-that-is-not-valid"></a>第 2 课： 提交无效 MT103 消息
在本课程中，提交无效 MT103 消息并你解决使用系统工具所生成的错误。  
  
### <a name="to-submit-an-mt103-message-that-is-not-valid"></a>若要提交 MT103 消息无效  
  
1.  将文件 MT103_Invalid_Sample.txt 复制从\<*驱动器：*\>files\microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial 到\<*驱动器*\>: \Labs\Inbound\FlatFile 文件夹。 请注意将文件放置到的文件夹的时间。  
  
2.  打开\<*驱动器：*\>\Labs\Outbound 验证对应于 MT103_Invalid_Sample.txt 没有 XML 文件是否在文件夹中。 （对应于有效的 MT103_Sample.txt 消息的 XML 文件仍应在该文件夹中）。  
  
3.  在记事本中，打开文件 MT103_Invalid_Sample.txt 中\<*驱动器：*\>files\microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial。  
  
4.  启动**BizTalk Server 管理**。  
  
5.  在 BizTalk Server 管理控制台中，展开**事件查看器 （本地）**，然后单击**应用程序**。  
  
6.  查找 SWIFT 和对应于放到无效的消息时的时间的某个源属于 BizTalk 快捷键的错误条目\<*驱动器*\>: \Labs\Inbound\FlatFile 文件夹。 双击该错误项。  
  
7.  在错误事件属性对话框中，验证说明窗格中，在失败的消息已发布到 MessageBox SWIFT 反汇编程序标记**A4SWIFT_Failed**作为**True**。 关闭事件属性对话框。  
  
8.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，然后展开**BizTalk 组**。 在**视图**菜单上，单击**组中心页**。  
  
9. 在**组概述**窗格中，请在**分组挂起的服务实例**窗格中，单击**按应用程序分组**。  
  
10. 在**预览所选的查询结果**窗格中，双击条目**MT103_FlatFile_ReceivePort**。  
  
11. 在服务详细信息对话框中，单击**消息**选项卡。双击为其服务名称的条目**MT103_FlatFile_ReceivePort**。  
  
12. 在消息详细信息对话框中，单击**正文**的左窗格中。  
  
13. 验证在消息详细信息对话框中的正文窗格中显示该消息对应于在记事本中打开的 MT103_Invalid_Sample.txt。  
  
 继续执行[第 3 课： 测试 XML 实例](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md)。