---
title: Oracle 数据库的密钥中的 BizTalk Adapter 功能 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- features, operations-related
- adapters, new and deprecated features
- features, technology-related
- features, new and deprecated
- features, performance-related
- features, metadata-related
ms.assetid: 7e79714c-1472-4721-a693-5be2a9a0cd1f
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4277c5d0691d44bdae26b6b395a91d2ecb8f093
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215981"
---
# <a name="key-features-in-biztalk-adapter-for-oracle-database"></a>用于 Oracle 数据库的 BizTalk Adapter 中的主要功能
本部分列出中的新的和已弃用功能[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。  

  
## <a name="technology-related-features"></a>技术相关功能  
  
|功能|注释|  
|-------------|-------------|  
|连接到 Oracle 数据库的新方法|除了将适配器连接到 Oracle 数据库 （如以前版本的适配器），tnsnames.ora 文件中使用 net 服务名称客户端可以现在还连接到 Oracle 数据库直接指定连接参数，因此不再需要使用 net 服务名称或 tnsnames.ora 文件。 不要求要连接到 Oracle 数据库的 tnsnames.ora 文件将保存你的麻烦的手动更新的连接参数 （net 服务名称） 从在每个客户端计算机上的 tnsnames.ora 文件时添加或更新中的 Oracle 服务器你环境。 有关详细信息，请参阅[创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)。|  
|支持 Windows 身份验证|适配器客户端可以使用 Windows 身份验证连接到 Oracle 数据库。 Windows 身份验证使您能够确定用户的标识基于的 Windows 登录凭据，并因此可帮助你利用内置的安全的 Windows 环境。 有关中的 Windows 身份验证的详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)。|  
  
## <a name="operations-related-features"></a>与操作相关的功能 
  
|功能|注释|  
|-------------|-------------|  
|在插入操作中指定内联值的支持|你可以使用**InlineValue**中要插入到表或视图的 Oracle 数据库中的计算的值执行插入操作的属性。 这是一个可选属性，可用于多个记录的插入操作中的所有简单数据记录。 如果指定此属性的值，它将重写的记录指定的值。 有关 InlineValue 属性的详细信息，请参阅[插入、 更新、 删除和选择 Oracle 表和视图上的操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)。|  
|增强的轮询|[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]现在支持使用存储的过程、 函数或打包的过程或函数以定期轮询 Oracle 数据库接收"轮询基于"数据更改消息。 除了 SELECT 语句中，现在你可以指定存储的过程、 函数或打包的过程或函数适配器执行定期轮询 Oracle 数据库的轮询声明。 有关轮询的详细信息，请参阅[支持基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)。|  
|对 Oracle 用户定义类型 (Udt) 的支持|[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]包含 Oracle Udt 的支持 Oracle 数据库中执行对项目的操作。 有关 UDT 支持的信息，请参阅[支持 Oracle 数据库中的 Oracle User-Defined 类型](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md)。|  
|对复合操作的支持|[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使适配器客户端可以执行对 Oracle 数据库的复合操作。 复合操作可以包含任意数量的以下操作，并按任何顺序：<br /><br /> -对表和视图的操作。<br />存储过程、 函数和过程或函数中加以表示的包内作为适配器中的操作。<br /><br /> 有关复合操作的详细信息，请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)。|  
|在不由用户拥有的架构中执行存储的过程的支持|[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ，你可以在架构中执行存储的过程，即使当前用户不是架构的所有者提供用户在 Oracle 中的架构上具有的权限。 但是，如果存储的过程使用记录类型，它们必须与存储的过程相同的架构中定义。 有关执行存储的过程使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[对函数和存储过程的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)。|  
|对数据库更改通知的支持|适配器客户端可以接收来自基于触发的 SELECT 语句的 Oracle 数据库的数据库更改通知。 向作为适配器客户端和在结果集的 SELECT 语句更改时，将 Oracle 数据库发送通知。 有关数据库更改通知的详细信息，请参阅[接收数据库更改通知时的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)。|  
|同义词的支持|适配器客户端可以执行操作上为表、 视图、 存储的过程、 函数和包创建的同义词。 有关同义词，以及如何使用信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]若要对同义词执行操作，请参阅[对 Oracle 数据库中的同义词操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md)。|  
|对布尔参数和 PL/SQL 表类型的支持|适配器客户端可以在存储的过程和包含布尔参数和 PL/SQL 表类型的函数执行操作。|  
  
### <a name="other-features"></a>其他功能  
  
