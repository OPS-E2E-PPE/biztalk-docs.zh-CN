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
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a><span data-ttu-id="5b528-102">使用 TIBCO Rendezvous 从 BizTalk Server 接收端口</span><span class="sxs-lookup"><span data-stu-id="5b528-102">Using TIBCO Rendezvous Receive Ports from BizTalk Server</span></span>
<span data-ttu-id="5b528-103">若要使用接收端口，您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中为传入消息提供一个架构。</span><span class="sxs-lookup"><span data-stu-id="5b528-103">To use a receive port, you can provide a schema to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for the incoming messages.</span></span> <span data-ttu-id="5b528-104">随后，将接收端口配置为侦听一组特定的使用者名称。</span><span class="sxs-lookup"><span data-stu-id="5b528-104">A receive port is configured to listen for a particular set of subject names.</span></span> <span data-ttu-id="5b528-105">它使用具有可选通配符字符的使用者名称与多个使用者名称匹配。</span><span class="sxs-lookup"><span data-stu-id="5b528-105">It uses a subject name with optional wildcard characters to match multiple subject names.</span></span> <span data-ttu-id="5b528-106">您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程中为匹配给定字符串的每个可能使用者配置不同的端口操作。</span><span class="sxs-lookup"><span data-stu-id="5b528-106">You define different port operations in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for each possible subject that matches the given string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b528-107">适配器支持业务流程和消息处理方案。</span><span class="sxs-lookup"><span data-stu-id="5b528-107">The Adapter supports both orchestration and messaging scenarios.</span></span>  
  
## <a name="defining-schemas"></a><span data-ttu-id="5b528-108">定义架构</span><span class="sxs-lookup"><span data-stu-id="5b528-108">Defining Schemas</span></span>  
 <span data-ttu-id="5b528-109">例如，如果端口被配置为侦听为使用者名称中，**库存。市场。索引。 >** (**>**意味着其他右侧的通配符)，它将有效地定义使用者名称的操作，如**库存。市场。索引。纽约证券交易所。SP500**，**库存。市场。索引。TSX.TSX60**，依次类推。</span><span class="sxs-lookup"><span data-stu-id="5b528-109">For example, if the port is configured to listen to the subject name, **STOCK.MARKET.INDICES.>** ('**>**' is a wildcard character that means anything else to the right), it would be valid to define operations for subject names such as **STOCK.MARKET.INDICES.NYSE.SP500**, **STOCK.MARKET.INDICES.TSX.TSX60**, and so on.</span></span> <span data-ttu-id="5b528-110">适配器生成使用的策略中所述的消息[Data Type Mapping for 接收 TIBCO 集合中的处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)，并生成的根元素名称和命名空间上侦听基于使用者名称和收到的消息使用者名称分别。</span><span class="sxs-lookup"><span data-stu-id="5b528-110">The adapter generates messages using the strategy described in [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md), and generates the root element name and namespaces based on the listen subject name and received message subject names respectively.</span></span>  
  
 <span data-ttu-id="5b528-111">在前一示例中，适配器生成与 SP500 事件类似的消息：</span><span class="sxs-lookup"><span data-stu-id="5b528-111">In the previous example, the adapter generates a message that looks like this for the SP500 event:</span></span>  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 <span data-ttu-id="5b528-112">你必须定义使用相同的约定的架构。</span><span class="sxs-lookup"><span data-stu-id="5b528-112">You must define a schema that uses the same conventions.</span></span> <span data-ttu-id="5b528-113">例如：</span><span class="sxs-lookup"><span data-stu-id="5b528-113">For example:</span></span>  
  
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
  
 <span data-ttu-id="5b528-114">请注意，使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName**批注。</span><span class="sxs-lookup"><span data-stu-id="5b528-114">Note the use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**recordInfo/rootTypeName** annotation.</span></span> <span data-ttu-id="5b528-115">这指示 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk 集成使用生成 .NET Framework 类型的名称，而非包含点的名称。</span><span class="sxs-lookup"><span data-stu-id="5b528-115">This is to instruct the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk integration to use that name for the generated .NET Framework types, instead of the name that contains dots.</span></span> <span data-ttu-id="5b528-116">您可以指定任何内容：</span><span class="sxs-lookup"><span data-stu-id="5b528-116">You can specify anything.</span></span> <span data-ttu-id="5b528-117">在示例中，点替换为下划线。</span><span class="sxs-lookup"><span data-stu-id="5b528-117">In the examples, the dots are replaced with underscores.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b528-118">因为，点将导致 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 开发工具生成无效的名称。</span><span class="sxs-lookup"><span data-stu-id="5b528-118">The dots cause invalid names to be generated by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development tools.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b528-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b528-119">See Also</span></span>  
 <span data-ttu-id="5b528-120">[数据类型映射中 TIBCO 会合接收处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="5b528-120">[Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="5b528-121">创建 TIBCO 会合接收处理程序</span><span class="sxs-lookup"><span data-stu-id="5b528-121">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)