---
title: 配置静态发送端口异步 Mdn 的通过 AS2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43e767-d9d7-4b02-b3fc-0cfdfd6e61c4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e023dc6f2165e9427fa57e109715dda6cdb258f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968371"
---
# <a name="configuring-a-static-send-port-for-asynchronous-mdns-over-as2"></a>配置用于通过 AS2 发送异步 MDN 的静态发送端口
本主题介绍如何配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以通过静态发送端口发送异步 EDIINT/AS2 编码的 MDN 消息。 此配置包括创建静态发送端口，以及设置发送端口使用的加密证书（如需要）。  
  
> [!NOTE]
>  可以配置动态发送端口而不是静态发送端口来发送 MDN 消息。 有关详细信息，请参阅[通过 AS2 异步 Mdn 的配置动态发送端口](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)。  
  
 若要发送 MDN 消息，请使用下列配置创建一个单向 HTTP 发送端口：  
  
|位置|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性： 常规**|端口类型|静态单向发送端口|  
|**发送端口属性： 常规**|传输类型|HTTP**注意：** 仅 HTTP 适配器可以用于编码 EDIINT/AS2 消息传输。 此传输不能用于除 HTTP 适配器之外的其他适配器。|  
|**发送端口属性： 常规**|发送处理程序|BizTalkServerApplication|  
|**发送端口属性： 常规**|发送管道|AS2Send|  
|**HTTP 传输属性**|目标 URL|\<目标 URL 字符串\>|  
|**HTTP 传输属性**|启用 Chunked 编码|已清除|  
|**发送端口属性： 筛选器**|属性|EdiIntAS.IsAS2AsynchronousMdn**注意：** 还应指定附加的筛选器表达式，以确保仅 MDN 消息要发送到在此指定的地址发送端口将拾取此订阅筛选器。|  
|**发送端口属性： 筛选器**|运算符|==|  
|**发送端口属性： 筛选器**|值|True|  
|**发送端口属性： 证书**|公用名和指纹|如果对出站 MDN 消息使用加密证书，请输入证书名称和指纹。|  
  
 应将异步 MDN 发送到中指定的地址**回执送达选项**已接收的 AS2 消息的标头。 动态发送端口将自动这样做，而静态发送端口将消息发送到**目标 URL**发送端口属性中。 使用静态发送端口发送异步 MDN 时，请确保您发送到的 URL 是正确的。  
  
## <a name="functionality"></a>功能  
 若要发送一个 MDN，发送端口和管道必须执行以下操作：  
  
-   通过对 `EdiIntAS.IsAS2AsynchronousMdn==True` 属性进行筛选，获取该 MDN。  
  
-   生成一条 AS2 消息。 有关此过程的详细信息，请参阅[生成传出的 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
-   将 MDN 路由到在发送端口中定义的地址。  
  
## <a name="see-also"></a>另请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)