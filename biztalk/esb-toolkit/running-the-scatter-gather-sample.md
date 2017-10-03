---
title: "运行散播-聚集示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53676974-ea1f-4c95-9dbb-98fff92286fa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dcafa519aac074ccb339373a591b590846c9341
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-scatter-gather-sample"></a>运行散播-聚集示例
散播-聚集示例使用 Windows 窗体测试客户端应用程序的路线入口示例来演示此模式将路线服务的功能的应用。  
  
 **若要运行散播-聚集示例**  
  
1.  如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。  
  
2.  在 Windows 资源管理器，打开文件夹 \Source\Samples\Itinerary\Source\ESB。你的安装位置的 Itinerary.Test[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后启动指定 Esb.Itinerary.Test.exe 的应用程序。  
  
3.  单击**LoadItinerary**按钮，，然后选择名为 ScatterGatherItinerary.xml \Source\Samples\ScatterGather\Itineraries 文件夹中的示例路线。  
  
4.  清除**是请求响应**复选框，这样应用程序将执行单向路线服务操作。  
  
5.  （可选）设置**使用 WCF 服务**复选框，如果你想要使用 OnRamp.Itinerary.Response.WCF 的应用程序接收位置而非默认 OnRamp.Itinerary.Response.SOAP 接收位置。  
  
6.  单击**LoadMessage**按钮，然后从 \Source\Samples\Itinerary\Test\Data 文件夹然后选择 NAOrderDoc.xml 示例消息。  
  
7.  单击**SubmitRequest**按钮以将请求发送到路线提升服务。 打开文件夹 \Source\Samples\DynamicResolution\Test\FileDrop\Out 若要查看响应消息。  
  
 有关如何散点图收集示例使用 ESB 路线服务的信息，请参阅[散播-聚集示例的工作原理](../esb-toolkit/how-the-scatter-gather-sample-works.md)。