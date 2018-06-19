---
title: 使用 SELECT 语句的轮询 Oracle E-business Suite |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81d70b36-8b80-4ab9-b97c-ee861aafbbac
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83e5b40d8176b8e4ba448cadf1676013db8f2706
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966907"
---
# <a name="poll-oracle-e-business-suite-using-select-statement"></a>使用 SELECT 语句的轮询 Oracle E-business Suite
你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要通过使用 SELECT 语句持续轮询接口表接收定期的数据更改消息，接口视图、 表和 Oracle E-business Suite 中的视图。 你可以指定为适配器执行定期轮询 Oracle E-business Suite 的轮询语句的 SELECT 语句。 你还可以指定后轮询 PL/SQL 代码块适配器执行执行轮询语句后。  
  
 若要启用轮询，必须指定 WCF 自定义或 WCF OracleEBS 上的特定绑定属性接收端口。  有关如何适配器支持轮询的详细信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。 有关轮询操作的 SOAP 消息结构的信息，请参阅[轮询操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-polling-operations1.md)。  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a>使用 Oracle E-business Suite 适配器绑定属性中配置的轮询操作  
 下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]更改消息的绑定属性，用于配置适配器，以接收数据。 配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定是否想要执行**轮询**或**通知**入站操作。 默认值是**轮询**。|  
