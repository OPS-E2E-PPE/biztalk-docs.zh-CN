---
title: "BizTalk Server 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, properties
- messages, about messages
ms.assetid: 6048c191-b495-4fdc-b547-e3e322340a49
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4fd150a0b93cac10c4d1f79a526846629c62e67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-biztalk-server-message"></a>BizTalk Server 消息
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 本质上是一个消息处理引擎。 若要了解 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的详细信息，则必须先了解消息以及 BizTalk Server 将如何表示、存储和处理消息。 对消息概念的理解将有助于了解 BizTalk Server 处理消息的方式的具体信息。  
  
 BizTalk Server 中的每条消息都可视为多部分消息，此类消息可以由零个或多个部分组成。 具有一个或多个部分的消息都具有一个标识为正文部分的部分。 每个部分均由可表示 XML 文档、平面文件、序列化的 .NET 类或其他二进制数据流的二进制数据块组成。 您可以使用消息的正文部分来标识可用于路由的消息类型。  
  
 此处，您需要了解一个非常重要的概念，即，所有消息在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中都是不可改变的。 这意味着，消息构造完成后，就不能再对其执行更改操作了。 将消息放入 MessageBox 数据库后，即可认为对消息的构造已完成。 若要对此类消息进行任何更改，则需要创建一条新消息，并从该点开始使用新的消息。 这一点在业务流程设计器中表现的尤为清楚，在该设计器中，编译规则将强制您在使用消息前严格遵守有关构造消息的准则，并且不允许在消息的构造块之外对该消息进行更改。 若要更改消息，则必须创建一个可创建同一类型消息的构造块，将原始消息复制到新消息中，然后在关闭该构造块之前对新消息执行所需的更改。  
  
## <a name="message-properties"></a>消息属性  
 除了构成一条消息的部件，在系统中的每条消息还具有一组属性被称为进入随之*消息上下文*。 这些属性的值是从消息本身提取或与消息本身相关的值。 例如，适配器将属性放入与消息接收操作相关的上下文中，例如接收消息的位置和用于接收消息的适配器类型。 属性或者写入上下文，或*提升*到上下文。 这两个选项之间的区别在于：升级的属性可用作消息路由中的条件，而写入的属性则不能。  
  
 将值写入或升级到上下文中的概念与 BizTalk 编辑器中的升级属性相关，但不完全相同。 在 BizTalk 编辑器中，架构中的元素和属性可以标记为升级属性或可分辨字段。 如果消息架构中包含标记有 PropertyField 批注的项，则将导致管道拆装器将升级的属性放入上下文中。 如果消息架构中包含标记有 DistinguishedField 批注的项，则将导致管道拆装器将写入的属性放入上下文中。  
  
 提升的属性的设计入门的设计*消息相关*： 关联到已在运行的业务流程实例接收一条消息的能力。 对于相关，需要定义一个或一组用于提供业务流程中消息间的链接的属性。 例如，在采购流程中，您需要根据 PurchaseOrderID 来关联消息。 但是，在许多业务案例中，消息中的特定字段或属性的名称可能会不匹配。 采购订单架构中可能存在一个名为 POId 的元素，但辅助发票架构则有一个名为 OrderID 的元素。 在这种情况下，若要关联已命名属性（例如 PurchaseOrderID）上的消息，则开发人员必须能够从值的源中提取出要进行关联的属性名称。 属性架构支持此类提取操作。  
  
 A*属性架构*使您能够在一个公共位置定义提升的属性并将它们引用的其他架构。 与其他架构相似，属性架构也具有命名空间，但不同的是，属性架构只有定义的元素（即，没有记录和属性）。 在属性架构中定义的每个元素都具有名称和类型。 由于可能有多个架构引用属性架构，并且由于在运行时属性架构中的信息必须对组件可用，因此与所有其他架构一样，属性架构也必须部署到 BizTalk Server 中。 除了正常架构部署步骤之外，还必须提取有关升级属性的信息并将其存储在管理数据库的 bts_documentSpec 表中。  
  
 创建属性架构后，元素和属性具有相同类型 （例如。 可以作为属性架构中的命名属性之一升级整数）。  
  
 **若要完成从上面的示例情况，开发人员应执行以下步骤以定义关联所需的共享的属性。**  
  
1.  创建属性架构并定义一个 xs:int 类型的元素，名为 PurchaseOrderId。  
  
2.  创建 PurchaseOrder 架构并添加一个 xs:int 类型的元素，名为 POId。  
  
3.  通过在 BizTalk 编辑器中使用显示升级命令，开发人员可将 POId 字段添加到升级属性列表中，并通过从该列表中选择已命名属性 PurchaseOrderId 来指明应将其升级为属性架构中定义的 PurchaseOrderId 属性。  
  
4.  创建发票架构并添加元素或属性的类型 xs:int 名为 orderid。  
  
5.  通过在 BizTalk 编辑器中使用显示升级命令，开发人员可将 OrderId 字段添加到升级属性列表中，并通过从该列表中选择已命名属性 PurchaseOrderId 来指明应将其升级为属性架构中定义的 PurchaseOrderId 属性。  
  
 既然此定义已存在于文档架构中，管道组件就可以正确地将 OrderId 和 POId 升级为已命名属性 PurchaseOrderID，以便该属性用于路由和相关。 有关此升级过程的详细信息，请参阅本文档中的“消息处理”主题。  
  
 升级属性的优点之一为已升级的元素值可用于消息上下文中。 这意味着检索该值将非常方便，因为您无需将消息加载到内存中就可以对该消息执行 XPath 语句。 实际上，简单属性包可与键结合使用以获取该值。 在非消息路由的情况下需要此类操作，并且，此类操作也是创建可分辨字段的原因。 升级属性是升级到消息上下文中的，而可分辨字段是写入到消息上下文中的。 但是，与升级属性不同，可分辨字段没有属性架构。 这就是可分辨字段无法用于路由的原因，因而在发送端口或业务流程接收形状中该字段也不能用作筛选条件。 但是，在业务流程中可分辨字段可用于在消息上下文中读取或写入值，而无需将消息加载到内存中和对值执行提取操作。  
  
 除了可以将属性升级或写入到消息上下文，还可将消息谓词添加到消息上下文中。 消息谓词在 BizTalk Server 中可用作安全措施，并且提供有关消息的上下文信息，这些消息谓词必须与为消息要路由到的任何主机指定的值相匹配。 通过此安全措施，您可以按以下方式来配置 BizTalk Server 环境：允许特定主机作为可接收和处理特定消息的唯一主机。 例如，在 BizTalk Server 管理控制台中，使用用于进行消息解码和解密的指纹证书配置主机。 配置此属性可在 MessageBox 中为该主机创建应用程序属性。 然后，使用此指纹接收和解密的安全消息只能路由到配置了该指纹的主机中。  
  
## <a name="see-also"></a>另请参阅  
 [运行时体系结构](../core/runtime-architecture.md)