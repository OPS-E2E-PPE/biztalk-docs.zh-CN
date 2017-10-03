---
title: "将转换以及消息路由到磁盘文件夹、 队列或 FTP 文件夹 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5bfdbc38-6663-4d95-a0ed-57fec0245b9f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eb767b588f5531e033ec0c867ee2c6dfad02bc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transforming-and-routing-a-message-to-disk-folder-queue-or-ftp-folder"></a>将转换以及消息路由到磁盘文件夹、 队列或 FTP 文件夹
在此用例，ESB 转换消息提交通过路线 Web 服务或任何在负载增加。 动态解析的文件类型的查找、 FTP 或队列位置确定 （适用于转换） 将映射名称和目标终结点的消息，如图 1 中所示。  
  
 ![转换磁盘文件夹](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3 TransformingDiskFolder")  
  
 **图 1**  
  
 **将转换以及将消息路由到磁盘文件夹**  
  
 包含动态解析示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何使用组件来动态解析终结点的位置、 设置路由的属性，并解决，并执行[!INCLUDE[prague](../includes/prague-md.md)]映射在消息级别，而无需使用业务流程。 它还演示了单向和双向消息模式。  
  
 此用例的扩展是转换的一种简单的路由解决方案，将传入消息路由到文件、 FTP 或队列的位置而无需额外的步骤。  
  
 有关详细信息，请参阅[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)。