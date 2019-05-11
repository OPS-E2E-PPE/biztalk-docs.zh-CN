---
title: 接收架构并处理事件与 TIBCO Rendezvous 适配器 |Microsoft Docs
description: 使用 TIBCO Rendezvous 架构在接收端，并使用 BizTalk Adapter for TIBCO Rendezvous BizTalk 中的事件处理
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d459ac2019ccf20edfd718815c7ee789a9089be5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302389"
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a>使用 TIBCO Rendezvous 从 BizTalk Server 接收端口

## <a name="overview"></a>概述
若要使用的接收端口，可以提供一个架构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的传入消息。 接收端口配置为侦听一组特定的使用者名称。 它使用具有可选通配符字符的使用者名称与多个使用者名称相匹配。 定义不同的端口操作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于每个可能的匹配给定的字符串的使用者的业务流程。  
  
> [!NOTE]
>  该适配器支持业务流程和消息处理方案。  
  
## <a name="define-schemas"></a>定义架构  
 例如，如果该端口配置为侦听使用者名称，**股票。市场。索引。 >** ('**>** 是表示右侧任何内容的通配符字符)，它可以有效地定义使用者名称的操作如**股票。市场。索引。纽约证券交易所。与 SP500**，**股票。市场。索引。TSX.TSX60**，依次类推。 适配器生成消息使用的策略中所述[TIBCO Rendezvous 中的接收处理程序的数据类型映射](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)，并生成根元素名称和命名空间，侦听基于使用者名称和接收的消息使用者分别命名。  
  
 在上一示例中，适配器生成与 SP500 事件如下消息：  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 必须定义使用相同的约定的架构。 例如：  
  
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
  
 请注意，使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName**批注。 这是为了指示[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk 集成使用生成的.NET Framework 类型，该名称而不是包含点的名称。 您可以指定任何内容。 在示例中，点替换为下划线。  
  
> [!NOTE]
>  点将导致无效的名称，若要生成的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发工具。  

## <a name="event-processing"></a>事件处理
用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器从队列中调度多个线程上的事件。 BizTalk Server 接收位置与一个 TIBCO Rendezvous 事件队列，以及自己的调度程序线程池相关联。  
  
### <a name="memory-use-and-errors"></a>内存使用和错误  
 处理事件时，适配器会监控所使用的资源情况。 如果内存使用量超出高水位，则适配器会停止调度事件，直至内存使用量达到低水位。 注意，对于未认证的消息，这会导致 TIBCO Rendezvous 消息丢失（TIBCO RV 使用者有 60 秒的时间将消息从队列中删除）。 此数据丢失会被报告为错误。 如果适配器收到 TIBCO Rendezvous 系统建议 NO_MEMORY 消息，则这些消息已经丢失。  
  
 用于 TIBCO Rendezvous 的 BizTalk 适配器会维持一种状态，并根据该状态的变化来执行任务。 如果 BizTalk 消息引擎报告错误，并且已将适配器配置为认证侦听器，则向 TIBCO Rendezvous 报告错误，以便可以重新提交消息。  
  
## <a name="see-also"></a>请参阅  
 [TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md)   
 [数据类型映射中 TIBCO Rendezvous 接收处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)   
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)