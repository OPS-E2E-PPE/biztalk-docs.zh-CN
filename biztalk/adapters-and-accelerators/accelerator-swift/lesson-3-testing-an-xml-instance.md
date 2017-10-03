---
title: "第 3 课： 测试 XML 实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, XML instances
- XML instances
ms.assetid: 19d7dd18-17dc-4355-a4f1-5c5e6750faf3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff7fb7efbe41711213103224bdbcda11eeda6281
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-3-testing-an-xml-instance"></a>第 3 课： 测试 XML 实例
在本课程中，你可以提交到该文件的 XML 格式的消息接收端口在前面的课程中创建有效 MT103。 此操作测试你在前一模块中创建的发送管道。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]以平面文件输出写入为前一模块中的发送端口选择的输出文件夹中。  
  
 启动文件通过将 SWIFT XML 格式的文件复制到入站文件夹接收适配器。 此操作会导致系统将有效的 SWIFT 平面文件复制到出站的文件夹。  
  
### <a name="to-test-an-xml-instance"></a>若要测试 XML 实例  
  
1.  在 Windows 资源管理器，打开\<*驱动器*>: \Labs\Outbound。 验证此文件夹包含发送到此文件夹中的 {GUID}.xml 文件[第 1 课： 提交示例平面文件](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md)此模块。  
  
2.  复制 XML 文件中，并将其粘贴到\<*驱动器*>: \Labs\Inbound\XMLFile。 请注意粘贴此文件的时间。  
  
3.  将移动到\<*驱动器*>: \Labs\Outbound。 验证是否存在此文件夹中名为 {GUID}.txt 的文件，以及此文件修改日期列中的时间对应于粘贴到文件的时间\<*驱动器*>: \Labs\Inbound\XMLFile。  
  
4.  在记事本中，打开在 MT103_Sample.txt \<*驱动器*>: files\microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial。  
  
5.  在记事本的另一个实例中，打开中的 {GUID}.txt \<*驱动器*>: \Labs\Inbound\XMLFile。  
  
6.  请验证两个文件在记事本中的包含相同的内容。  
  
 继续执行[模块 8： 修复了无效的消息](http://msdn.microsoft.com/en-us/fb531b22-ac7a-4620-b395-87aebf56077d)。