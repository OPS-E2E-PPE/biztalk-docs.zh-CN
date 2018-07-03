---
title: 第 3 课： 测试 XML 实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, XML instances
- XML instances
ms.assetid: 19d7dd18-17dc-4355-a4f1-5c5e6750faf3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5660ab4e67545b1b98785aedeaeea6e123b6d008
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971894"
---
# <a name="lesson-3-testing-an-xml-instance"></a>第 3 课： 测试 XML 实例
在本课中，你提交无效的 MT103 消息采用 XML 格式的文件接收端口创建在前面的课程。 此操作测试你在上一模块中创建的发送管道。 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]以平面文件输出写入为前一模块中的发送端口选择的输出文件夹。  
  
 启动文件接收适配器的将 SWIFT XML 格式的文件复制到入站的文件夹。 此操作会导致系统将有效的 SWIFT 平面文件复制到出站的文件夹。  
  
### <a name="to-test-an-xml-instance"></a>若要测试 XML 实例  
  
1. 在 Windows 资源管理器中打开\<*驱动器*\>: \Labs\Outbound。 验证此文件夹包含发送到此文件夹中的 {GUID}.xml 文件[第 1 课： 提交示例平面文件](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md)此模块。  
  
2. 复制 XML 文件中，并将其粘贴到\<*驱动器*\>: \Labs\Inbound\XMLFile。 请注意在粘贴此文件的时间。  
  
3. 将移动到\<*驱动器*\>: \Labs\Outbound。 验证是否在此文件夹中，名为 {GUID}.txt 的文件，以及此文件修改日期列中的时间对应于粘贴到文件的时间\<*驱动器*\>: \Labs\Inbound\XMLFile。  
  
4. 在记事本中，打开在 MT103_Sample.txt \<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial。  
  
5. 在记事本的另一个实例中，打开中的 {GUID}.txt \<*驱动器*\>: \Labs\Inbound\XMLFile。  
  
6. 验证在记事本中的两个文件包含相同的内容。  
  
   请继续执行[模块 8： 修复无效消息](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d)。