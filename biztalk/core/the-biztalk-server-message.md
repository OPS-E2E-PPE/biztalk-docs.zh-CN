---
title: BizTalk Server 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, properties
- messages, about messages
ms.assetid: 6048c191-b495-4fdc-b547-e3e322340a49
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 012bb1f9602b6afa02ab609d8ff2e1b967117bce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298883"
---
# <a name="the-biztalk-server-message"></a>BizTalk Server 消息
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是，在其核心，消息处理引擎。 若要详细了解[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，务必要了解消息以及如何表示、 存储和处理由 BizTalk Server。 消息时，BizTalk Server 的工作原理的详细信息会变得更易理解后获得了了解有哪些消息。  
  
 在 BizTalk Server 中的每个消息被视为多部分消息，由零个或多个部分组成。 一个或多个部分每个消息都有一个标识为正文部分这些部件。 每个部分包含的数据可以表示 XML 文档、 平面文件、 序列化的.NET 类或其他二进制数据流的二进制块。 消息的正文部分用于标识可用于路由消息的类型。  
  
 若要了解一个非常重要概念是所有消息都是在不可变[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这意味着，构造一条消息后，它不能更改。 构造后将被放入 MessageBox 数据库，则认为该消息。 对消息的任何更改都需要创建并从该点开始使用新的消息。 这是在业务流程设计器，其中编译规则强制您遵循严格的指导原则，有关构造一条消息，然后再使用它，并且不允许更改构造块之外的消息中表现的尤为清楚。 如果需要更改该消息，必须创建创建相同类型的消息的构造块、 将原始消息复制到新的消息，并关闭该构造块之前对新消息然后进行任何更改。  
  
## <a name="message-properties"></a>消息属性  
 除了组成消息的部分，在系统中的每个消息具有一组与它一起进入所谓的属性*消息上下文*。 这些属性可以从提取或与消息本身相关的值。 例如，适配器将属性放入与接收的消息，例如从该处接收消息，该位置相关的上下文和用于接收消息的适配器的类型。 属性既可以写入到上下文，或*提升*到上下文。 这两个选项之间的区别是升级的属性可以用作消息路由，而不能写入的属性中的条件。  
  
 写入或升级到上下文的值的这一概念相关，但不是完全相同，升级属性在 BizTalk 编辑器中。 在 BizTalk 编辑器中的元素或属性在架构中的可以被标记为已提升的属性或可分辨的字段。 标记有 PropertyField 批注消息架构中的项将导致管道拆装器将升级的属性放入上下文。 标记有 DistinguishedField 批注消息架构中的项将导致管道拆装器将写入的属性放入上下文。  
  
 升级的属性的设计入门的设计*消息相关*: 相关联将要接收到已在运行的业务流程实例的消息的功能。 对于相关性，没有需要定义一个属性或一组属性，用于提供业务流程中消息间的链接。 例如，在购买过程中，您需要根据 PurchaseOrderID 消息关联。 但是，在许多业务案例，可能不匹配的消息中的属性的特定字段的名称。 采购订单架构可能具有名为 POId，而辅助发票架构可能有一个名为 OrderID 的元素的元素。 若要关联消息命名属性 PurchaseOrderID 如在此情况下，开发人员必须能够提取要进行从值的源关联的属性的名称。 属性架构支持这种抽象。  
  
 一个*属性架构*使您能够在共同位置定义升级的属性并将它们引用的其他架构。 与其他架构一样，属性架构具有一个命名空间，但与不同的其他架构，它可以仅定义的元素 （即，不记录或属性）。 属性架构中定义每个元素具有名称和类型。 由于属性架构可能需要引用的多个架构，并且必须在运行时组件可用的属性架构中的信息，必须获取该属性架构部署到 BizTalk Server 与所有其他架构一样。 除了正常架构部署步骤，已升级的属性有关的信息提取，并存储在中管理数据库的 bts_documentSpec 表中。  
  
 创建属性架构后，元素和属性具有相同类型 （例如。 整数） 可以升级为属性架构中的命名属性之一。  
  
 **若要完成从上面的示例用例，开发人员会执行以下步骤来定义相关的所需的共享的属性。**  
  
1. 创建属性架构并定义名为 PurchaseOrderId 类型 xs: int 的元素。  
  
2. 创建 PurchaseOrder 架构并添加元素或属性的类型 xs: int 名为 POId。  
  
3. 在 BizTalk 编辑器中使用显示升级命令，开发人员将 POId 字段添加到已升级属性的列表并指示它应将其升级为通过选择 PurchaseOrderId 属性架构中定义的 PurchaseOrderId 属性从列表中的命名的属性。  
  
4. 创建发票架构并添加元素或类型 xs: int 名为 OrderId 的属性。  
  
5. 在 BizTalk 编辑器中使用显示升级命令，开发人员将 OrderId 字段添加到已升级属性的列表和指示它应将其升级为通过选择 PurchaseOrderId 属性架构中定义的 PurchaseOrderId 属性从列表中的命名的属性。  
  
   现在，此定义已存在文档架构中，管道组件可以正确地将提升 OrderId 和 POId 为命名属性 PurchaseOrderID，以便它可以用于路由和关联。 有关此升级过程的更多详细信息，请参阅本文档中的"消息处理"主题。  
  
   升级属性的优点之一是元素的提升的值是元素的在消息的上下文中可用。 这意味着检索该值成本较低，因为它不需要将消息加载到内存，无法对消息执行 XPath 语句。 相反，简单属性包可以使用与键结合，若要获取的值。 这种行为最好在非消息路由的情况下，创建可分辨的字段的原因。 升级的属性升级到消息上下文，而可分辨的字段将写入到消息上下文。 与升级属性不同，但是可分辨字段没有属性的架构。 这就是原因可分辨的字段不能用于路由，因此不提供作为筛选条件中的发送端口或业务流程接收形状。 可分辨字段可，但是，在业务流程中使用来读取或写入值从消息上下文，而无需将消息加载到内存和提取的值。  
  
   除了属性升级或写入到消息上下文，消息谓词还可以添加到上下文。 消息谓词用作 BizTalk Server 中一种安全措施，并提供有关必须与该消息将路由到任何主机指定的值匹配的消息的上下文信息。 此安全措施，可允许特定的主机是可以接收和处理特定消息的唯一主机的方式配置 BizTalk Server 环境。 例如，在 BizTalk Server 管理控制台中，主机可以配置要使用消息解码和解密的证书的指纹。 配置此属性为该主机在 MessageBox 中创建应用程序属性。 保护消息的接收和解密使用此指纹被仅路由到的主机配置的指纹。  
  
## <a name="see-also"></a>请参阅  
 [运行时体系结构](../core/runtime-architecture.md)