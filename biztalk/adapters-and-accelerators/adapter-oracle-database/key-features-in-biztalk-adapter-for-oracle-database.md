---
title: 主要用于 Oracle 数据库的 BizTalk 适配器中的功能 |Microsoft Docs
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
ms.openlocfilehash: ccba29495a1d74135ba34ab6228523b50dc59595
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376466"
---
# <a name="key-features-in-biztalk-adapter-for-oracle-database"></a>用于 Oracle 数据库的 BizTalk 适配器的主要功能
本部分列出了中的新的和已弃用功能[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。  

  
## <a name="technology-related-features"></a>与技术相关的功能  
  
|                   功能                    |                                                                                                                                                                                                                                                                                                                                                                                                     注释                                                                                                                                                                                                                                                                                                                                                                                                     |
|----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 连接到 Oracle 数据库的新方法 | 除了适配器连接到 Oracle 数据库 （如中所示的以前版本的适配器），在 tnsnames.ora 文件中使用 net 服务名称的客户端现在可以还连接到 Oracle 数据库直接通过指定连接参数，因此无需使用网络服务名称或 tnsnames.ora 文件。 Tnsnames.ora 文件，若要连接到 Oracle 数据库中无需将保存您需要手动更新连接参数 （net 服务名称） 的麻烦 tnsnames.ora 文件中每个客户端计算机上时添加或更新中的 Oracle 服务器应用环境。 有关详细信息，请参阅[创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)。 |
|      支持 Windows 身份验证      |                                                                                                适配器客户端可以使用 Windows 身份验证连接到 Oracle 数据库。 Windows 身份验证使您能够确定用户的标识基于 Windows 登录凭据，并因此可帮助你利用内置的 Windows 环境的安全性。 有关详细信息中的 Windows 身份验证[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)。                                                                                                |
  
## <a name="operations-related-features"></a>与操作相关的功能 
  
|                                   功能                                    |                                                                                                                                                                                                                                                                                                                                                              注释                                                                                                                                                                                                                                                                                                                                                              |
|------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         在插入操作中指定内联值的支持         |                                                    可以使用**InlineValue**插入操作将计算的值插入到表或视图中的 Oracle 数据库中的属性。 这是一个可选属性，可用于多个记录的插入操作中的所有简单的数据记录。 如果指定此属性的值，它将替代指定的值的一条记录。 有关 InlineValue 属性的详细信息，请参阅[Insert、 Update、 Delete 和选择 Oracle 表和视图操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)。                                                    |
|                               增强的轮询                               | [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]现在支持使用存储的过程、 函数或封装的过程或函数来定期轮询 Oracle 数据库接收"基于轮询的"数据更改消息。 除了 SELECT 语句中，现在您可以指定存储的过程、 函数或打包的过程或函数作为适配器执行定期轮询 Oracle 数据库的轮询语句。 有关轮询的详细信息，请参阅[对基于接收轮询的数据更改消息的支持](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)。 |
|                 对 Oracle 用户定义类型 (Udt) 的支持                 |                                                                                                                                                                [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]包含 Oracle Udt 的支持的 Oracle 数据库中执行对项目的操作。 有关 UDT 的支持信息，请参阅[支持的 Oracle 数据库中的 Oracle User-Defined 类型](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md)。                                                                                                                                                                 |
|                       支持复合操作                       |                                         [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使适配器客户端能够执行对 Oracle 数据库的复合操作。 复合操作可以包含任意数量的以下操作，并按任何顺序：<br /><br /> -对表和视图的操作。<br />存储过程、 函数和过程或函数中显示的包作为在适配器中的操作。<br /><br /> 有关复合操作的详细信息，请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)。                                         |
| 在不由用户拥有的架构中执行存储的过程的支持 |                           [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ，你可以在架构中执行存储的过程，即使当前用户不是架构的所有者提供用户在 Oracle 中的架构具有的权限。 但是，如果存储的过程使用的记录类型，它们必须与存储过程相同的架构中定义。 有关执行存储的过程使用的信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[对函数和存储过程操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)。                            |
|                  对数据库更改通知的支持                   |                                                                                                    适配器客户端可以从基于触发的 SELECT 语句的 Oracle 数据库接收数据库更改通知。 作为适配器客户端和在结果集的 SELECT 语句更改时，将通过 Oracle 数据库发送通知。 有关数据库更改通知的详细信息，请参阅[接收数据库更改通知时的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)。                                                                                                    |
|                             同义词支持                             |                                                                                                                                       适配器客户端可以执行对为表、 视图、 存储的过程、 函数和包创建的同义词的操作。 有关同义词，以及如何使用信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]若要执行对同义词的操作，请参阅[对 Oracle 数据库中的同义词的操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md)。                                                                                                                                        |
|            对布尔参数和 PL/SQL 表类型的支持             |                                                                                                                                                                                                                                                                                                 适配器客户端可以在存储的过程和包含布尔参数和 PL/SQL 表类型的函数中执行操作。                                                                                                                                                                                                                                                                                                  |
  
### <a name="other-features"></a>其他功能  
  
|                    功能                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                           注释                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 在 BizTalk Server 中使用该适配器的新方法 | [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]可以在 BizTalk 中可作为 WCF 自定义端口或 Wcf-oracledb 端口使用。 如果你想要使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过 WCF 自定义端口，您不必将 WCF 自定义端口添加到 BizTalk Server 管理控制台，因为默认情况下将 WCF 自定义端口添加到 BizTalk Server 管理控制台。 但是，如果你想要使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过 Wcf-oracledb 端口，首先必须向 BizTalk Server 管理控制台添加 Wcf-oracledb 适配器。 有关详细信息，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。 |
  
## <a name="deprecated-features-in-the-oracle-adapter"></a>Oracle 适配器中弃用的功能  
 下表列出了当前版本中弃用的功能[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
|功能|注释|  
|-------------|-------------|  
|绑定属性|**PollingRetryCount**， **TransactionIsolationLevel**，并**LongDataTypeColumnSize**绑定属性已弃用。 <br/><br/>**请注意**若要设置的入站操作的事务隔离级别，必须设置适当的值通过配置接收端口时添加的服务行为。 有关如何设置事务隔离级别的说明，请参阅[配置事务隔离级别和事务超时](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。|  
  
## <a name="changes-to-note"></a>需注意的更改

### <a name="general"></a>常规  
* 类型在 OUT REF CURSOR 参数

    -   如果没有在存储过程内的 REF CURSOR 值未更改，输出的值是与输入的 REF CURSOR 中的值相同。  
  
    -   REF CURSOR 中的输入和输出数据是类型的相同。  
  
* "Nil"属性的不正确的行为：对于所有的简单数据类型，如果设置为"true"nil 属性的值和字段或参数的值则存在 Oracle 数据库适配器错误地将传递指定的值而不是 NULL。 解决方法是，如果你想要传递 NULL 值的字段或参数，则必须确保未指定字段或参数的任何值。 例如，若要将一个字段的 NULL 值传递名为"name":  
  
  ```  
  <name xsi:nil="true"/>  
  ```  
* Real、 Float 和长时间数据类型和额外的零 (0) 中选择操作的结果集的值的末尾将不会被截断。 此外，始终在选择操作的结果集返回与实际的精度 8、 Float 和长时间数据类型的值。  
  
* 记录类型的数据的处理方式：为这些节点上的值取决于传递的值**SkipNilNodes**属性绑定。 有关此绑定属性的详细信息，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。 
  
* 出站操作：没有输入的 XML 文件中指定的值的参数会不发送任何值。 如果存储过程中指定默认值，则 Oracle 数据库将使用该值，因为由适配器不发送任何值。 如果需要发送 NULL 值，用户需要通过设置为"true。"nil"属性的值输入的 XML 文件中指定 NULL 节点  
  
* 支持命令的超时值。  
  
* UpdateLOB 操作必须作为事务的一部分执行。 若要确保此值的**UseAmbientTransaction**绑定属性必须设置为**True**。  
  
### <a name="biztalk-scenario"></a>BizTalk 方案  
  
- 出站操作：如果**UseAmbientTransaction**绑定属性为"True"上的 Oracle 数据库的操作，并且在 BizTalk MessageBox 数据库在同一分布式事务中执行。 有关中的事务的详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[与 Oracle 数据库适配器处理事务](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md)。  
  
- 入站的操作：不能使用请求-响应接收端口中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]入站操作使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 只有单向接收端口可以用于。  
  
### <a name="other-scenarios"></a>其他方案  
  
- 出站操作：该适配器并不会启动一个事务。 如果用户想要在同一事务中插入的多个行，则用户的责任，以执行此操作 System.Transactions 事务范围内。 用户还需要设置的值**UseAmbientTransaction**属性设置为**True**。 有关中的事务的详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[与 Oracle 数据库适配器处理事务](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md)。  
  
- 出站操作：不可能在同一物理连接到 Oracle 数据库上执行 Sll 相同 IRequestChannel/代理对象上执行的操作。  
  
- WCF 通道模型：[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 WCF 通道模型时，不支持 IReplyChannel。 但是，可用于 IInputChannel 执行入站的操作。 此外，有关的事务，该适配器依赖 WCF 调度程序启动的事务执行轮询语句和发布针对 Oracle 数据库的轮询语句。 可以通过在 servicebehavior 设置适当的值控制的事务隔离级别和 WCF 调度程序启动的事务的超时时间。  
  
## <a name="see-also"></a>请参阅  
 [了解用于 Oracle 数据库的 Biztalk 适配器](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)