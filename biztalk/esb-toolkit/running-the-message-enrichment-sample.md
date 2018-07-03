---
title: 运行消息充实示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7015a2fe-3727-48f3-a2ed-c368e0630626
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 192d300702b8194096f40e5f54b57717669730ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015126"
---
# <a name="running-the-message-enrichment-sample"></a>运行消息充实示例
消息收集示例使用路线接入点示例随附的 Windows 窗体测试客户端应用程序。  
  
 **若要运行消息充实示例**  
  
1. 如果尚未运行 GlobalBank.ESB 应用程序，使用 Microsoft BizTalk 管理控制台来启动它。  
  
2. 在 Windows 资源管理器中打开文件夹 \Source\Samples\Itinerary\Source\ESB。安装位置的 Itinerary.Test[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，并启动名为 Esb.Itinerary.Test.exe 应用程序。  
  
3. 清除**使用 WCF 服务**复选框，以便可以利用客户端的路线。  
  
4. 单击**负载路线**按钮，并选择其中一个示例路线 \Source\Samples\MessageEnrichment\Itineraries 文件夹中。  
  
5. 单击**LoadMessage**按钮，并从 \Source\Samples\MessageEnrichment\Test\ 文件夹选择 OrderDoc.xml 示例消息。  
  
6. 单击**SubmitRequest**按钮以将请求发送到路线接入点服务。  
  
7. 浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out\\%MessageID%.xml 若要查看输出消息。  
  
   有关消息充实示例工作原理的信息，请参阅[消息充实示例工作原理](../esb-toolkit/how-the-message-enrichment-sample-works.md)。