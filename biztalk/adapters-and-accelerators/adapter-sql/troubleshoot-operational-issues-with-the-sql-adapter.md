---
title: 使用 SQL 适配器在 BizTalk 中进行的操作问题故障排除 |Microsoft Docs
description: 常见的问题和解决方法的 SQL 适配器在 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c75f85f4-cd03-4c6a-aac9-a6d02d3c3449
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d167777ccd9fd9ccb2ddc5a43410d798bde3e7b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367516"
---
# <a name="troubleshoot-operational-issues-with-the-sql-adapter"></a>使用 SQL 适配器进行的操作问题故障排除
本部分讨论如何使用故障排除技术来解决操作使用时可能遇到的错误[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]。  
  
## <a name="enabling-tracing"></a>启用跟踪  
 必须启用该适配器之间的跟踪[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，并以收集问题的任何详细信息的 SQL Server 在使用时遇到[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 有关跟踪中的支持的详细信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[诊断跟踪和消息日志记录中的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)。  
  
## <a name="known-issues"></a>已知问题  
 以下是在使用时可能遇到的最常见错误[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，以及其可能的原因和解决方法。  
  
  
  
###  <a name="BKMK_SQLLoadBinding"></a> 加载适配器绑定时出错  
 **问题**  
  
 当您尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，收到以下错误：  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 当您尝试启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 将加载所有已安装的适配器的适配器绑定。 反过来，适配器绑定都依赖于企业应用程序特定的客户端软件。 如果你这样做将适配器安装中包含的所有适配器的典型或完全安装，可能会遇到此问题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 但是，可能只有一个企业应用程序安装 LOB 客户端库。 因此，在 GUI 无法加载其他适配器的绑定。  
  
 **解决方法**  
  
 请确保执行要安装仅需要的适配器的适配器的自定义安装。  
  
###  <a name="BKMK_SQLDisplay"></a> SQL 适配器不会显示在 BizTalk Server 管理控制台中的适配器列表中  
 **问题**  
  
 与早期版本附带的适配器的不同[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]中的适配器列表中未显示[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 **原因**  
  
 最新[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是 WCF 自定义绑定。 因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，因此，不会显示基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 **解决方法**  
  
 您可以显式添加[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。  
  
###  <a name="BKMK_MissingAction"></a> 在 SQL Server 数据库上执行操作时出错  
 **问题**  
  
 执行 SQL Server 数据库使用的任何操作时，适配器将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
- **为 BizTalk Server**  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  **原因**  
  
  未指定消息的 WCF 操作。 WCF 需要用于为每个操作，向适配器通知上的 LOB 应用程序执行的操作指定的 SOAP 操作。  
  
  **解决方法**  
  
  在发送端口或为 BizTalk 业务流程的消息上下文属性指定的 SOAP 操作。 有关说明，请参阅[配置 SQL 适配器的 SOAP 操作](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)。 请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)若要查看每个操作的操作的列表。  
  
###  <a name="BKMK_SQLInvalidOp"></a> 与错误代码的 InvalidOperationException 执行 FILESTREAM 操作时 = 5  
 **问题**  
  
 使用时遇到以下错误[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]用于执行 FILESTREAM 操作。  
  
```  
System.InvalidOperationException: OpenSqlFileStream returned error.  
ErrorCode:5  
  
```  
  
 **原因**  
  
 您可能会指定用于连接到 SQL Server 数据库的数据库凭据。 若要执行 FILESTREAM 操作，必须始终使用 Windows 身份验证。 错误代码"5"表示的访问被拒绝，因为不正确的凭据。 有关不同的错误代码的详细信息，请参阅[系统错误代码 (0-最初包含 499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx)。
  
 **解决方法**  
  
 使用 Windows 身份验证连接到 SQL Server 数据库。 在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，就可以做到将用户名称和密码字段留空 WCF 自定义或 WCF SQL 端口配置对话框中。  
  
###  <a name="BKMK_SQLPolling"></a> 轮询操作不返回任何消息即使 PollingStatement 和 PolledDataAvailableStatement 指定了有效语句  
 **问题**  
  
 即使为 PollingStatement 和 PolledDataAvailableStatement 绑定属性指定了有效的值，则该适配器不从 SQL Server 接收轮询消息。  
  
 **原因**  
  
 验证任何其他事务是否已在适配器轮询的表上获取锁。  
  
 **解决方法**  
  
 如果你想要轮询正在更新作为另一个事务的一部分的表，可以考虑使用"with (nolock)"参数作为 PolledDataAvailableStatement 绑定属性指定的查询的一部分，以确保即使施加锁定返回数据由其他事务。 有关详细信息，请参阅[数据库引擎中的锁定 SQL](https://msdn.microsoft.com/library/ms190615.aspx)。
  
###  <a name="BKMK_SQLSingleOp"></a> 该适配器无法插入、 更新或删除在单个操作中使用 BizTalk Server 的数据量很大  
 **问题**  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]无法插入、 更新或删除在单个操作中使用的数据量很大[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 **原因**  
  
 插入、 更新或删除数据量很大可能需要时间和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]或在其中正在执行操作，该事务可能会超时。  
  
 **解决方法**  
  
- **为 BizTalk Server**  
  
  1. 在 machine.config 中指定的 WCF 适配器的超时时间。导航到下的 machine.config 文件\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG 并添加如下所示的摘录。  
  
     ```  
     <configuration>  
      <system.transactions>  
       <machineSettings maxTimeout="02:00:00" />  
      </system.transactions>  
     </configuration>  
     ```  
  
      使用此设置时，WCF 适配器超时设置为 2 小时。  
  
  2. 在 machine.config 中指定的超时设置的 MSDTC 事务。导航到下的 machine.config 文件\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG 并添加如下所示的摘录。  
  
     ```  
     <system.transactions>   
             <defaultSettings distributedTransactionManagerName="<computer_name>" timeout="02:00:00"/>   
         </system.transactions>  
  
     ```  
  
      使用此设置，MSDTC 超时设置为 2 小时。 MSDTC 超时的默认值为 10 分钟。  
  
     > [!IMPORTANT]
     >  运行适配器客户端和 SQL Server 的计算机上，必须进行此更改。 摘录中，运行适配器客户端和 SQL Server 计算机的名称替换 < 计算机名 >。  
  
  3. 设置**SendTimeout**绑定属性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]为相当大的值。 有关如何设置绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。  
  
###  <a name="BKMK_SQLFullSchemaValidate"></a> 包含数据集的响应消息的 BizTalk Server 中的完整架构验证失败  
 **问题**  
  
 返回包含数据集，例如 ExecuteReader 的响应消息的操作的完整架构验证失败中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 **解决方法**  
  
 我们建议你为不包含数据集的响应消息的完整架构验证。 相反，可以执行以下操作：  
  
1.  返回的响应消息的架构后，请执行此操作。  
  
2.  将架构从响应消息复制到一个.xsd 文件并将其添加到 BizTalk 项目。  
  
3.  在业务流程中使用 xpath 查询以从响应消息中提取的数据。  
  
###  <a name="BKMK_SQLRootNode"></a> 使用 BizTalk 项目中的 RootNode TypeName 错误  
 **问题**  
  
 中的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，则从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效的字符或保留的字**RootNode TypeName**属性，编译项目时将发生以下错误:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解决方法**  
  
1.  右键单击该错误，然后选择中引用的 rood 这样节点**属性**。  
  
2.  有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，点 （.）。  
  
###  <a name="BKMK_SQLMetadataStronglyTyped"></a> 适配器无法将生成的强类型化的存储过程与临时表的元数据  
 **问题**  
  
 该适配器无法生成的强类型化的存储过程，包括其定义中的临时表的元数据。 适配器提供了以下异常。  
  
```  
Microsoft.ServiceModel.Channels.Common.MetadataException:  
Retrieval of Operation Metadata has failed while building WSDL at 'TypedProcedure/<schema>/<stored_procedure_name>' --->  
System.Data.SqlClient.SqlException: Invalid object name '<temp_table_name>'.  
  
```  
  
 **解决方法**  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持生成元数据的强类型化的存储过程包含其定义中的临时表。 相反，应生成相同的过程从下的元数据**过程**时使用的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
###  <a name="BKMK_SQLVS2008"></a> 无效的绑定时出现的警告在 Visual Studio 中使用适配器  
 **问题**  
  
 当适配器用于在 Visual Studio 中创建应用程序并打开由适配器生成的配置文件 (app.config) 时，您会看到类似于下面的警告：  
  
```  
The element 'bindings' has invalid child element 'sqlBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 会出现此警告[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定， `sqlBinding`，不标准绑定随附于[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。  
  
 **解决方法**  
  
 可以放心地忽略此警告。  
  
###  <a name="BKMK_SQLNotification"></a> BizTalk Server 将引发异常，如果在同一个应用程序中使用多个通知架构或在同一主机上的多个应用程序中使用通知架构  
 **问题**  
  
 BizTalk Server 将引发异常，表明该应用程序找不到文档规范，因为多个架构匹配的消息类型或 XLANG 异常。  
  
 **原因**  
  
 由于以下任一发生这种情况：  
  
- 已生成多个通知架构在 BizTalk Server 项目中，部署到 BizTalk Server 应用程序，然后运行应用程序从 SQL Server 数据库中接收通知。 由于通知架构都是公用的冲突之间没有 BizTalk Server 应用程序中部署的架构。  
  
- 发生多个项目时您已为每个 BizTalk Server 部署的项目，每个项目到同一主机上单独的 BizTalk Server 应用程序生成的通知架构，然后运行应用程序或应用程序以接收来自通知SQL Server 数据库中。 因为架构和程序集都是可访问 BizTalk Server 中的应用程序，则冲突之间常见的架构部署在各种 BizTalk Server 应用程序和程序集。  
  
  **解决方法**  
  
  为 BizTalk Server 应用程序使用单个通知架构文件。 如果需要在同一主机上的多个 BizTalk Server 应用程序中使用通知架构，创建包含单个通知架构的应用程序，然后使用 BizTalk Server 中的从所有其他应用程序的通知架构。  
  
###  <a name="BKMK_SQLRestoreConn"></a> 适配器客户端会引发异常的连接恢复之间适配器客户端和 SQL Server 数据库后执行的操作  
 **问题**  
  
 适配器客户端会引发以下异常在执行 SQL Server 数据库上的操作：  
  
```  
{System.Data.Common.DbException} = {"A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.)"}  
```  
  
 **原因**  
  
 执行过程中的操作，适配器使用该连接从 SQL ADO.NET 连接池中连接到 SQL Server 数据库，并执行该操作。 如果适配器客户端和 SQL Server 数据库之间的短暂的网络中断，或者如果 SQL Server 数据库暂时已关闭，SQL ADO.NET 连接池中的所有连接都将失效。 还原连接并尝试对 SQL Server 数据库执行操作之后，则适配器将使用从 SQL ADO.NET 连接池中，相同的无效连接并因此适配器客户端引发异常。  
  
 **解决方法**  
  
 适配器客户端应在其操作执行它们应该捕获异常和指定的操作重试计数为"n + 1"位置中实施重试逻辑，其中"n"是为 MaxConnectionPoolSize 绑定属性指定的值。 这意味着，如果有"n"中的连接池具有已呈现为无效的连接数，从理论上讲适配器客户端应重试"n + 1"的最长时间，以获取有效的连接，并因此执行该操作。  
  
 例如，若要指定重试计数[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，打开**属性**对话框中的应用程序中的发送端口，单击**传输高级选项**在左窗格中的对话框中，并在**传输选项**区域中，指定的值**重试计数**列表。  
  
###  <a name="BKMK_MemUsage"></a> 内存使用情况和线程数将增加时在事务处理的入站操作中使用适配器  
 **问题**  
  
 在事务处理的入站操作中，如轮询，**如果没有数据轮询表中可用**并且该适配器将继续轮询，一段时间内遇到内存使用情况和线程计数的增加。  
  
 **原因**  
  
 **如果没有数据轮询表中可用**后，每个接收超时周期[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]产生了一个新的线程无法继续轮询操作。 因此，一段时间内会增加线程计数和内存使用情况。 但是，如果正在轮询一次的表具有一些数据，同一个线程继续执行所有后续轮询。  
  
 **解决方法**  
  
 我们建议设置**ReceiveTimeout**的最大可能值，这是 24.20:31:23.6470000 （24 天），以便生成新线程，仅每隔 24 天。 这将确保，内存使用情况和线程计数不会不会变得太多时间太短。  
  
> [!NOTE]
>  如果尚未设置 SqlAdapterInboundTransactionBehavior，请确保 TransactionTimeout 也被配置为最大可能值，即 24.20:31:23.6470000 （24 天）。 在使用此解决方法，我们可以添加 SqlAdapterInboundTransactionBehavior，仅当事务隔离级别必须进行配置。 否则，它是删除该行为的最佳做法。  
  
 有关详细信息**ReceiveTimeout**绑定属性，请参阅[了解有关 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 指定绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。  
  
> [!NOTE]
>  使用的适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，超时值设置为较大的值不会影响适配器的功能。  
  
## <a name="see-also"></a>请参阅  
[SQL 适配器疑难解答](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)