---
title: 保留收到的批处理 EDI 交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10d21b9b-9684-422a-8948-8bd71a4d5a10
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4883f6c6df9042d40b82138a4d3a871797a5fa1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985774"
---
# <a name="preserving-a-received-batched-edi-interchange"></a>保留接收的批处理 EDI 交换
> [!NOTE]
>  本主题中所述的所有用户界面选项都位于**本地主机设置**页 (**接收方设置**部分) 中的双向协议选项卡的**协议属性**对话框。  

 当 EDI 接收管道保留传入批处理 EDI 交换时，将不按常规过程把每个事务集/消息解析为单独的中间 XML 文件。 EDI 接收管道将交换作为一个文档进行处理而不拆分事务集/消息。 发生这种情况时**入站批处理选项**属性设置为**保留交换-出错时挂起交换**或**保留交换-挂起事务集错误**。  

 **架构验证**  

 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 验证使用批架构和服务架构保留批的信封。 批架构用于验证保留消息的根节点；服务架构用于验证交换、组和事务集标头及尾部。 有关批架构的详细信息，请参阅[EDI 批架构](../core/edi-batch-schemas.md)。 服务架构的详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。  

 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 验证在项目中使用文档架构的批处理交换中的文档。  

 **接收方处理**  

 EDI 拆装器按如下方式处理保留批：  

- 当 EDI 拆装器处理一个要保留的批时，它将把平面文件格式转换为 XML 并将 X12InterchangeXML 或 EdifactInterchangeXML 添加为 XML 根节点。 这将指示发送管道应保留该批处理交换，并指示应使用 Edifact_BatchSchema 或 X12_BatchSchema 架构来验证根节点。  

- 拆装器将 DelimiterSetSerializedData 属性添加到批处理 XML 消息的根节点，以指示发送管道在从 XML 消息生成批处理 EDI 交换时使用分隔符。 当 XML 消息是保留批时，该属性将由接收管道使用传入消息中的分隔符来填充。 当批处理的 XML 由批处理业务流程时，会在协议属性中指定的值填充属性。  

- 拆装器的以下命名空间之一创建时，使用 XML 编码保留的交换：`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006/InterchangeXML`或`http://schemas.microsoft.com/BizTalk/EDI/X12/2006/InterchangeXML`。  

- 拆装器会升级上下文属性`EDI.ReuseEnvelope == True`以将交换标识为保留。 这将允许您创建用于订阅所有保留的批处理交换的发送端口。  

  > [!NOTE]
  >  HIPAA 文档将不会拆分为子文档**入站批处理选项**设置为**保留交换**。 即使 HIPAA 架构内的子文档创建中断批注设置为“Yes”，也是如此。  

  **错误处理**  

  如果选择了**保留交换-出错时挂起交换**有关**入站批处理选项**，出现错误，就将挂起整个交换。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]挂起整个保留的交换、 交换结构和顺序将事务的保留该交换内的集。 发生错误时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将事件日志中发布一个合并的错误条目。 此条目将包括交换、功能组和事务集级别中的所有错误。  

  如果选择了**保留交换-出错时挂起事务集**的入站批处理选项，EDI 接收管道将从交换中删除所有无效事务集并继续创建交换 XML。 要重用现有的控制段信封（对于 X12 编码的交换为 ISA、GS、GE，对于 EDIFACT 编码的交换为 UNA、UNB、UNG、UNE 和 UNZ），必须使用创建的该交换 XML。 该交换将被视作已成功处理的文档；但是，错误将在事件查看器中进行报告，如果生成功能确认，则将报告该错误。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将处于错误的每个事务集在事件日志中创建一个单独的条目。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]删除来自交换的交换结构设置和排序的错误的事务可能不会保留。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将更新交换中事务集数目。  

  挂起的出错事务集具有以下特殊情况：  

- 如果组中的所有事务集都是无效的，则将单独挂起每个事务集；但是，该组控制段（没有事务集，因为已被删除）将包括在生成的交换 XML 中。  

- 如果交换中的所有事务集都是无效的，则将单独挂起每个事务集；但是，该交换控制段（没有事务集，因为已被删除）将包括在生成的交换 XML 中。  

- 如果组控制段无效，则将单独挂起该组中的所有事务集。  

- 如果交换控制段无效，则将单独挂起该交换中的所有事务集，且不会生成交换 XML， 但会在事件查看器中为拒绝的交换创建日志。
