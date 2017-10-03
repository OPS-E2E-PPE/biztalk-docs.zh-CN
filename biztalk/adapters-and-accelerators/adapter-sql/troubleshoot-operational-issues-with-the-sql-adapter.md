---
title: "使用 BizTalk 中的 SQL 适配器进行的操作问题故障排除 |Microsoft 文档"
description: "常见的问题和解决方法为 SQL 适配器 BizTalk 适配器包 (BAP) 中"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c75f85f4-cd03-4c6a-aac9-a6d02d3c3449
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d3febbda1799c1f002ed352caecc5d9d838db00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-operational-issues-with-the-sql-adapter"></a>使用 SQL 适配器进行故障排除操作问题：
本部分讨论如何使用故障排除方法来解决操作使用时可能遇到的错误[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]。  
  
## <a name="enabling-tracing"></a>启用跟踪  
 必须启用跟踪之间适配器， [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，并且 SQL Server 以收集问题的任何有关的详细信息在遇到时使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 有关跟踪中的支持的详细信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[诊断跟踪和消息日志记录中的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)。  
  
## <a name="known-issues"></a>已知问题  
 以下是使用时可能遇到的最常见错误[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，以及其可能的原因和解决方法。  
  
  
  
###  <a name="BKMK_SQLLoadBinding"></a>在加载适配器绑定错误  
 **问题**  
  
 当你尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，你将收到以下错误：  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **可能的原因**  
  
 当你尝试启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 加载所有已安装适配器的适配器绑定。 反过来，适配器绑定都依赖于企业应用程序的特定客户端软件。 如果你这样做将适配器安装中包含的所有适配器的典型或完全安装，可能会遇到此问题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 但是，可能只有一个企业应用程序安装 LOB 客户端库。 因此，GUI 无法加载其他适配器的绑定。  
  
 **解决方法**  
  
 请确保执行适配器安装需要适配器的自定义安装。  
  
###  <a name="BKMK_SQLDisplay"></a>SQL 适配器不会显示在列表中在 BizTalk Server 管理控制台中的适配器  
 **问题**  
  
 与不同的是较早版本附带的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]未显示在列表中中适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 **可能的原因**  
  
 最新[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是 WCF 自定义绑定。 因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，并因此，不会显示基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 **解决方法**  
  
 你可以显式添加[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。  
  
###  <a name="BKMK_MissingAction"></a>在 SQL Server 数据库上执行操作时出错  
 **问题**  
  
 适配器执行针对 SQL Server 数据库使用的任何操作时将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
-   **有关[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 **可能的原因**  
  
 未指定消息的 WCF 操作。 WCF 需要为每个操作，在 LOB 应用程序上执行的操作会告知适配器指定的 SOAP 操作。  
  
 **解决方法**  
  
 指定的 SOAP 操作中发送端口或 BizTalk 业务流程中的消息上下文属性。 有关说明，请参阅[配置 SQL 适配器的 SOAP 操作](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)。 请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)若要查看的每个操作的操作的列表。  
  
###  <a name="BKMK_SQLInvalidOp"></a>与 ErrorCode InvalidOperationException 执行 FILESTREAM 操作时 = 5  
 **问题**  
  
 使用时遇到以下错误[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行 FILESTREAM 操作。  
  
```  
System.InvalidOperationException: OpenSqlFileStream returned error.  
ErrorCode:5  
  
```  
  
 **可能的原因**  
  
 你可能指定用于连接到 SQL Server 数据库的数据库凭据。 若要执行 FILESTREAM 操作，必须始终使用 Windows 身份验证。 错误代码"5"表示访问被拒绝由于不正确的凭据。 有关不同的错误代码的详细信息，请参阅[系统错误代码 (0-499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx)。
  
 **解决方法**  
  
 使用 Windows 身份验证连接到 SQL Server 数据库。 在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你可以做到这一点将用户名称和密码字段保留为空白 WCF 自定义或 WCF SQL 端口配置对话框中。  
  
###  <a name="BKMK_SQLPolling"></a>轮询操作不返回任何消息即使 PollingStatement 和 PolledDataAvailableStatement 为指定的有效语句  
 **问题**  
  
 即使为 PollingStatement 和 PolledDataAvailableStatement 绑定属性指定有效的值，则适配器不从 SQL Server 收到轮询消息。  
  
 **可能的原因**  
  
 验证任何其他事务是否已在轮询适配器的表上获取锁。  
  
 **解决方法**  
  
 如果你想要轮询正在更新作为另一个事务的一部分的表，可以考虑使用"使用 (nolock)"参数作为 PolledDataAvailableStatement 绑定属性指定的查询的一部分，以确保即使施加锁定返回数据被另一个事务。 有关详细信息，请参阅[中数据库引擎的锁定 SQL](https://msdn.microsoft.com/library/ms190615.aspx)。
  
###  <a name="BKMK_SQLSingleOp"></a>该适配器无法插入、 更新或删除单个操作使用 BizTalk Server 中的数据的大型卷  
 **问题**  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]无法插入、 更新或删除在单个操作中使用的数据大容量[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 **可能的原因**  
  
 插入、 更新或删除的大量数据可能需要时间和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]或的事务中正在执行该操作，可能会超时。  
  
 **解决方法**  
  
-   **有关[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**  
  
    1.  在 machine.config 中指定的 WCF 适配器的超时值。导航到 machine.config 文件在下\<系统驱动器 >: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG 并添加如下所示的摘要。  
  
        ```  
        <configuration>  
         \<system.transactions>  
          <machineSettings maxTimeout="02:00:00" />  
         \</system.transactions>  
        </configuration>  
        ```  
  
         使用此设置时，WCF 适配器超时设置为 2 小时。  
  
    2.  在 machine.config 中指定的超时设置的 MSDTC 事务。导航到 machine.config 文件在下\<系统驱动器 >: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG 并添加如下所示的摘要。  
  
        ```  
        \<system.transactions>   
                <defaultSettings distributedTransactionManagerName="<computer_name>" timeout="02:00:00"/>   
            \</system.transactions>  
  
        ```  
  
         使用此设置时，MSDTC 超时设置为 2 小时。 MSDTC 超时的默认值为 10 分钟。  
  
        > [!IMPORTANT]
        >  你必须运行的适配器客户端和 SQL Server 的计算机上进行此更改。 摘录内容中，运行的适配器客户端和 SQL Server 计算机的名称替换 < 计算机名 >。  
  
    3.  设置**SendTimeout**绑定属性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]为相当大的值。 有关如何设置绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。  
  
###  <a name="BKMK_SQLFullSchemaValidate"></a>BizTalk Server 中的完整架构验证失败的响应消息包含数据集  
 **问题**  
  
 在中的完整架构验证失败的操作，返回的响应消息包含的数据集，例如 ExecuteReader， [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 **解决方法**  
  
 我们建议你不要包含数据集的响应消息的完整架构验证。 相反，您无法执行以下操作：  
  
1.  一旦返回的响应消息的架构，请执行该操作。  
  
2.  将从响应消息的架构复制到.xsd 文件并将此文件添加到你的 BizTalk 项目。  
  
3.  业务流程中使用 xpath 查询从响应消息中提取数据。  
  
###  <a name="BKMK_SQLRootNode"></a>与 RootNode TypeName BizTalk 项目中的错误  
 **问题**  
  
 在 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，如果从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效字符或保留的字**RootNode TypeName**属性，编译项目时将出现以下错误:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解决方法**  
  
1.  右键单击该错误并选择中引用的 rood 节点**属性**。  
  
2.  有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，圆点 （.）。  
  
###  <a name="BKMK_SQLMetadataStronglyTyped"></a>适配器失效，则生成的强类型与临时表的存储过程的元数据  
 **问题**  
  
 适配器无法正常工作，生成的强类型的存储过程，包括其定义中的临时表的元数据。 适配器提供了以下异常。  
  
```  
Microsoft.ServiceModel.Channels.Common.MetadataException:  
Retrieval of Operation Metadata has failed while building WSDL at 'TypedProcedure/<schema>/<stored_procedure_name>' --->  
System.Data.SqlClient.SqlException: Invalid object name '<temp_table_name>'.  
  
```  
  
 **解决方法**  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持生成的元数据的强类型的存储过程包含其定义中的临时表。 相反，应生成相同的过程从下的元数据**过程**时使用的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
###  <a name="BKMK_SQLVS2008"></a>使用 Visual Studio 中的适配器时出现的无效的绑定警告  
 **问题**  
  
 当你使用该适配器创建的应用程序在[!INCLUDE[vs2010](../../includes/vs2010-md.md)]并打开生成的适配器的配置文件 (app.config)，你看到类似于以下警告：  
  
```  
The element 'bindings' has invalid child element 'sqlBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **可能的原因**  
  
 由于会出现此警告[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定， `sqlBinding`，不标准绑定随[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。  
  
 **解决方法**  
  
 可以安全地忽略此警告。  
  
###  <a name="BKMK_SQLNotification"></a>BizTalk Server 引发异常，如果你在同一应用程序使用多个通知架构或跨同一个主机上的多个应用程序使用通知架构  
 **问题**  
  
 BizTalk Server 引发 XLANG 异常或异常指出应用程序找不到文档规范，因为多个架构匹配的消息类型。  
  
 **可能的原因**  
  
 由于以下任一发生这种情况：  
  
-   在你生成多个通知架构在 BizTalk Server 项目中，将其部署到 BizTalk Server 应用程序，，然后运行应用程序从 SQL Server 数据库中接收通知。 由于通知架构是公用的冲突之间没有部署 BizTalk Server 应用程序中的架构。  
  
-   发生多个项目，你已为每个 BizTalk 服务器到单独的 BizTalk Server 应用程序在同一主机上的每个项目部署的项目生成通知架构，然后运行应用程序或应用程序接收来自通知SQL Server 数据库中。 因为架构和程序集都可访问 BizTalk Server 中的应用程序，各种 BizTalk Server 应用程序和程序集下部署的常见架构之间存在不冲突。  
  
 **解决方法**  
  
 BizTalk Server 应用程序使用单个通知架构文件。 如果你需要在同一主机上的多个 BizTalk Server 应用程序中使用通知架构，创建包含单个通知架构的应用程序，然后使用 BizTalk Server 中的所有其他应用程序中的通知架构。  
  
###  <a name="BKMK_SQLRestoreConn"></a>适配器的客户端引发异常，正在执行的操作后连接恢复适配器客户端和 SQL Server 数据库之间  
 **问题**  
  
 适配器的客户端引发以下异常上执行的 SQL Server 数据库上的操作：  
  
```  
{System.Data.Common.DbException} = {"A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.)"}  
```  
  
 **可能的原因**  
  
 在执行期间的操作，该适配器使用连接来自 SQL ADO.NET 连接池来连接到 SQL Server 数据库，并执行该操作。 如果没有适配器客户端和 SQL Server 数据库之间的短暂的网络中断，或者如果 SQL Server 数据库暂时已关闭，SQL ADO.NET 连接池中的所有连接都将失效。 连接恢复并尝试执行 SQL Server 数据库上的操作后，适配器使用的相同的无效连接从 SQL ADO.NET 连接池，并因此适配器客户端引发异常。  
  
 **解决方法**  
  
 适配器客户端应在操作执行其中它们应捕获异常，并指定为"n + 1"的操作重试计数中实施重试逻辑，其中"n"是为 MaxConnectionPoolSize 绑定属性指定的值。 这意味着，如果有"n"中的连接池已变为无效的连接数，从理论上讲适配器客户端应重试"n + 1"的最长时间，以获取有效的连接，并因此执行该操作。  
  
 例如，若要指定重试计数的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，打开**属性**对话框中的应用程序中发送端口，请单击**传输高级选项**的对话框中，和中的左窗格中**传输选项**区域中，指定中的值**重试计数**列表。  
  
###  <a name="BKMK_MemUsage"></a>内存使用情况和线程计数的增加而在事务处理的入站操作中使用该适配器时  
 **问题**  
  
 在事务处理的入站操作中，如轮询，**如果没有数据轮询表中可用**和适配器继续轮询，通过一段时间则会遇到内存使用量和线程计数的增加。  
  
 **可能的原因**  
  
 **如果没有数据轮询表中可用**之后，每个接收超时周期[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]生成新的线程来继续轮询操作。 因此，通过一段时间会增加线程计数和内存使用情况。 但是，如果正在轮询一次的表具有一些数据，同一个线程继续执行所有后续的轮询。  
  
 **解决方法**  
  
 我们建议设置**ReceiveTimeout**为最大可能值，这是 24.20:31:23.6470000 （24 天），以便生成新线程，仅每隔 24 天。 这将确保，内存使用情况和线程计数不会增长过多时间太短。  
  
> [!NOTE]
>  如果已设置 SqlAdapterInboundTransactionBehavior，请确保 TransactionTimeout 也被配置为最大可能值，该值是 24.20:31:23.6470000 （24 天）。 在使用此解决方法，我们可以添加 SqlAdapterInboundTransactionBehavior，仅当事务的隔离级别必须进行配置。 否则，它是一种最佳做法来删除该行为。  
  
 有关详细信息**ReceiveTimeout**绑定属性，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 指定绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。  
  
> [!NOTE]
>  使用的适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，将超时设置为较大的值不会影响的适配器的功能。  
  
## <a name="see-also"></a>另请参阅  
[解决 SQL 适配器](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)