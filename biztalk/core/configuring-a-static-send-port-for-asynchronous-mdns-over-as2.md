---
title: 配置静态发送端口通过 AS2 发送异步 Mdn 的 |Microsoft Docs
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
ms.openlocfilehash: 24119db6566207455867b0a2e6b998870d445d74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391410"
---
# <a name="configuring-a-static-send-port-for-asynchronous-mdns-over-as2"></a>配置通过 AS2 发送异步 Mdn 的静态发送端口
本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送异步 EDIINT/AS2 编码的 MDN 消息通过静态发送端口。 此配置包括创建静态发送端口，然后如果需要，设置加密证书用于通过发送端口。  
  
> [!NOTE]
>  可以配置动态发送端口以发送 MDN 消息，而不是静态发送端口。 有关详细信息，请参阅[配置动态发送端口通过 AS2 发送异步 Mdn 的](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)。  
  
 若要发送 MDN 消息，请使用以下配置创建一个单向 HTTP 发送端口：  
  
|Location|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性：常规**|端口类型|静态单向发送端口|  
|**发送端口属性：常规**|传输类型|HTTP**注意：** 只有 HTTP 适配器可用于传输 EDIINT/AS2 编码的消息。 此传输不会使用非 HTTP 适配器的适配器。|  
|**发送端口属性：常规**|发送处理程序|BizTalkServerApplication|  
|**发送端口属性：常规**|发送管道|AS2Send|  
|**HTTP 传输属性**|目标 URL|\<目标 URL 字符串\>|  
|**HTTP 传输属性**|启用 chunked 编码|已清除|  
|**发送端口属性：筛选器**|属性|EdiIntAS.IsAS2AsynchronousMdn**注意：** 你还应指定附加的筛选器表达式，以确保仅有的 MDN 消息要发送到此发送端口中指定的地址会选取此订阅筛选器。|  
|**发送端口属性：筛选器**|运算符|==|  
|**发送端口属性：筛选器**|ReplTest1|True|  
|**发送端口属性：证书**|公用名称和指纹|如果使用的加密证书进行出站 MDN 消息，请输入证书名称和指纹。|  
  
 异步 MDN 应发送到中指定的地址**回执送达选项**所接收 AS2 消息的标头。 动态发送端口将自动完成此操作，而静态发送端口将消息发送到**目标 URL**发送端口属性中。 在发送异步 MDN 使用静态发送端口时，请确保将发送到的 URL 正确。  
  
## <a name="functionality"></a>功能  
 发送端口和管道必须执行以下操作来发送一个 MDN:  
  
-   进行筛选来获取该 MDN`EdiIntAS.IsAS2AsynchronousMdn==True`属性。  
  
-   生成 AS2 消息。 有关此过程的详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
-   将 MDN 路由到发送端口中定义的地址。  
  
## <a name="see-also"></a>请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)