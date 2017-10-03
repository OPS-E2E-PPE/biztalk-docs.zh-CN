---
title: "使用 SQL 适配器接收查询通知的注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0142f385-3d55-41a7-a50e-dda94b96d0a4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20bb7019a993e47137ec2e4f71334c5b6b3f663c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-for-receiving-query-notifications-using-the-sql-adapter"></a>使用 SQL 适配器接收查询通知的注意事项
本主题提供一些注意事项和最佳实践，在使用时需要牢记[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 数据库接收查询通知。  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a>使用该适配器可在收到通知时的注意事项  
 你必须考虑以下方法时使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收查询通知：  
  
-   [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收查询通知，然后只需将交给通知适配器客户端。 适配器不区分不同的操作的通知 （即，适配器没有任何信息是用于插入操作或更新操作的一个特定的通知）。  
  
-   该操作所影响的记录数不影响操作的通知消息。 例如，无论包含几个记录插入、 更新或删除的 SQL Server 数据库表中，适配器客户端接收只有一个通知消息。  
  
-   我们建议适配器客户端应用程序包含的逻辑来解释收到来自 SQL Server 的通知的类型。 可以通过提取的信息，确定通知类型**\<信息 >**收到的通知消息元素。 下面是收到有关插入操作的通知消息示例：  
  
    ```  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>  
      <Source>Data</Source>  
      <Type>Change</Type>  
    </Notification>  
    ```  
  
     请注意内的值**\<信息 >**元素。 此值提供有关为其接收到通知消息的操作的信息。 你的应用程序应具有用于提取内的值的功能**\<信息 >**元素，然后根据值，执行后续的任务。 主题[过程通知消息，以完成 SQL 使用 BizTalk Server 中的特定任务](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)说明了如何提取的值在**\<信息 >**元素。 执行类似任务的详细的教程也是在[教程 2： 员工-采购订单过程使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)。  
  
-   理想情况下，客户端应用程序收到特定记录的通知后，该记录应更新，以便不会收到其他通知。 例如，考虑**员工**表具有**状态**列。 为所有新记录插入到**员工**表中的值**状态**列始终是"0"因此表看起来类似于以下：  
  
    |员工姓名|状态|  
    |-------------------|------------|  
    |John|0|  
  
     若要接收新插入的记录的通知，适配器客户端将设置**NotificatonStatement**绑定属性作为：  
  
    ```  
    SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
    ```  
  
    > [!NOTE]
    >  具体而言，你必须指定在此所示的语句中的列名称 SELECT 语句。 此外，你必须始终指定表名称以及架构名称。 例如，dbo。员工。  
  
     在收到通知，客户端应用程序必须重置的值**状态**为"1"的列，以便通知语句不会再次运行的记录。 若要实现此目的，客户端应用程序必须执行更新操作上**员工**表。 更新操作后，该记录中**员工**表将如下所示：  
  
    |员工姓名|状态|  
    |-------------------|------------|  
    |John|1|  
  
     有趣的是，更新操作会再次发送通知到适配器客户端并将再次重复整个过程，因此，客户端应用程序必须具有所需的逻辑，以放弃此类不需要发送的通知。  
  
-   如果**NotifyOnListenerStart**绑定属性为 true 时，每次接收位置启动时，适配器客户端将收到一条通知消息。 有关如何使用绑定属性和解释通知消息的详细信息，请参阅[接收查询通知后接收位置分解 SQL 使用 BizTalk Server 中](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)。  
  
## <a name="typical-orchestration-for-receiving-notifications"></a>典型的业务流程，用于接收通知  
 本部分概述了用于接收通知使用的典型的业务流程流[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
1.  必须执行业务流程的第一件事是确定接收通知的类型包括：  
  
    -   是否接收位置重新启动后收到通知。  
  
    -   是否通知已接收到操作数据库表，如 Insert、 Update 或 Delete。  
  
     业务流程必须包括**表达式**形状，并在其中 xpath 查询来确定收到的消息类型。  
  
2.  在通知后类型确定，业务流程必须包括决策块执行基于收到的通知的类型的特定操作。 若要实现此目的，业务流程必须包括**确定**形状，其中包括**规则**块和**Else**块：  
  
    -   在**规则**块中，你必须指定条件，并且然后包括业务流程形状，以便执行某些操作，如果满足该条件。  
  
    -   在**Else**块中，你必须包括业务流程形状，以便执行某些操作，如果条件为*不*满足。  
  
 中介绍的上述要求的详细信息[过程通知消息，以完成 SQL 使用 BizTalk Server 中的特定任务](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)。 详细的教程还会显示在[教程 2： 员工-采购订单过程使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)。