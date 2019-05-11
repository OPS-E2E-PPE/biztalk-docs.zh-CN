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
ms.openlocfilehash: 71d902e18c851d3ae2ae432fa1e39d5db4e75206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338069"
---
# <a name="how-to-edit-the-console-colors-for-btstask"></a>如何为 BTSTask 编辑控制台颜色
本主题介绍如何编辑 BTSTask 输出到控制台的前景色。 如果控制台背景色为白色，您将有困难查看默认 BTSTask 控制台的输出，并将需要修改控制台前景色。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须具有读/写权限中包含的 BTSTask.exe.config 文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹。  
  
### <a name="to-edit-the-console-foreground-colors-for-btstask"></a>若要为 BTSTask 编辑控制台前景色  
  
1. 你想要运行 BTSTask 的计算机，打开中的 BTSTask.exe.config[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]或者文本或 XML 编辑器。 此文件位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹。  
  
2. 编辑控制台前景色想分别要用于错误消息、 警告和信息，根据 Console.ForegroundColor.Error、 Console.ForegroundColor.Warning 和 Console.ForegroundColor.Info 项的值，然后保存文件。 （对于单色，删除这三个条目，而不是无需编辑其值。）  
  
    前景色的可用值如下所示：  
  
    0：黑色  
  
    1:DarkBlue  
  
    2:DarkGreen  
  
    3:DarkCyan  
  
    4:DarkRed  
  
    5:DarkMagenta  
  
    6:DarkYellow  
  
    7:灰色  
  
    8:DarkGray  
  
    9:蓝色  
  
    10:绿色  
  
    11:蓝绿色  
  
    12:Red  
  
    13:洋红色  
  
    14:Yellow  
  
    15:白色  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)