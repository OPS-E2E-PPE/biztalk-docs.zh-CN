---
title: 如何保护管道 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3a717f-acf8-4f08-a6fb-6d1d48b5b80a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 903e9faec81ce58aac243fb7a22bac6678a81a42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255181"
---
# <a name="how-to-secure-pipelines"></a>如何确保管道安全

## <a name="authentication-trusted"></a>受信任的身份验证
主机可以在管理控制台中为标记**受信任的身份验证**。 将主机表示为“受信任验证”意味着 Microsoft BizTalk Server 将信任该主机所发送消息的上下文中的安全相关属性。 在消息上下文的安全相关的属性是**OriginatorPID**，对应于消息上下文属性 BTS。SourcePartyID，和**OriginatorSID**，对应于消息上下文属性**BTS。WindowsUser**。 有关详细信息，请参阅**消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
 标记为主机**身份验证受信任**允许以指示，受信任的主机是一条消息队列将从添加到自身以外的其他人为消息的发送程序。 换而言之，未标记为的主机**受信任的身份验证**不允许从其他消息发送方将消息添加到队列。  
  
> [!IMPORTANT]
>  MIME/SMIME 解码器管道组件不会检查解密证书的到期日期。 但是，它会检查签名证书的到期日期。  
  
 有关编码和解码通过 SMTP 或 HTTP 发送的消息的信息，请参阅[MIME SMIME 编码器管道组件](../core/mime-smime-encoder-pipeline-component.md)。 另请参阅[MIME SMIME 解码器管道组件](../core/mime-smime-decoder-pipeline-component.md)。  
  
 有关第三方在处理时的签名验证的信息，请参阅[方解析管道组件](../core/party-resolution-pipeline-component.md)。 另请参阅[如何创建协议](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)。  
  
## <a name="see-also"></a>另请参阅  
 [创建管道使用管道设计器](../core/creating-pipelines-using-pipeline-designer.md)   
 [开发自定义管道组件](../core/developing-custom-pipeline-components.md)