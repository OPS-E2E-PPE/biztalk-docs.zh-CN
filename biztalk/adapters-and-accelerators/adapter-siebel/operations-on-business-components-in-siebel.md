---
title: "在 Siebel 的业务组件上的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business components, operations on
- operations, on business components
- operations, on business components with picklist fields
ms.assetid: 5430a8bd-88eb-4851-92e3-676ca83780c9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc634d48d4a39e610247edbab98104bc3c6da379
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-business-components-in-siebel"></a>在 Siebel 的业务组件上的操作
Siebel 在业务组件是将一个或多个数据库表中的列到单个结构相关联的逻辑实体。 适配器客户端可以使用该适配器执行对 Siebel 业务组件执行以下操作：  
  
-   **插入**。 适配器客户端可以将一个或多个记录插入在业务组件。  
  
-   **查询**。 适配器客户端可以查询在业务组件中的一个或多个记录。 此操作将作为输入的以下参数：  
  
    -   SearchExpr： 包含搜索表达式。 与此搜索表达式中，指定在业务组件下的所有记录进行都比较和匹配记录返回到适配器客户端。  
  
    -   SortSpec： 如果有多个与搜索表达式匹配的记录，该规范可确定在其中返回记录的顺序。 此参数可选。  
  
    -   QueryFields： 允许适配器客户端来检索值中返回的记录的字段的一个子集。 此参数可选。  
  
        > [!NOTE]
        >  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持在业务组件上的查询操作中的 QueryField 参数中使用原始名称  
  
-   **更新**。 适配器客户端可以更新在业务组件中的一个或多个记录。  
  
-   **删除**。 适配器客户端可以删除在业务组件中的一个或多个记录，通过指定一组的 Id 或通过提供搜索表达式。  
  
    > [!NOTE]
    >  除了其他参数的查询、 更新和删除操作还需要 ViewMode 参数。 此参数采用一个整数，它确定用户的访问权限。 有关这些操作的其他参数和 ViewMode 参数的详细信息，请参阅下的业务组件操作的请求消息[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)。  
  
 有关的信息：  
  
-   执行使用 BizTalk Server 业务组件上的操作，请参阅[在业务组件使用 BizTalk Server 和 Siebel 适配器上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)。  
  
-   执行上使用 WCF 服务模型的业务组件的操作，请参阅[与 Siebel 适配器使用 WCF 服务模型的业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)。  
  
-   执行在业务组件使用 WCF 通道模型上的操作，请参阅[与 Siebel 适配器使用 WCF 服务模型的业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)。  
  
-   执行上使用消息结构和 SOAP 操作的业务组件的操作，请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)。  
  
## <a name="operations-on-business-components-with-mvg-fields"></a>对具有 MVG 字段的业务组件的操作  
 Siebel 在业务组件还可以使用联接或多值的组 (MVG) 其他业务组件中检索字段。 所有业务组件中加以表示的插入、 查询、 更新和删除操作，除了适配器客户端可以通过适配器执行对 Siebel 业务组件执行以下操作：  
  
-   **将关联**。 适配器客户端可以将记录通过指定搜索表达式父和子记录相关联。 这是仅适用于具有 MVG 字段的业务组件。 搜索表达式应筛选恰好一个记录的父和子业务组件。  
  
-   **取消关联**。 通过指定父搜索表达式的记录和子记录，则可以取消关联适配器客户端。 这是仅适用于具有 MVG 字段的业务组件。 搜索表达式必须筛选恰好一个记录的父和子业务组件。  
  
-   **Query_ [MVG_Child_Business_Comp]**。 适配器客户端可以查询通过指定的父记录和 MVG 字段名称与父记录相关联的子记录。 这是仅适用于具有 MVG 字段的业务组件。  
  
    > [!NOTE]
    >  除了其他参数，这些操作还需要 ViewMode 参数。 此参数采用一个整数，它确定用户的访问权限。 有关这些操作的其他参数和 ViewMode 参数的详细信息，请参阅下的业务组件操作的请求消息[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)。  
  
 有关详细信息：  
  
-   执行这些操作使用的业务组件上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[带有 MVG 字段使用 BizTalk Server 和 Siebel 适配器业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)。  
  
-   执行这些操作在业务组件使用 WCF 服务模型，请参阅[带有 MVG 字段与使用 WCF 服务模型的 Siebel 适配器业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)。  
  
-   消息结构和这些操作的 SOAP 操作，请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)。  
  
## <a name="operations-on-business-components-with-picklist-fields"></a>对与选择列表字段的业务组件的操作  
 选择列表在业务组件中的字段类型构成的用户可以从中选择要传递到 Siebel 系统的特定值的值的集合。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持在业务组件与选择列表字段上的操作。 上一段中所述，包含选择列表字段的业务组件上的操作都是作为任何其他业务组件上的操作相同的。 但是，具体取决于选择列表的种类，在业务组件的输入的值可能有所不同。 有关选择列表和它们的类型的详细信息，请参阅 Siebel 文档。  
  
 选择列表类型之一，绑定的静态选择列表，作为枚举的选择列表进行展示的适配器在设计时生成的适配器的元数据中的类型。 这包含一组静态在运行时必须选择列表类型为指定的值。  同时为静态绑定选择列表中指定一个值，必须始终指定一个属于集的值。  
  
 在选择列表字段的业务组件上执行操作的消息结构是类似于任何其他业务组件，对操作的消息结构中所述[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
 有关详细信息：  
  
-   消息结构的包含选择列表字段的业务组件，请参阅[选择列表操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schema-for-picklist-operations.md)。  
  
-   执行在业务组件包含选择列表字段上的操作，请参阅[与选择列表字段使用 BizTalk Server 和 Siebel 适配器的业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)