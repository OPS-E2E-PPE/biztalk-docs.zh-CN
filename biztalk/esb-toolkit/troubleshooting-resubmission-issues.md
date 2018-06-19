---
title: 重新提交问题疑难解答 |Microsoft 文档
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
ms.openlocfilehash: d1a143924b97117a708caea3006f74db6e029ca4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295093"
---
# <a name="troubleshooting-resubmission-issues"></a>重新提交问题疑难解答
如果必须在重新提交消息的问题，请检查下列项目：  
  
-   你可以通过你浏览器访问接收位置？ 如果你尝试将重新提交至上提升 WCF 或 SOAP 入口，URL 应为窗体 http://localhost/ESB.OnRampServices.WCF/ProcessItinerary.svc 或 http://localhost/ESB.OnRampServices/ProcessItinerary.asmx。 如果你尝试重新提交到 HTTP 接收位置，你可以使用 Internet 浏览器来确定是否接收位置正常通过将示例消息追加到查询字符串，如下面的示例中所示。  
  
    ```  
    http://localhost/HTTPOnRamp/BTSHttpReceive.dll?<SampleMessage>Sample Message Content</SampleMessage>  
    ```  
  
-   请验证是否 BizTalk HTTP 接收适配器已正确配置。