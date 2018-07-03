---
title: 在 Siebel 业务组件上的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business components, operations on
- operations, on business components
- operations, on business components with picklist fields
ms.assetid: 5430a8bd-88eb-4851-92e3-676ca83780c9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2156aa058126e4029ee0002a24eca1bcedb19999
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988478"
---
# <a name="operations-on-business-components-in-siebel"></a>在 Siebel 业务组件上的操作
Siebel 业务组件是将一个或多个数据库表中的列的单个结构相关联的逻辑实体。 适配器客户端可以使用适配器来执行对 Siebel 业务组件执行以下操作：  
  
- **插入**。 适配器客户端可以将一个或多个记录插入业务组件。  
  
- **查询**。 适配器客户端可以查询业务组件中的一个或多个记录。 此操作将作为输入以下参数：  
  
  - SearchExpr： 包含的搜索表达式。 与此搜索表达式中，指定的业务组件的所有记录进行都比较和匹配的记录返回到适配器客户端。  
  
  - SortSpec： 如果有多个与搜索表达式匹配的记录，此规范将确定返回记录的顺序。 此参数可选。  
  
  - QueryFields： 允许适配器客户端检索返回的记录中字段的一个子集的值。 此参数可选。  
  
    > [!NOTE]
    >  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持 QueryField 参数在业务组件上的查询操作中使用原始名称  
  
- **更新**。 适配器客户端可以更新在业务组件中的一个或多个记录。  
  
- **删除**。 适配器客户端可以删除在业务组件中的一个或多个记录，通过指定的一组 Id 或通过提供的搜索表达式。  
  
  > [!NOTE]
  >  除了其他参数的查询、 更新和删除操作还考虑 ViewMode 参数。 此参数采用一个整数，确定用户的访问权限。 有关 ViewMode 参数和这些操作的其他参数的详细信息，请参阅下的业务组件操作的请求消息[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)。  
  
  有关信息：  
  
- 在执行业务组件使用 BizTalk Server 上的操作，请参阅[运行业务组件使用 BizTalk Server 和 Siebel 适配器的操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)。  
  
- 在执行使用 WCF 服务模型的业务组件上的操作，请参阅[使用 Siebel 适配器使用 WCF 服务模型的业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)。  
  
- 在执行业务组件使用 WCF 通道模型上的操作，请参阅[使用 Siebel 适配器使用 WCF 服务模型的业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)。  
  
- 在执行使用消息结构和 SOAP 操作的业务组件上的操作，请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)。  
  
## <a name="operations-on-business-components-with-mvg-fields"></a>在包含 MVG 字段与在业务组件上的操作  
 Siebel 业务组件还可以使用联接或多值属性的组 (包含 MVG) 其他业务组件中检索字段。 除了显示的所有业务组件的插入、 查询、 Update 和 Delete 操作，适配器客户端可以通过使用适配器执行 Siebel 业务组件上的以下操作：  
  
- **将关联**。 通过指定搜索表达式的父记录和子记录，则可以将关联适配器客户端。 这是仅适用于包含在包含 MVG 字段的业务组件。 搜索表达式应筛选的父和子业务组件的一个记录。  
  
- **取消关联**。 通过指定搜索表达式的父记录和子记录，则可以取消关联适配器客户端。 这是仅适用于包含在包含 MVG 字段的业务组件。 搜索表达式必须筛选的父和子业务组件的一个记录。  
  
- **Query_ [MVG_Child_Business_Comp]**。 适配器客户端可以查询通过指定的父记录和在包含 MVG 字段名称与父记录关联的子记录。 这是仅适用于包含在包含 MVG 字段的业务组件。  
  
  > [!NOTE]
  >  除了其他参数，这些操作还考虑 ViewMode 参数。 此参数采用一个整数，确定用户的访问权限。 有关 ViewMode 参数和这些操作的其他参数的详细信息，请参阅下的业务组件操作的请求消息[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)。  
  
  有关详细信息：  
  
- 执行这些操作使用的业务组件上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[与在包含 MVG 字段使用 BizTalk Server 和 Siebel 适配器的业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)。  
  
- 在执行这些操作在业务组件使用 WCF 服务模型，请参阅[在包含 MVG 字段使用 Siebel 适配器使用 WCF 服务模型使用的业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)。  
  
- 消息结构和这些操作的 SOAP 操作，请参见[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)。  
  
## <a name="operations-on-business-components-with-picklist-fields"></a>与选择列表字段的业务组件上的操作  
 在业务组件中的选择列表字段类型构成的用户可以从中选择要传递到 Siebel 系统的特定值的值的集合。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持对具有选择列表字段的业务组件操作。 上一段中所述，其中包含选择列表字段的业务组件上的操作是与任何其他业务组件上的操作相同。 但是，具体取决于选择列表的种类，业务组件的输入的值可能有所不同。 有关选择列表及其类型的详细信息，请参阅 Siebel 文档。  
  
 一种选择列表类型，静态绑定选择列表，为枚举选择列表适配器会显示在设计时由适配器生成的元数据中的类型。 这包含一组静态的值必须在运行时指定的选择列表类型。  同时为静态绑定选择列表中指定一个值，必须始终指定一个值，属于集。  
  
 若要执行与选择列表字段的业务组件上的操作的消息结构是类似于任何其他业务组件上的操作的消息结构中所述[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
 有关详细信息：  
  
-   消息的业务组件包含选择列表字段的结构，请参见[选择列表的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schema-for-picklist-operations.md)。  
  
-   在执行包含选择列表字段的业务组件上的操作，请参阅[与选择列表字段使用 BizTalk Server 和 Siebel 适配器的业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)