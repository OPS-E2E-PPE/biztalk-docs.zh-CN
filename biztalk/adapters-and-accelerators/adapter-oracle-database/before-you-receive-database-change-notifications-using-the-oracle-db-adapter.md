---
title: 接收数据库更改通知使用的 Oracle 数据库适配器时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 206439b9-0408-4fbb-80e3-cfda2f5a89a5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 965e5334da8e76e6172ab5236cfda948e4d8a93c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376809"
---
# <a name="considerations-for-receiving-database-change-notifications-using-the-oracle-database-adapter"></a>接收数据库更改通知使用的 Oracle 数据库适配器时的注意事项
本主题提供的一些注意事项和最佳实践，您在使用时必须牢记于心[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]从 Oracle 数据库接收数据库通知。  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a>使用适配器来接收通知时的注意事项  
 你必须考虑以下方法同时使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接收查询通知。  
  
- [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]仅传递通知，它接收从 Oracle 数据库时，向适配器客户端。 适配器不会区分不同操作的通知即，一个特定的通知是用于插入操作或更新操作，适配器不具有任何信息。  
  
- 该操作所影响的记录数不会影响操作的通知消息。 例如，而不考虑为 Oracle 数据库表中插入的记录数，适配器客户端收到一个通知消息。  
  
- 我们建议适配器客户端应用程序包含的逻辑来解释的类型从 Oracle 数据库接收的通知。 适配器客户端应用程序可以执行操作来提取中的信息**\<信息\>** 收到的通知消息的元素。 下面是收到了插入操作的通知消息的示例。  
  
  ```  
  <?xml version="1.0" encoding="utf-8" ?>   
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
  
   请注意内的值 **\<信息\>** 元素。 此值提供为其接收通知消息操作的信息。 你的应用程序应具有的功能中的值中提取 **\<信息\>** 元素，然后根据值，执行后续任务。 本主题[处理通知消息，以完成特定任务在 Oracle 数据库中](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)说明了如何在值中提取**\<信息\>** 元素。  
  
- 理想情况下，客户端应用程序收到通知后，它应更新为其已收到通知，以便后续通知不能用于同一条记录的记录。 例如，考虑**ACCOUNTACTIVITY**具有表**处理**列。 对于所有新记录插入到**ACCOUNTACTIVITY**表中的值**处理**列始终是 ' n '。 例如，在插入操作，在中记录**ACCOUNTACTIVITY**表将如下所示：  
  
  |帐户事务 ID|处理|  
  |----------------------------|---------------|  
  |10001|n|  
  
   若要获取新插入记录的通知，适配器客户端将设置**NotificationStatement**绑定属性设置为：  
  
  ```  
  SELECT * FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
  ```  
  
   之后，接收通知，客户端应用程序必须设置的值**处理**为 y 的列，以便通知语句不会进行的记录的有关已通知的操作。 因此，若要实现此目的，客户端应用程序必须执行更新操作上**ACCOUNTACTIVITY**表。 更新操作后，该记录中**ACCOUNTACTIVITY**表将如下所示：  
  
  |帐户事务 ID|处理|  
  |----------------------------|---------------|  
  |10001|y|  
  
   有趣的是，更新操作将再次向适配器客户端发送通知，并且将再次重复整个过程。 因此，客户端应用程序必须具有所需的逻辑，若要放弃此类不需要发送的通知。  
  
- 如果**NotifyOnListenerStart**绑定属性为 true 时，每次启动接收位置时适配器会将通知发送到适配器客户端。 有关如何使用绑定属性和解释该通知消息的详细信息，请参阅[接收 Oracle 数据库更改通知后接收位置中断](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md)。  
  
## <a name="typical-orchestration-for-receiving-notifications"></a>典型的业务流程接收通知  
 本部分概述了用于接收通知使用典型的业务流程流[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
1. 业务流程必须执行的第一件事是通知的检查收到的类型。 要检查的事项包括：  
  
   - 是否收到通知的接收位置重新启动。  
  
   - 是否通知已接收到操作数据库表，例如插入、 更新或删除。  
  
     业务流程必须包括**表达式**形状，并在其中接收一个 xpath 查询，以确定哪种消息。  
  
2. 通知类型可用后，业务流程必须包括判定块，以执行特定操作的通知接收到的类型。 若要实现此目的，该业务流程必须包括**判定**形状。 **判定**形状组成**规则**块和一个**Else**块。 内**规则**块中，必须指定的条件，然后将包含业务流程形状来执行某些操作，如果满足该条件。 内**Else**块中，必须包括业务流程形状来执行某些操作，如果条件为*不*满足。  
  
   中详细介绍之前提出的建议[处理通知消息，以完成特定任务在 Oracle 数据库中使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 的 Oracle 数据库更改通知的接收](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)