---
title: 使用 SQL 适配器接收查询通知的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0142f385-3d55-41a7-a50e-dda94b96d0a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21b3cc0056bf8105618aac7a9c47056d3e493c49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004342"
---
# <a name="considerations-for-receiving-query-notifications-using-the-sql-adapter"></a>使用 SQL 适配器接收查询通知的注意事项
本主题提供了一些注意事项和最佳实践，以使用时应牢记[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 数据库接收查询通知。  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a>使用适配器来接收通知时的注意事项  
 你必须考虑以下方法同时使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收查询通知：  
  
- [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]收到 SQL Server 查询通知，然后只需将传递通知给适配器客户端。 适配器不会区分不同的操作的通知 （即，适配器不具有任何信息的特定通知是用于插入操作或更新操作）。  
  
- 该操作所影响的记录数不会影响操作的通知消息。 例如，无论包含几个记录插入、 更新或删除 SQL Server 数据库表中，适配器客户端接收只有一条通知消息。  
  
- 我们建议适配器客户端应用程序包含的逻辑来解释的类型从 SQL Server 收到的通知。 通知类型可通过提取的信息，确定**\<信息\>** 收到的通知消息的元素。 下面是收到了插入操作的通知消息的示例：  
  
  ```  
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
    <Info>Insert</Info>  
    <Source>Data</Source>  
    <Type>Change</Type>  
  </Notification>  
  ```  
  
   请注意内的值**\<信息\>** 元素。 此值提供为其接收通知消息操作的信息。 你的应用程序应具有的功能中的值中提取**\<信息\>** 元素，然后根据值，执行后续任务。 本主题[进程通知消息，以完成特定任务中使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)说明了如何在值中提取**\<信息\>** 元素. 执行类似任务的详细的教程也是可在[教程 2： 员工-采购订单流程使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)。  
  
- 理想情况下，客户端应用程序收到的特定记录的通知后，该记录应更新，以便不会接收其他通知。 例如，考虑**员工**具有表**状态**列。 对于所有新记录插入到**员工**表中的值**状态**列始终是"0"以便查找表将如下所示：  
  
  |员工姓名|“登录属性”|  
  |-------------------|------------|  
  |John|0|  
  
   若要接收通知的新插入的记录，适配器客户端将设置**NotificatonStatement**绑定属性设置为：  
  
  ```  
  SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
  ```  
  
  > [!NOTE]
  >  具体而言，必须指定在此所示的语句中的列名称的 SELECT 语句。 此外，您必须始终指定表名称以及架构名称。 例如，dbo。员工。  
  
   在后接收通知，客户端应用程序必须重置的值**状态**为"1"的列，以便通知语句不会再次运行的记录。 若要实现此目的，客户端应用程序必须执行更新操作上**员工**表。 更新操作后，该记录中**员工**表将如下所示：  
  
  |员工姓名|“登录属性”|  
  |-------------------|------------|  
  |John|@shouldalert|  
  
   有趣的是，更新操作将再次向适配器客户端发送通知并将再次重复整个过程，因此，客户端应用程序必须具有所需的逻辑，若要放弃此类不需要发送的通知。  
  
- 如果**NotifyOnListenerStart**绑定属性为 true 时，每次接收位置时，适配器客户端将收到一条通知消息。 有关如何使用绑定属性和解释该通知消息的详细信息，请参阅[接收查询通知后接收位置中断在 SQL 中使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)。  
  
## <a name="typical-orchestration-for-receiving-notifications"></a>典型的业务流程接收通知  
 本部分概述了用于接收通知使用典型的业务流程流[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
1. 业务流程必须执行的第一件事是确定接收通知的类型包括：  
  
   - 是否接收位置重启后收到通知。  
  
   - 是否通知已接收到操作数据库表，例如插入、 更新或删除。  
  
     业务流程必须包括**表达式**形状，并在其中，xpath 查询来确定接收的消息类型。  
  
2. 通知之后类型确定，该业务流程必须包括一个决策块来执行特定操作的通知接收到的类型。 若要实现此目的，该业务流程必须包括**判定**形状，其中包括**规则**块和一个**Else**块：  
  
   -   内**规则**块中，必须指定的条件，然后将包含业务流程形状来执行某些操作，如果满足该条件。  
  
   -   内**Else**块中，必须包括业务流程形状来执行某些操作，如果条件为*不*满足。  
  
   上述要求的详细信息所述[进程通知消息，以完成特定任务中使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)。 详细的教程也会出现在[教程 2： 员工-采购订单流程使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)。