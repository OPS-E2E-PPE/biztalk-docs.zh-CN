---
title: 配置 AS2 协议属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.as2agreement.properties
ms.assetid: a62d8d2a-0b8d-4179-a48f-92f135b5787d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27f6b95aa723f15f9290ac86fd9dc47f1cc4f9bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356312"
---
# <a name="configuring-as2-agreement-properties"></a>配置 AS2 协议属性
本部分介绍 AS2 传输协议属性。 作为传输协议设置的一部分，您还可以定义是否应对消息进行签名，是否应对消息进行加密，等等。  
  
> [!NOTE]
>  配置 AS2 协议是可选的。 AS2 协议定义的消息是如何使用 AS2 协议传输。 如果贸易合作伙伴决定使用其他任何传输协议来传输消息，他们可以选择不定义 AS2 协议。 但是，贸易合作伙伴必须定义控制如何形成和编码消息的编码协议。 有关编码协议的详细信息，请参阅[配置编码协议属性](../core/configuring-encoding-agreement-properties.md)。  
> 
> [!IMPORTANT]
>  每次在协议中更改 AS2 设置，必须重新启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例，更改才会生效。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)  
  
-   [配置标识符 (AS2)](../core/configuring-identifiers-as2.md)  
  
-   [配置验证 (AS2)](../core/configuring-validation-as2.md)  
  
-   [配置确认 (Mdn) (AS2)](../core/configuring-acknowledgements-mdns-as2.md)  
  
-   [配置本地主机设置 (AS2)](../core/configuring-local-host-settings-as2.md)  
  
-   [配置签名证书 (AS2)](../core/configuring-signature-certificates-as2.md)  
  
-   [配置发送端口关联 (AS2)](../core/configuring-send-port-association-as2.md)  
  
## <a name="see-also"></a>请参阅  
 [配置 AS2 属性](../core/configuring-as2-properties.md)