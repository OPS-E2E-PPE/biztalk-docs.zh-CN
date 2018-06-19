---
title: 保留已收到批处理的 EDI 交换 |Microsoft 文档
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
ms.openlocfilehash: de14760110eedd002ee01527d57f82c3d6a1aa02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265677"
---
# <a name="preserving-a-received-batched-edi-interchange"></a>保留接收的批处理 EDI 交换
> [!NOTE]
>  本主题中提到的所有用户界面选项都位于**本地主机设置**页 (**接收方设置**部分) 中的双向协议选项卡的**协议属性**对话框。  
  
 当 EDI 接收管道保留传入批处理 EDI 交换时，将不按常规过程把每个事务集/消息解析为单独的中间 XML 文件。 EDI 接收管道将交换作为一个文档进行处理而不拆分事务集/消息。 发生这种情况时**入站批处理选项**属性设置为**保留交换-出错时暂停交换**或**保留交换-时暂停事务集错误**。  
  
 **架构验证**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]验证的信封中使用批处理架构和服务架构保留批处理。 批架构用于验证保留消息的根节点；服务架构用于验证交换、组和事务集标头及尾部。 有关批处理架构的详细信息，请参阅[批处理的 EDI 架构](../core/edi-batch-schemas.md)。 有关服务架构的详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]验证批处理的交换，在你的项目中使用的文档架构中的文档。  
  
 **接收方处理**  
  
 EDI 拆装器按如下方式处理保留批：  
  
-   当 EDI 拆装器处理一个要保留的批时，它将把平面文件格式转换为 XML 并将 X12InterchangeXML 或 EdifactInterchangeXML 添加为 XML 根节点。 这将指示发送管道应保留该批处理交换，并指示应使用 Edifact_BatchSchema 或 X12_BatchSchema 架构来验证根节点。  
  
-   拆装器将 DelimiterSetSerializedData 属性添加到批处理 XML 消息的根节点，以指示发送管道在从 XML 消息生成批处理 EDI 交换时使用分隔符。 当 XML 消息是保留批时，该属性将由接收管道使用传入消息中的分隔符来填充。 如果批处理的 XML 批处理的业务流程由生成的该属性从协议属性中指定的值填充。  
  
-   当它创建 XML 编码保留交换反汇编程序都将使用以下命名空间之一：`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006/InterchangeXML`或`http://schemas.microsoft.com/BizTalk/EDI/X12/2006/InterchangeXML`。  
  
-   反汇编程序提升上下文属性`EDI.ReuseEnvelope == True`来标识该交换，因为保留。 这将允许您创建用于订阅所有保留的批处理交换的发送端口。  
  
    > [!NOTE]
    >  HIPAA 文档将不拆分为子文档如果**入站批处理选项**设置为**保留交换**。 即使 HIPAA 架构内的子文档创建中断批注设置为“Yes”，也是如此。  
  
 **错误处理**  
  
 如果选择了**保留交换-出错时暂停交换**为**入站批处理选项**，将挂起整个交换，由于任何错误。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]挂起整个保留的交换、 交换结构和排序的事务中交换集将被保留。 发生错误时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会将事件日志中发布一个合并的错误条目。 此条目将包括交换、功能组和事务集级别中的所有错误。  
  
 如果选择了**保留交换-出错时暂停事务集**对于入站批处理选项，EDI 接收管道将从该交换中删除任何无效的事务集并继续进行创建XML 的交换。 要重用现有的控制段信封（对于 X12 编码的交换为 ISA、GS、GE，对于 EDIFACT 编码的交换为 UNA、UNB、UNG、UNE 和 UNZ），必须使用创建的该交换 XML。 该交换将被视作已成功处理的文档；但是，错误将在事件查看器中进行报告，如果生成功能确认，则将报告该错误。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将每个事务集有错误的事件日志中创建一个单独的条目。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]谷交换的交换结构从设置和排序错误事务可能不会保留。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将更新的交换中的事务集的数量。  
  
 挂起的出错事务集具有以下特殊情况：  
  
-   如果组中的所有事务集都是无效的，则将单独挂起每个事务集；但是，该组控制段（没有事务集，因为已被删除）将包括在生成的交换 XML 中。  
  
-   如果交换中的所有事务集都是无效的，则将单独挂起每个事务集；但是，该交换控制段（没有事务集，因为已被删除）将包括在生成的交换 XML 中。  
  
-   如果组控制段无效，则将单独挂起该组中的所有事务集。  
  
-   如果交换控制段无效，则将单独挂起该交换中的所有事务集，且不会生成交换 XML， 但会在事件查看器中为拒绝的交换创建日志。