|功能|注释|  
|-------------|-------------|  
|在 BizTalk Server 中使用该适配器的新方法|[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]可以在 BizTalk 中作为 WCF 自定义端口或 WCF OracleDB 端口使用。 如果你想要使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过 WCF 自定义端口，你不必将 WCF 自定义端口添加到 BizTalk Server 管理控制台，因为 WCF 自定义端口添加到 BizTalk Server 管理控制台上，默认情况下。 但是，如果你想要使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过 WCF OracleDB 端口，你必须首先 WCF OracleDB 将适配器添加到 BizTalk Server 管理控制台。 有关详细信息，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。|  
  
## <a name="deprecated-features-in-the-oracle-adapter"></a>Oracle 适配器中已弃用的功能  
 下表列出了中的当前版本已弃用的功能[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
|功能|注释|  
|-------------|-------------|  
|绑定属性|**PollingRetryCount**， **TransactionIsolationLevel**，和**LongDataTypeColumnSize**绑定属性已弃用。 <br/><br/>**请注意**若要设置的入站操作的事务隔离级别，必须设置适当的值通过配置接收端口时添加的服务行为。 有关如何设置事务的隔离级别的说明，请参阅[配置事务隔离级别和事务超时](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。|  
  
## <a name="changes-to-note"></a>要注意的更改

### <a name="general"></a>常规  
* 类型在出 REF CURSOR 参数

    -   如果没有存储过程内的 REF CURSOR 值没有更改，则输出的值是中输入的 REF CURSOR 的值相同。  
  
    -   中 REF CURSOR 的输入和输出数据是类型的相同。  
  
-   "Nil"属性不正确的行为： 对于所有的简单数据类型，如果设置为"true"，nil 属性的值，并且字段或参数的值不存在然后 Oracle 数据库适配器不正确地将传递指定的值而不是 NULL。 解决方法是，如果你想要传递 NULL 值的字段或参数，则必须确保未指定字段或参数的任何值。 例如，可将一个字段的 NULL 值传递名为"name":  
  
    ```  
    <name xsi:nil="true"/>  
    ```  
-   Real、 Float、 和长时间数据类型和额外零 (0) 中选择操作的结果集的值的末尾将不会被截断。 此外，始终选择操作的结果集返回具有真实精度 8、 Float、 和长时间数据类型的值。  
  
-   处理的数据的记录类型： 为这些节点依赖于的值传递的值**SkipNilNodes**绑定属性。 有关此绑定属性的详细信息，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。 
  
-   出站操作： 没有值发送没有输入的 XML 文件中指定的值的参数。 如果存储过程中指定默认值，Oracle 数据库将使用该值，因为适配器不发送任何值。 如果一个 NULL 值需要发送，用户需要输入的 XML 文件中指定的 NULL 节点，通过设置为"true。"的"nil"属性的值  
  
-   支持命令的超时值。  
  
-   UpdateLOB 操作必须作为事务的一部分执行。 若要确保此操作，请的值**UseAmbientTransaction**绑定属性必须设置为**True**。  
  
### <a name="biztalk-scenario"></a>BizTalk 方案  
  
-   出站操作： 如果**UseAmbientTransaction**绑定属性是"True"上的 Oracle 数据库的操作和在 BizTalk MessageBox 数据库在相同的分布式事务中执行。 有关详细信息中的事务有关[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[与 Oracle 数据库适配器处理事务](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md)。  
  
-   入站操作： 不能使用请求-响应接收端口中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用的入站操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 仅单向接收端口可用。  
  
### <a name="other-scenarios"></a>其他方案  
  
-   出站操作： 适配器并不会启动一个事务。 如果用户想要在同一事务中插入的多个行，则用户负责以执行此操作 System.Transactions 事务范围内。 用户还需要设置的值**UseAmbientTransaction**属性**True**。 有关详细信息中的事务有关[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[与 Oracle 数据库适配器处理事务](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md)。  
  
-   出站操作： 执行同一 IRequestChannel/代理对象的 Sll 操作可能不会执行同一个物理连接到 Oracle 数据库上。  
  
-   WCF 通道模型：[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 WCF 通道模型时，不支持 IReplyChannel。 但是，可用于 IInputChannel 执行入站的操作。 此外，关于事务，该适配器依赖于 WCF 调度程序启动事务执行轮询语句和 post 轮询语句对 Oracle 数据库。 可以通过在 ServiceBehavior 中设置适当的值控制事务的隔离级别和 WCF 调度程序启动事务的超时时间。  
  
## <a name="see-also"></a>另请参阅  
 [了解 Biztalk 适配器用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)