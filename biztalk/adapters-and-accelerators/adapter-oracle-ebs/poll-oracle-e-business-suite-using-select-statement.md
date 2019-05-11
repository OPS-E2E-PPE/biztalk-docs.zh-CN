---
title: 使用 SELECT 语句轮询 Oracle E-business Suite |Microsoft Docs
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
ms.openlocfilehash: cb6c7ff189ffe711e34d087f0a00cff72abed082
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374987"
---
# <a name="poll-oracle-e-business-suite-using-select-statement"></a>使用 SELECT 语句轮询 Oracle E-business Suite
你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要接收使用 SELECT 语句，若要连续轮询接口表定期的数据更改消息，接口视图、 表和 Oracle E-business Suite 中的视图。 您可以指定为适配器执行定期轮询 Oracle E-business Suite 的轮询语句的 SELECT 语句。 此外可以指定后轮询 PL/SQL 代码块适配器执行轮询语句执行后。  

 若要启用轮询，必须指定 WCF 自定义或 WCF OracleEBS 的特定绑定属性接收端口。  有关如何在适配器支持轮询的详细信息，请参阅[支持用于入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。 轮询操作的 SOAP 消息结构的信息，请参阅[轮询操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-polling-operations1.md)。  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a>使用 Oracle E-business Suite 适配器的绑定属性中配置轮询操作  
 下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定属性，用于将适配器配置为接收数据更改消息。 配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  


|         绑定属性         |                                                                                                                                                                                                                            Description                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                          指定是否想要执行**轮询**或**通知**的入站操作。 默认值是**轮询**。                                                                                                                                                                          |
| **PolledDataAvailableStatement** |                                                                                                             指定适配器执行以确定是否可用于轮询的任何数据的 SQL 语句。 仅当一条记录不可用，SELECT 语句指定的**PollingInput**将执行属性绑定。                                                                                                              |
|       **PollingInterval**        | 指定的时间间隔，以秒为单位，从该处[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]执行该语句为指定**PolledDataAvailableStatement**属性绑定。 默认值为 30 秒。 轮询间隔确定连续轮询之间的时间间隔。 如果在指定时间间隔内执行该语句，则适配器将休眠的剩余时间间隔中。 |
|         **PollingInput**         |                         指定的轮询语句。 若要轮询使用 SELECT 语句，必须指定此绑定属性的 SELECT 语句。 默认值为 NULL。<br /><br /> 必须指定的值**PollingInput**绑定属性来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**属性绑定。                          |
|        **PollingAction**         |                                                                                                    指定轮询操作的操作。 您可以确定操作使用生成的元数据中的特定操作的轮询操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。                                                                                                     |
|      **PostPollStatement**       |                                                                                                                                                                  指定在指定的语句之后执行的语句块**PollingInput**执行绑定属性。                                                                                                                                                                  |
|      **PollWhileDataFound**      |                                    指定是否[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]忽略的轮询间隔，连续执行轮询语句中，如果数据是可用的轮询的表。 如果表中有任何数据，不则适配器将恢复执行轮询语句按照指定的轮询间隔。 默认值为 false。                                     |

 有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要轮询 Oracle 数据库，请阅读更多。  

## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 本主题演示如何[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收数据的支持更改使用 SELECT 语句的消息、 创建 BizTalk 项目和生成架构**轮询**你想要轮询的表的操作。 在本主题中，我们生成的架构**轮询**操作**MS_SAMPLE_EMPLOYEE**中的接口表**应用程序对象库**应用程序。 运行提供的示例在 Oracle E-business Suite 中创建这些对象的 create_apps_artifacts.sql 脚本时创建此表。  

 接下来，我们将使用基于内容的路由 (CBR) 中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将接收轮询消息的接收端口配置应用程序**MS_SAMPLE_EMPLOYEE**接口表，并路由至发送端口。 在这种情况下，我们将检查指定的接收位置，并将消息路由到发送端口的发送端口上创建筛选器。  

 为了演示轮询操作，我们执行以下操作：  

-   指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性，以确定其中接口表正在轮询一次 (MS_SAMPLE_EMPLOYEE) 有任何数据。 在此示例中，可以设置为此绑定属性：  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     这可确保只有 MS_SAMPLE_EMPLOYEE 接口表有某些记录时，适配器都将执行轮询语句。  

-   指定 SELECT 语句，以**PollingInput**属性绑定。 此语句检索 MS_SAMPLE_EMPLOYEE 接口表中的所有行。 在此示例中，可以设置为此绑定属性：  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  有关 FOR UPDATE 子句的 SELECT 语句中使用的信息，请参阅[使用 SELECT 语句轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)。  

-   指定 DELETE 语句的一部分**PostPollStatement**属性绑定。 此语句将 MS_SAMPLE_EMPLOYEE 接口表中删除所有数据。 在此示例中，可以设置为此绑定属性：  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     一旦发生这种情况下, 一次为指定的语句**PollingInput**将执行，它将不提取任何数据。  

-   之前更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表，您将无法获得任何轮询消息。 因此，您必须重新填充 MS_SAMPLE_EMPLOYEE 接口表与新的记录。 可以通过运行这些示例提供的 insert_apps_data.sql 脚本执行操作。 在运行此脚本后下, 一个轮询操作将提取新记录插入到表。  

## <a name="how-to-receive-data-change-messages-from-oracle-e-business-suite"></a>如何从 Oracle E-business Suite 中接收数据更改消息  
 执行对 Oracle 数据库使用的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及以下过程任务中所述[来创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要配置的适配器轮询 Oracle E-business Suite 使用 SELECT 语句，这些任务包括：  

1. 创建 BizTalk 项目，并生成的架构**轮询**你想要轮询的接口表的操作。  

2. 生成并部署 BizTalk 项目。  

3. 配置的 BizTalk 应用程序通过创建接收和发送端口。 此外，在发送端口上添加筛选器，以便它会检查在接收端口中指定的接收位置和轮询消息路由到发送端口。  

   > [!IMPORTANT]
   >  为入站的轮询方案，始终必须配置一个单向接收端口。 双向接收端口不支持的入站操作。  

4. 启动 BizTalk 应用程序。  

   本主题介绍如何执行这些任务。  

## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 使用 BizTalk Adapter Pack 还提供的示例中，PollingUsingSelectStatement，根据本主题。 有关详细信息，请参阅[示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。  

## <a name="generating-schema"></a>生成架构  
 必须生成的架构**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作**应用程序对象库**应用程序。 执行以下任务，同时生成架构使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  

- 选择作为协定类型**服务 （入站操作）**。  

- 生成架构**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。 您可以选择该操作和接口表从**基于应用程序的视图**节点或**项目-基于视图**节点。  

  有关如何生成架构的详细信息，请参阅[浏览、 搜索和获取 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  

## <a name="building-and-deploying-the-biztalk-project"></a>生成和部署 BizTalk 项目  
 现在必须生成 BizTalk 解决方案，并将其部署到 BizTalk Server。 有关将解决方案部署到 BizTalk Server 的信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。

## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，应用程序列入**应用程序**BizTalk Server 管理控制台中的节点。 必须使用 BizTalk Server 管理控制台来配置应用程序。 作为配置应用程序的一部分，必须在应用程序中创建的接收端口和发送端口，然后将筛选器添加到发送端口，以便从接收端口的所有消息都路由到发送端口。  

 配置应用程序包括：  

-   选择应用程序的主机。  

-   创建接收和发送端口。  

### <a name="creating-a-receive-port"></a>创建接收端口  
 必须创建 WCF 自定义或 WCF OracleEBS 单向接收端口，轮询使用 SELECT 语句为指定的 Oracle **PollingInput**属性绑定。 有关如何创建接收端口，请参阅[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。 在创建接收端口，请确保指定以下绑定属性。  

 **用于轮询**  

|绑定属性|ReplTest1|  
|----------------------|-----------|  
|**InboundOperationType**|将此设置为**轮询**。|  
|**PolledDataAvailableStatement**|对于此示例中，此绑定属性设置为：<br /><br /> `SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE`|  
|**PollingAction**|轮询操作检索有关生成的架构**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。 对于此示例中，此绑定属性设置为**InterfaceTables/轮询/查找/应用/MS_SAMPLE_EMPLOYEE**。|  
|**PollingInput**|对于此绑定属性，指定 SELECT 语句从 MS_SAMPLE_EMPLOYEE 接口表中检索所有记录。 对于此示例中，此绑定属性设置为：<br /><br /> `SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE`|  
|**PostPollStatement**|指定轮询后语句来删除 MS_SAMPLE_EMPLOYEE 接口表的所有数据。 对于此示例中，此绑定属性设置为：<br /><br /> `DELETE FROM MS_SAMPLE_EMPLOYEE`|  

 **用于设置应用程序上下文**  

 如果您正在执行对 Oracle E-business Suite 项目的操作，则必须指定要设置应用程序上下文的相应的绑定属性的值。 有关应用程序上下文和所需的设置应用程序上下文的绑定属性的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

 对于此示例中，指定相应的值**oracleUserName**， **oraclePassword**，并**oracleEBSResponsibility**绑定属性。  

> [!NOTE]
>  我们建议执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 可以配置接收端口时添加的服务行为来完成此操作。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和事务超时与 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。  

### <a name="creating-a-send-port"></a>创建发送端口  
 在硬盘上定义的位置并创建相应的文件发送端口其中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将从 Oracle 删除消息。 这些消息将以响应接收端口中指定的轮询语句。 有关如何创建发送端口的信息，请参阅[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。  

 您还必须添加一个筛选器上的发送端口将消息路由到从接收位置。 若要将筛选器添加到发送端口：  

1.  双击要打开的发送端口**发送端口属性**对话框。  

2.  在中**发送端口属性**对话框中，单击**筛选器**选项卡。  

3.  指定以下值：  

    -   在中**属性**列表中，单击**BTS。ReceivePortName**。  

    -   在中**运算符**列表中，单击**==**。  

    -   在中**值**字段中，指定接收端口名称。  

4.  在中**发送端口属性**对话框中，单击**确定**。  

## <a name="starting-the-application"></a>启动应用程序  
 必须启动轮询 Oracle E-business Suite 的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。  

 在此阶段，请确保：  

-   WCF 自定义或 WCF OracleEBS 单向接收端口，轮询使用 SELECT 语句为指定的 Oracle **PollingInput**绑定属性，正在运行。  

-   FILE 发送端口，从 Oracle 数据库接收消息，正在运行。  

## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，以下组操作需要置于相同的序列：  

-   适配器将执行**PolledDataAvailableStatement**这会返回正值，指示要执行的语句为指定的适配器**PollingInput**属性绑定。  

-   适配器执行的 SELECT 语句**PollingInput** MS_SAMPLE_EMPLOYEE 接口表中的绑定属性，并返回所有行。 来自 Oracle E-business Suite 的响应类似于以下内容：  

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

-   适配器执行轮询后语句从 MS_SAMPLE_EMPLOYEE 接口表中删除所有数据。  

-   轮询间隔后，适配器再次执行**PolledDataAvailableStatement**。 因为 MS_SAMPLE_EMPLOYEE 接口表现在，有没有记录**PolledDataAvailableStatement**不会返回正值，因此该适配器不会执行该语句为指定**PollingInput**属性绑定。 因此，适配器客户端不会获取任何轮询消息。  

-   适配器客户端不会获得更多轮询消息，直到显式向 MS_SAMPLE_EMPLOYEE 接口表中插入一些记录。 要插入更多的记录，可以运行这些示例提供的 insert_apps_data.sql 脚本。 在运行此脚本中下, 一次后**PolledDataAvailableStatement**是执行，它会返回正值。 因此，适配器将执行轮询语句和适配器客户端再次接收轮询消息。  

> [!NOTE]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将继续轮询，直到显式禁用该接收端口从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口和接收端口从文件导的配置设置。 有关绑定文件的详细信息，请参阅[Oracle E-business Suite 的重用适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  

## <a name="see-also"></a>请参阅  
 [轮询 Oracle E-business Suite 使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)