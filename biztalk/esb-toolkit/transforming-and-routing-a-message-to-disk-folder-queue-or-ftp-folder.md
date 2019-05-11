---
title: 转换和消息路由到磁盘文件夹、 队列或 FTP 文件夹 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bfdbc38-6663-4d95-a0ed-57fec0245b9f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfed87c48e0e8dfc845163325319f77de1bc2dff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399638"
---
# <a name="transforming-and-routing-a-message-to-disk-folder-queue-or-ftp-folder"></a>转换和消息路由到磁盘文件夹、 队列或 FTP 文件夹
在此用例，ESB 转换提交通过路线 Web 服务或任何接入点的消息。 动态解析查找属于文件类型、 FTP 或队列位置确定的映射名称 （转换） 和目标终结点的消息，如图 1 中所示。  
  
 ![转换磁盘文件夹](../esb-toolkit/media/ch3-transformingdiskfolder.gif "Ch3-TransformingDiskFolder")  
  
 **图 1**  
  
 **转换和一条消息路由到磁盘文件夹**  
  
 动态解析示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何为使用组件动态解析终结点位置、 设置路由属性和解析和执行级别的消息传送的 BizTalk Server 映射而无需使用业务流程。 它还演示了单向和双向消息传送模式。  
  
 此用例的扩展是转换的一种简单的路由解决方案，将传入消息路由到文件、 FTP 或队列的位置而无需额外的步骤。  
  
 有关详细信息，请参阅[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)。