---
title: 运行分散-集中示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53676974-ea1f-4c95-9dbb-98fff92286fa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f824730d284724b3504c969b371877cad5250066
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242692"
---
# <a name="running-the-scatter-gather-sample"></a>运行分散-集中示例
分散-集中示例使用 Windows 窗体测试客户端应用程序的路线接入点示例来演示此模式将路线服务的功能的应用。  
  
 **若要运行分散-集中示例**  
  
1. 如果尚未运行 GlobalBank.ESB 应用程序，使用 Microsoft BizTalk 管理控制台来启动它。  
  
2. 在 Windows 资源管理器中打开文件夹 \Source\Samples\Itinerary\Source\ESB。安装位置的 Itinerary.Test[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，并启动名为 Esb.Itinerary.Test.exe 应用程序。  
  
3. 单击**LoadItinerary**按钮，并选择示例路线名为 ScatterGatherItinerary.xml \Source\Samples\ScatterGather\Itineraries 文件夹中的。  
  
4. 清除**是请求响应**复选框，以便应用程序将执行单向路线服务操作。  
  
5. （可选）设置**使用 WCF 服务**复选框，如果你想要使用 OnRamp.Itinerary.Response.WCF 的应用程序接收位置而不是默认 OnRamp.Itinerary.Response.SOAP 接收位置。  
  
6. 单击**LoadMessage**按钮，并从 \Source\Samples\Itinerary\Test\Data 文件夹选择 NAOrderDoc.xml 示例消息。  
  
7. 单击**SubmitRequest**按钮以将请求发送到路线接入点服务。 打开文件夹 \Source\Samples\DynamicResolution\Test\FileDrop\Out 若要查看的响应消息。  
  
   有关如何收集的散点图示例使用 ESB 路线服务的信息，请参阅[散播-聚集示例的工作原理](../esb-toolkit/how-the-scatter-gather-sample-works.md)。