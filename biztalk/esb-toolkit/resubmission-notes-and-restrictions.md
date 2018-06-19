---
title: 重新提交说明和限制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 391064a9-1d61-4b10-97ab-d93b37d1ae23
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d03c969dc056e251d8109ce5bc0a29c16f8ffeda
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976603"
---
# <a name="resubmission-notes-and-restrictions"></a>重新提交说明和限制
下面的注意事项和限制适用于重新提交过程：  
  
-   你可以重新提交到 ESB WCF 的负载增加，SOAP (ASMX) 上的负载增加，XML 消息或任何 HTTP 接收位置。  
  
-   用于在提升 WCF 默认 URL 为 http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc。  
  
-   门户网站的 Web.config 文件定义 WCF 入口中的终结点详细信息**\<客户端\>** 节点 **\<System.ServiceModel\>** 部分。 下面是默认值。  
  
    ```  
    <endpoint  
      address="http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc"  
      binding="wsHttpBinding"  
      bindingConfiguration="WSHttpBinding_ITwoWayAsyncVoid"  
      contract="ProcessRequest"   
      name="WSHttpBinding_ITwoWayAsyncVoid">                  
    </endpoint>  
    ```  
  
-   如果上提升 WCF 驻留在远程服务器上，则必须更新以指向正确的服务器的地址。  
  
-   用于在提升 SOAP (ASMX) 默认 URL 为 http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx。  
  
-   门户网站的 Web.config 文件定义的 SOAP (ASMX) 上的负载增加中配置 **\<applicationSettings\>** 部分。 下面是默认值。  
  
    ```  
    <setting   
      name="Microsoft_Practices_ESB_Portal_ProcessItinerary_Process"  
      serializeAs="String">  
      <value>  
        http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx  
      </value>  
    </setting>  
    ```  
  
-   如果上提升 ASMX 驻留在远程服务器上，你需要将 URL 更新具有正确的服务器地址。  
  
-   你可以重新提交平面文件格式的消息，仅对 HTTP 接收位置。 无法将其提交至 WCF 或 SOAP 入口。 你必须确保 HTTP 接收位置具有相应的管道，可以使用和/或分析平面文件。  
  
-   重新提交的消息不包含任何原始消息的上下文属性。  
  
-   重新提交适用于仅消息正文;它不适用于整个消息。  
  
-   重新提交过程支持仅单一部分消息。 重新提交过程不能使用多个部分的消息。  
  
-   你不能重新提交二进制格式的消息。