|**PolledDataAvailableStatement**|指定适配器以确定任何数据是否可用于轮询将执行的 SQL 语句。 仅当一条记录时，SELECT 语句你为指定**PollingInput**将执行绑定属性。|  
|**PollingInterval**|指定的时间间隔，以秒为单位，从该处[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。 默认值为 30 秒。 轮询间隔确定连续两次轮询之间的时间间隔。 如果在指定间隔内执行该语句，该适配器休眠的剩余时间的时间间隔内。|  
|**PollingInput**|指定的轮询语句。 若要轮询使用 SELECT 语句，必须指定此绑定属性的 SELECT 语句。 默认值为 null。<br /><br /> 必须指定的值**PollingInput**绑定属性来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。|  
|**PollingAction**|指定轮询操作的操作。 你可以确定从元数据生成操作使用特定操作的轮询操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。|  
|**PostPollStatement**|指定在指定的语句之后执行的语句块**PollingInput**绑定属性执行。|  
|**PollWhileDataFound**|指定是否[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]忽略轮询间隔和连续执行轮询语句中，如果数据中轮询的表。 如果表中可用的任何数据不，该适配器将恢复执行轮询语句按照指定的轮询间隔。 默认值为 false。|  
  
 有关这些属性的更完整说明，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要轮询的 Oracle 数据库，进一步阅读。  
  
## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 在此主题中，以演示如何[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收数据的支持更改使用 SELECT 语句的消息、 创建 BizTalk 项目和生成架构**轮询**你想要轮询的表的操作。 在本主题中，我们生成架构**轮询**操作**MS_SAMPLE_EMPLOYEE**接口中的表**应用程序对象库**应用程序。 运行示例后，在 Oracle E-business Suite 中创建这些对象提供的 create_apps_artifacts.sql 脚本时创建此表。  
  
 接下来，我们将使用基于内容的路由 (CBR) 中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将轮询从接收消息的接收端口配置应用程序**MS_SAMPLE_EMPLOYEE**接口表，然后将它路由到发送端口。 在这种情况下，我们将在检查接收位置指定，并将消息路由到发送端口发送端口上创建筛选器。  
  
 为了演示轮询操作，我们执行以下操作：  
  
-   指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性以确定其中接口表轮询 (MS_SAMPLE_EMPLOYEE) 有任何数据。 在此示例中，你可以设置为此绑定属性：  
  
    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     这可确保仅当 MS_SAMPLE_EMPLOYEE 接口表具有某些记录时，适配器都将执行轮询语句。  
  
-   指定 SELECT 语句，以**PollingInput**绑定属性。 此语句将检索 MS_SAMPLE_EMPLOYEE 接口表中的所有行。 在此示例中，你可以设置为此绑定属性：  
  
    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  
  
    > [!NOTE]
    >  有关 FOR UPDATE 子句的 SELECT 语句中使用的信息，请参阅[轮询 Oracle E-business Suite 使用 SELECT 语句](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)。  
  
-   指定作为的一部分的 DELETE 语句**PostPollStatement**绑定属性。 此语句将从 MS_SAMPLE_EMPLOYEE 接口表中删除所有数据。 在此示例中，你可以设置为此绑定属性：  
  
    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     一旦发生这种情况下, 一次为指定的语句**PollingInput**将执行，它将不提取任何数据。  
  
-   直到更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表，则将无法获得任何轮询消息。 因此，你必须重新填充 MS_SAMPLE_EMPLOYEE 接口表与新记录。 你可以通过运行这些示例使用提供的 insert_apps_data.sql 脚本来实现。 运行此脚本后下, 一个轮询操作将获取新记录插入到表。  
  
## <a name="how-to-receive-data-change-messages-from-oracle-e-business-suite"></a>如何从 Oracle E-business Suite 接收数据更改消息  
 使用 Oracle 数据库上执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及以下过程任务中所述[创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要配置的适配器轮询 Oracle E-business Suite 使用 SELECT 语句，这些任务包括：  
  
1.  创建 BizTalk 项目，并生成架构**轮询**你想要轮询接口表的操作。  
  
2.  生成和部署 BizTalk 项目。  
  
3.  配置的 BizTalk 通过创建的应用程序接收和发送端口。 此外，在发送端口上添加筛选器，以便它检查中接收端口中，指定的接收位置和轮询消息路由到发送端口。  
  
    > [!IMPORTANT]
    >  你始终必须配置的入站的轮询方案单向接收端口。 双向接收入站操作不支持端口。  
  
4.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 使用 BizTalk 适配器包还提供了一个示例中，PollingUsingSelectStatement，基于本主题。 有关详细信息，请参阅[示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。  
  
## <a name="generating-schema"></a>生成架构  
 必须生成的架构**轮询**操作中的 MS_SAMPLE_EMPLOYEE 接口表**应用程序对象库**应用程序。 生成架构使用时执行以下任务[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
-   选择与具有协定类型**服务 （入站操作）**。  
  
-   生成架构**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。 你可以选择该操作，接口表从**基于应用程序的视图**节点或**项目-基于视图**节点。  
  
 有关如何生成架构的详细信息，请参阅[浏览，搜索，并获得用于 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
## <a name="building-and-deploying-the-biztalk-project"></a>构建和部署 BizTalk 项目  
 现在，你必须生成 BizTalk 解决方案中，并将其部署到 BizTalk Server。 有关将解决方案部署到 BizTalk Server 的信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，应用程序下列出**应用程序**BizTalk Server 管理控制台中的节点。 必须使用 BizTalk Server 管理控制台配置该应用程序。 作为配置应用程序的一部分，必须在应用程序，创建一个接收端口和发送端口，然后将筛选器添加到发送端口以便从接收端口的所有消息都路由到发送端口。  
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   创建接收和发送端口。  
  
### <a name="creating-a-receive-port"></a>创建接收端口  
 你必须创建一个 WCF 自定义或 WCF OracleEBS 单向接收端口，从而轮询使用为指定的 SELECT 语句的 Oracle **PollingInput**绑定属性。 有关如何创建接收端口，请参阅[手动配置到 Oracle E-business 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。 在创建时接收端口，请确保指定以下绑定属性。  
  
 **进行轮询**  
  
|绑定属性|值|  
|----------------------|-----------|  
|**InboundOperationType**|将其设置为**轮询**。|  
|**PolledDataAvailableStatement**|此示例中，此绑定属性设置为：<br /><br /> `SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE`|  
|**PollingAction**|为生成的架构从检索轮询操作**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。 对于此示例中，此绑定属性设置为**InterfaceTables/轮询/查找/应用程序/MS_SAMPLE_EMPLOYEE**。|  
|**PollingInput**|此绑定属性，指定要从 MS_SAMPLE_EMPLOYEE 接口该表中检索所有记录的 SELECT 语句。 此示例中，此绑定属性设置为：<br /><br /> `SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE`|  
|**PostPollStatement**|指定要从 MS_SAMPLE_EMPLOYEE 接口表中删除所有数据的后轮询声明。 此示例中，此绑定属性设置为：<br /><br /> `DELETE FROM MS_SAMPLE_EMPLOYEE`|  
  
 **用于设置应用程序上下文**  
  
 如果您正在执行对 Oracle E-business Suite 项目的操作，则必须指定要设置的应用程序上下文的合适的绑定属性的值。 有关应用程序上下文和所需的设置应用程序上下文的绑定属性的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
 对于此示例中，指定为相应值**oracleUserName**， **oraclePassword**，和**oracleEBSResponsibility**绑定属性。  
  
> [!NOTE]
>  我们建议在执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 你可以这样做通过配置接收端口时添加的服务行为。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和与 Oracle E-business Suite 的事务超时](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。  
  
### <a name="creating-a-send-port"></a>创建发送端口  
 硬盘上定义的位置和创建相应的文件发送端口其中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将从 Oracle 丢弃消息。 这些消息将以响应接收端口指定轮询语句。 有关如何创建发送端口的信息，请参阅[手动配置到 Oracle E-business 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。  
  
 你还必须添加筛选器上发送端口将消息路由到从接收位置。 若要将筛选器添加到发送端口：  
  
1.  双击要打开的发送端口**发送端口属性**对话框。  
  
2.  在**发送端口属性**对话框中，单击**筛选器**选项卡。  
  
3.  请指定以下值：  
  
    -   在**属性**列表中，单击**BTS。ReceivePortName**。  
  
    -   在**运算符**列表中，单击 **==** 。  
  
    -   在**值**字段中，指定接收端口名称。  
  
4.  在**发送端口属性**对话框中，单击**确定**。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动轮询 Oracle E-business Suite 的 BizTalk 应用程序。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF OracleEBS 单向接收端口，从而轮询使用为指定的 SELECT 语句的 Oracle **PollingInput**绑定属性，正在运行。  
  
-   文件发送端口，从而从 Oracle 数据库中接收消息，正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，下面的一组操作需要置于相同的序列：  
  
-   适配器执行**PolledDataAvailableStatement**它返回一个正值，该值指示要执行的语句，为指定的适配器**PollingInput**绑定属性。  
  
-   适配器执行的 SELECT 语句**PollingInput** MS_SAMPLE_EMPLOYEE 接口表中的绑定属性，并返回所有行。 从 Oracle E-business Suite 响应如下所示：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Poll xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">   
      <DATA>   
        <SelectRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">   
         <EMP_NO>10002</EMP_NO>   
         <NAME>JEFF PRICE</NAME>   
         <DESIGNATION>MANAGER</DESIGNATION>   
         <SALARY>25000</SALARY>   
         <JOIN_DATE>2007-12-15T00:00:00</JOIN_DATE>   
        </SelectRecord>   
        <SelectRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">   
         <EMP_NO>10003</EMP_NO>   
         <NAME>DON HALL</NAME>   
         <DESIGNATION>ACCOUNTANT</DESIGNATION>   
         <SALARY>12000</SALARY>   
         <JOIN_DATE>2005-10-29T00:00:00</JOIN_DATE>   
        </SelectRecord>   
        …        
        <SelectRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">   
         …   
        </SelectRecord>   
        …   
      </DATA>   
    </Poll>  
    ```  
  
-   适配器执行后轮询语句，用于从 MS_SAMPLE_EMPLOYEE 接口表中删除所有数据。  
  
-   轮询间隔后，该适配器再次执行**PolledDataAvailableStatement**。 由于 MS_SAMPLE_EMPLOYEE 接口该表有没有记录现在， **PolledDataAvailableStatement**不返回一个正值，并且因此适配器不执行为指定的语句**PollingInput**绑定属性。 因此，适配器客户端不会获取任何轮询消息。  
  
-   适配器客户端不会获得更多的轮询消息，直到某些记录显式插入 MS_SAMPLE_EMPLOYEE 接口表。 要插入更多的记录，你可以运行这些示例使用提供的 insert_apps_data.sql 脚本。 运行此脚本下, 一次后**PolledDataAvailableStatement**是执行，返回一个正值。 因此，适配器执行轮询的语句，适配器客户端可能再次收到轮询消息。  
  
> [!NOTE]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将继续轮询除非你显式禁用接收端口从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口和接收端口。 有关绑定文件的详细信息，请参阅[重用 Oracle E-business Suite 适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  
  
## <a name="see-also"></a>另请参阅  
 [轮询 Oracle E-business Suite 使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)