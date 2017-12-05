---
title: "配置传入 Mdn 的接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d156beae-e145-48de-9f02-37457073ef97
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8585ae946e15d2677e225d42f6c123d5dd5e8e49
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-a-receive-port-for-incoming-mdns"></a>配置传入 MDN 的接收端口
若要接收 AS2 MDN，请创建一个单向 HTTP 接收端口以接收消息并向参与方返回响应。  
  
 不应将用来接收 AS2 消息的双向请求-响应接收端口用于接收 MDN 消息。 为 MDN 使用一个请求-响应接收端口可防止为了响应传入的 MDN 而返回一条 200OK 消息以及由此导致的不必要的 MDN 传输重试。  
  
 既可以使用 AS2Receive 管道也可以使用 AS2EdiReceive 管道处理收到的 MDN。 但是，如果你使用 AS2EdiReceive，你不能将发送 MDN 到 MessageBox 通过设置**路由/传递到 MessageBox 处理入站的 MDN**属性**确认**页单向协议的选项卡。如果尝试进行此操作，将会导致一个 EDI 错误，因为 MSN 将传递至 EDI 解码器，而 EDI 解码器无法对 MDN 进行处理。 如果 MDN 不发送到 MessageBox，则 AS2Decoder 将使用该 MDN，因此不会将其传递到 EDI 解码器。  
  
 使用下列配置创建接收端口：  
  
|位置|属性|设置|  
|--------------|--------------|-------------|  
|**接收端口属性： 常规**|端口类型|单向|  
|**接收位置属性： 常规**|传输类型|HTTP<br /><br /> **请注意**仅 HTTP 适配器可以用于传输 Mdn，编码 EDIINT/AS2 消息。 此传输不能用于除 HTTP 适配器之外的其他适配器。|  
|**接收位置属性： 常规**|接收处理程序|BizTalkServerIsolatedHost|  
|**接收位置属性： 常规**|接收管道|AS2Receive 或 AS2EdiReceive|  
|**HTTP 传输属性**|虚拟目录和 ISAPI 扩展|/\<虚拟目录名称\>/BTSHTTPReceive.dll|  
  
## <a name="see-also"></a>另请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)