---
title: "运行消息扩充示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7015a2fe-3727-48f3-a2ed-c368e0630626
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4ed3b3ebc24a908dfefd70711db0d40638c2d3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-message-enrichment-sample"></a>运行消息扩充示例
消息扩充示例使用了路线入口示例随附的 Windows 窗体测试客户端应用。  
  
 **若要运行消息扩展示例**  
  
1.  如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。  
  
2.  在 Windows 资源管理器，打开文件夹 \Source\Samples\Itinerary\Source\ESB。你的安装位置的 Itinerary.Test[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后启动指定 Esb.Itinerary.Test.exe 的应用程序。  
  
3.  清除**使用 WCF 服务**复选框，以便可以利用客户端路线。  
  
4.  单击**负载路线**按钮，，然后选择一个位于 \Source\Samples\MessageEnrichment\Itineraries 文件夹示例路线。  
  
5.  单击**LoadMessage**按钮，然后从 \Source\Samples\MessageEnrichment\Test\ 文件夹然后选择 OrderDoc.xml 示例消息。  
  
6.  单击**SubmitRequest**按钮以将请求发送到路线提升服务。  
  
7.  浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out\\%MessageID%.xml 若要查看输出消息。  
  
 有关消息扩充示例的工作原理的信息，请参阅[消息扩充示例的工作原理](../esb-toolkit/how-the-message-enrichment-sample-works.md)。