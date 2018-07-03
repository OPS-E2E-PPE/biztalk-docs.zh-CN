---
title: 如何为 BTSTask 编辑控制台颜色 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 725dcb7b-5a19-4166-9d1c-93f30ddca201
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f52c727d2606898084d6397e6eb1b96ddc129b6d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974863"
---
# <a name="how-to-edit-the-console-colors-for-btstask"></a>如何为 BTSTask 编辑控制台颜色
本主题介绍如何编辑 BTSTask 输出到控制台的前景色。 如果控制台背景色为白色，则难以查看默认 BTSTask 控制台的输出，您就需要修改控制台的前景色。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须具有读/写权限中包含的 BTSTask.exe.config 文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹。  
  
### <a name="to-edit-the-console-foreground-colors-for-btstask"></a>为 BTSTask 编辑控制台前景色  
  
1. 你想要运行 BTSTask 的计算机，打开中的 BTSTask.exe.config[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]或者文本或 XML 编辑器。 此文件位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹。  
  
2. 根据所需的控制台前景色，分别编辑与错误消息、警告和信息相对应的 Console.ForegroundColor.Error、Console.ForegroundColor.Warning 和 Console.ForegroundColor.Info 项的值，然后保存该文件。 （对于单色，可删除这三个条目，而不必编辑其值。）  
  
    前景色的可用值如下：  
  
    0： 黑色  
  
    1: DarkBlue  
  
    2: DarkGreen  
  
    3: DarkCyan  
  
    4: DarkRed  
  
    5: DarkMagenta  
  
    6: DarkYellow  
  
    7： 灰色  
  
    8: 深灰  
  
    9： 蓝色  
  
    10： 绿色  
  
    11： 蓝绿色  
  
    12： 红色  
  
    13： 洋红色  
  
    14： 黄色  
  
    15： 白色  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)