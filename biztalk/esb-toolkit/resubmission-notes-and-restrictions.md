---
title: 重新提交说明和限制 |Microsoft Docs
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
ms.openlocfilehash: f08f6a2740331518d6fc92fb0c12e6f89d1b79f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401506"
---
# <a name="resubmission-notes-and-restrictions"></a>重新提交说明和限制
下面的注意事项和限制适用于重新提交过程：  
  
-   您可以重新提交到了 ESB WCF 的途径，SOAP (ASMX) 的途径，XML 消息或任何 HTTP 接收位置。  
  
-   默认 url 为 WCF 帮手 http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc。  
  
-   门户网站的 Web.config 文件定义了 WCF 的途径，在终结点详细信息**\<客户端\>** 节点的**\<System.ServiceModel\>** 部分。 以下是默认值。  
  
    ```  
    <endpoint  
      address="http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc"  
      binding="wsHttpBinding"  
      bindingConfiguration="WSHttpBinding_ITwoWayAsyncVoid"  
      contract="ProcessRequest"   
      name="WSHttpBinding_ITwoWayAsyncVoid">                  
    </endpoint>  
    ```  
  
-   如果 WCF 帮手驻留在远程服务器上，则必须更新为指向正确的服务器的地址。  
  
-   SOAP (ASMX) 接入点的默认 URL 是 http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx。  
  
-   门户网站的 Web.config 文件定义了 SOAP (ASMX) 的途径中的配置**\<applicationSettings\>** 部分。 以下是默认值。  
  
    ```  
    <setting   
      name="Microsoft_Practices_ESB_Portal_ProcessItinerary_Process"  
      serializeAs="String">  
      <value>  
        http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx  
      </value>  
    </setting>  
    ```  
  
-   如果 ASMX 帮手驻留在远程服务器上，您需要使用正确的服务器地址更新 URL。  
  
-   您可以重新提交平面文件格式的消息，仅对 HTTP 接收位置。 不能将其提交到 WCF 或 SOAP 接入点。 必须确保 HTTP 接收位置具有相应的管道，可以使用和/或分析平面文件。  
  
-   重新提交的消息不包含任何原始消息的上下文属性。  
  
-   重新提交适用于只会将消息正文;它不适用于整个消息。  
  
-   重新提交过程支持仅单部分消息。 不能使用多部分消息重新提交过程。  
  
-   无法重新提交二进制文件格式的邮件。