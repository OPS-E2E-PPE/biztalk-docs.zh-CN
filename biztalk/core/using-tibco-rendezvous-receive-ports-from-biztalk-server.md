---
title: "使用 TIBCO 会合接收端口从 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive ports, using from BizTalk Server
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8e0999362844570bb56cfbc488e5fd5775e286
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a>使用 TIBCO Rendezvous 从 BizTalk Server 接收端口
若要使用接收端口，您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中为传入消息提供一个架构。 随后，将接收端口配置为侦听一组特定的使用者名称。 它使用具有可选通配符字符的使用者名称与多个使用者名称匹配。 您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程中为匹配给定字符串的每个可能使用者配置不同的端口操作。  
  
> [!NOTE]
>  适配器支持业务流程和消息处理方案。  
  
## <a name="defining-schemas"></a>定义架构  
 例如，如果端口被配置为侦听为使用者名称中，**库存。市场。索引。 >** (**>**意味着其他右侧的通配符)，它将有效地定义使用者名称的操作，如**库存。市场。索引。纽约证券交易所。SP500**，**库存。市场。索引。TSX.TSX60**，依次类推。 适配器生成使用的策略中所述的消息[Data Type Mapping for 接收 TIBCO 集合中的处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)，并生成的根元素名称和命名空间上侦听基于使用者名称和收到的消息使用者名称分别。  
  
 在前一示例中，适配器生成与 SP500 事件类似的消息：  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 你必须定义使用相同的约定的架构。 例如：  
  
```  
<xsd:schema  
targetNamespace='   
  
http://schemas.microsoft.com/TibcoRendezvous/Types/STOCK.MARKET.INDICES.N  
YSE.GTWILDCARD'  
xmlns:xsd=' http://www.w3.org/2001/XMLSchema'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types'>  
xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
<xsd:element name='STOCK.MARKET.INDICES.NYSE.SP500'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_NYSE_SP500" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<SP500 message definitions goes here>  
</xsd:complexType>  
<xsd:element name='STOCK.MARKET.INDICES.TSX.TSX60'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_TSX_TSX60" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<TSX60 message definitions goes here>  
</xsd:complexType>  
  
```  
  
 请注意，使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName**批注。 这指示 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk 集成使用生成 .NET Framework 类型的名称，而非包含点的名称。 您可以指定任何内容： 在示例中，点替换为下划线。  
  
> [!NOTE]
>  因为，点将导致 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 开发工具生成无效的名称。  
  
## <a name="see-also"></a>另请参阅  
 [数据类型映射中 TIBCO 会合接收处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)   
 [创建 TIBCO 会合接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)