---
title: 重新提交问题疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b60ad45-d793-4de6-b9bc-3e8ef34f2b61
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a095e5c0a2f6b7de9830a43fc632f9ca59aec3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399633"
---
# <a name="troubleshooting-resubmission-issues"></a>重新提交问题疑难解答
如果必须重新提交消息的问题，检查以下项：  
  
-   您可以通过浏览器访问的接收位置？ 如果想要重新提交到 WCF 接入点或 SOAP 帮手，URL 应采用以下形式 http://localhost/ESB.OnRampServices.WCF/ProcessItinerary.svc或 http://localhost/ESB.OnRampServices/ProcessItinerary.asmx。 如果想要重新提交到 HTTP 接收位置，可以使用 Internet 浏览器以确定是否接收位置正常运行的示例消息追加到查询字符串，如下面的示例中所示。  
  
    ```  
    http://localhost/HTTPOnRamp/BTSHttpReceive.dll?<SampleMessage>Sample Message Content</SampleMessage>  
    ```  
  
-   验证 BizTalk HTTP 接收适配器已正确配置。