---
title: "接收更改通知使用数据库的 Oracle 数据库适配器注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 206439b9-0408-4fbb-80e3-cfda2f5a89a5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01894ab7011324d0f5a3eab84a4cea72e8186c14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-for-receiving-database-change-notifications-using-the-oracle-database-adapter"></a>接收更改通知使用数据库的 Oracle 数据库适配器的注意事项
本主题提供一些注意事项和最佳做法，你必须使用时应牢记[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以接收从 Oracle 数据库的数据库通知。  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a>使用该适配器可在收到通知时的注意事项  
 你必须考虑以下方法时使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接收查询通知。  
  
-   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]只需将传递通知，它从 Oracle 数据库时，接收到适配器客户端上。 适配器不区分不同的操作的通知即、 特定通知是用于插入操作或更新操作，该适配器不具有任何信息。  
  
-   该操作所影响的记录数不影响操作的通知消息。 例如，而不考虑在 Oracle 数据库表中插入的记录数，适配器客户端收到一个通知消息。  
  
-   我们建议适配器客户端应用程序包含的逻辑来解释从 Oracle 数据库接收的通知的类型。 适配器客户端应用程序可以做到这一点提取中的信息**\<信息 >**收到的通知消息元素。 下面是收到有关插入操作的通知消息的示例。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>1</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Insert</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
  
    ```  
  
     请注意内的值**\<信息 >**元素。 此值提供有关为其接收到通知消息的操作的信息。 你的应用程序应具有用于提取内的值的功能**\<信息 >**元素，然后根据值，执行后续的任务。 主题[处理通知消息来完成 Oracle 数据库中的特定任务](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)说明了如何提取的值在**\<信息 >**元素。  
  
-   理想情况下，客户端应用程序接收的通知后，它应更新为其已收到通知，以便后续通知不是针对同一条记录的记录。 例如，考虑**ACCOUNTACTIVITY**表具有**处理**列。 为所有新记录插入到**ACCOUNTACTIVITY**表中的值**处理**列始终是 ' n '。 例如，在插入操作中的记录之后**ACCOUNTACTIVITY**表将如下所示：  
  
    |帐户事务 ID|已处理|  
    |----------------------------|---------------|  
    |10001|n|  
  
     若要获取新插入的记录的通知，适配器客户端将设置**NotificationStatement**绑定属性作为：  
  
    ```  
    SELECT * FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
    ```  
  
     之后，接收通知时，客户端应用程序必须设置的值的**处理**为 y 的列，以便通知语句未以已被告知有关的记录的运行。 因此，若要实现此目的，客户端应用程序必须执行更新操作上**ACCOUNTACTIVITY**表。 更新操作后，该记录中**ACCOUNTACTIVITY**表将如下所示：  
  
    |帐户事务 ID|已处理|  
    |----------------------------|---------------|  
    |10001|y|  
  
     有趣的是，更新操作将再次向适配器客户端发送通知，并且将再次重复整个过程。 因此，客户端应用程序必须具有所需的逻辑，以放弃此类不需要发送的通知。  
  
-   如果**NotifyOnListenerStart**绑定属性为 true 时，每次接收位置启动时该适配器将将通知发送到适配器客户端。 有关如何使用绑定属性和解释通知消息的详细信息，请参阅[接收 Oracle 数据库更改通知后接收位置分解](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md)。  
  
## <a name="typical-orchestration-for-receiving-notifications"></a>典型的业务流程，用于接收通知  
 本部分概述了用于接收通知使用的典型的业务流程流[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
1.  必须执行业务流程的第一个操作是通知的检查收到的类型。 若要检查的事项为：  
  
    -   接收位置重新启动是否收到通知。  
  
    -   是否通知已接收到操作数据库表，如 Insert、 Update 或 Delete。  
  
     业务流程必须包括**表达式**形状，并在其中接收 xpath 查询，以确定哪种类型的消息。  
  
2.  可用的通知类型后，业务流程必须包括决策块执行基于收到的通知的类型的特定操作。 若要实现此目的，业务流程必须包括**确定**形状。 **确定**形状组成**规则**块和**Else**块。 在**规则**块中，你必须指定条件，并且然后包括业务流程形状，以便执行某些操作，如果满足该条件。 在**Else**块中，你必须包括业务流程形状，以便执行某些操作，如果条件为*不*满足。  
  
 中详细描述了上述建议[处理通知消息来完成使用 BizTalk Server 的 Oracle 数据库中的特定任务](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 的接收 Oracle 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)