---
title: 配置传入 Mdn 的接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d156beae-e145-48de-9f02-37457073ef97
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b630555d5ec32ca9c1a3d48a8320f138a977284f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391391"
---
# <a name="configuring-a-receive-port-for-incoming-mdns"></a>配置传入 Mdn 的接收端口
若要接收 AS2 MDN，创建一个单向 HTTP 接收端口以接收消息并返回响应返回给参与方。  
  
 双向请求-响应接收端口用于接收的 AS2 消息不应该用于接收 MDN 消息。 使用请求-响应接收端口将 MDN 将阻止 200OK 消息来响应传入 MDN，从而导致不必要的 MDN 传输返回。  
  
 可以使用 AS2Receive 或 AS2EdiReceive 管道处理收到的 MDN。 但是，如果使用 AS2EdiReceive，则不能将 MDN 路由到 MessageBox 中通过设置**到 MessageBox 中处理入站的 MDN 以进行路由/传递**上的属性**确认**页单向协议选项卡。尝试进行此操作将导致一个 EDI 错误，因为 MSN 将传递至 EDI 解码器，将无法对 MDN 进行处理。 如果 MDN 不发送到 MessageBox，则 AS2Decoder 将使用该 MDN，因此它不会传递到 EDI 解码器。  
  
 使用以下配置创建接收端口：  
  
|Location|属性|设置|  
|--------------|--------------|-------------|  
|**接收端口属性：常规**|端口类型|单向|  
|**接收位置属性：常规**|传输类型|HTTP<br /><br /> **请注意**只有 HTTP 适配器可用于传输 Mdn，是 EDIINT/AS2 编码的消息。 此传输不会使用非 HTTP 适配器的适配器。|  
|**接收位置属性：常规**|接收处理程序|BizTalkServerIsolatedHost|  
|**接收位置属性：常规**|接收管道|AS2Receive 或 AS2EdiReceive|  
|**HTTP 传输属性**|虚拟目录和 ISAPI 扩展|/\<虚拟目录名称\>/BTSHTTPReceive.dll|  
  
## <a name="see-also"></a>请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)