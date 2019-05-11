---
title: 如何解决映射警告和错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8a3e7f3-c96c-4d3d-9f7c-d2bfd9ace4fd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68ec8b45d3e336c12d6a72f8827c536605ad7ccb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384140"
---
# <a name="how-to-resolve-map-warnings-and-errors"></a>如何解决映射警告和错误
在编译映射时，可能会发现在编译过程导致警告和错误。  
  
## <a name="resolve-warnings-and-errors-when-building-a-map"></a>构建映射时，解决警告和错误  
  
1.  对于链接和 functoid 错误，在**错误列表**窗口中，双击任何说明。  
  
     突出显示的链接、 functoid 或与错误关联的架构节点。 解决此问题。  
  
2.  审阅**描述**区域中的**错误列表**窗口，以确定其他错误。  
  
3.  单击**输出**窗口选项卡以查看其他警告和错误消息信息。  
  
4.  解决所有问题后，右键单击解决方案资源管理器中的映射文件名称，然后单击**测试映射**或**生成解决方案**、，具体情况而定。  
  
    > [!NOTE]
    >  如果出现警告，则问题可能存在多个网格页。 例如，有一条记录的网格页 1 (名为**项**) 的源架构树中链接到一条记录 (名为**数**) 在目标架构树中。 在网格页上 2 有一条记录 (名为**产品**) 的源架构树中链接到相同**数**记录目标架构树中。 在此方案中，会生成警告消息，指出您具有对同一记录的多个输入。 但是如果您查看网格页 1，会看到只有一个输入进入**数**记录。 
  
## <a name="see-also"></a>请参阅  
 [编译和测试映射](../core/compiling-and-testing-maps.md)   
 [BizTalk 映射器错误](../core/biztalk-mapper-errors.md)   
 [排除地图故障](../core/troubleshooting-maps.md)