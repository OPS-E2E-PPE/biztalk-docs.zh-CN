---
title: "如何解决映射警告和错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a3e7f3-c96c-4d3d-9f7c-d2bfd9ace4fd
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a2983a53bb47aa66d1564772d0f8e033132e5a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-map-warnings-and-errors"></a>如何解决映射警告和错误
在编译映射时，可能会在编译过程中显示警告和错误。  
  
## <a name="resolve-warnings-and-errors-when-building-a-map"></a>解决警告和错误时生成映射  
  
1.  对于链接和 functoid 错误，在**错误列表**窗口中，双击任何说明。  
  
     此时将突出显示与该错误相关的链接、functoid 或架构节点。 解决该问题。  
  
2.  查看**说明**中的区域**错误列表**窗口来确定其他错误。  
  
3.  单击**输出**窗口选项卡以查看其他警告和错误消息信息。  
  
4.  解决了所有问题后，右键单击解决方案资源管理器中的映射文件名称，然后单击**测试映射**或**生成解决方案**、，具体情况而定。  
  
    > [!NOTE]
    >  如果显示警告，则可能在多个网格页中都存在该问题。 例如，你有一条记录的网格页 1 (名为**项**) 在源架构树链接到一条记录 (名为**数**) 目标架构树中。 在网格的第 2 页中，你将有一个记录 (名为**产品**) 在源架构树链接到相同**数**目标架构树中的记录。 在此方案中，将生成警告消息，指出你具有对同一记录的多个输入。 但是如果您查看网格的第 1 页，你看到只有一个输入**数**记录。 
  
## <a name="see-also"></a>另请参阅  
 [编译和测试映射](../core/compiling-and-testing-maps.md)   
 [BizTalk 映射程序错误](../core/biztalk-mapper-errors.md)   
 [排除地图故障](../core/troubleshooting-maps.md)