---
title: "使用轮询的入站调用的支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae02a93a-808f-4774-a2c4-efdf39a4d49a
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8533ce2829fec956819b311fd6b8f99479f40d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-inbound-calls-using-polling"></a>使用轮询的入站调用的支持
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]启用客户端程序来告知他们对 Oracle E-business Suite 中的数据的更改的 Oracle E-business Suite 从接收消息。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收适配器指定的 SQL 语句、 存储的过程、 函数或在包中，过程将执行其中的"轮询基于"消息的支持检索数据，然后将定期的提供给客户端的结果时间。  
  
> [!NOTE]
>  您还可以设置中的轮询操作的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 它是一定要设置轮询操作的应用程序上下文，如果对接口表或接口视图执行此操作。 有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
 典型轮询操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]涉及下列：  
  
1.  适配器客户端必须指定`Polling`中的入站操作作为**InboundOperationType**绑定属性。 此绑定属性的默认值是**轮询**。  
  
2.  适配器客户端必须指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性来确定是否存在可用于轮询数据。 如果第一个返回的结果集上执行此语句的第一行的第一列包含一个正整数值，则日期可用于轮询。  
  
3.  适配器客户端必须指定一个轮询间隔以供**PollingInterval**绑定属性来定义以秒为单位语句中指定的间隔**PolledDataAvailableStatement**执行绑定属性。 在每个轮询间隔结束时，执行轮询的数据可用语句，并返回的结果集。  
  
4.  适配器客户端必须指定 SELECT 语句或存储的过程作为**PollingInput**绑定属性。 如果你想要轮询的表或视图，则必须指定此绑定属性的 SELECT 语句。 如果你想要轮询使用存储的过程，你必须指定此绑定属性的整个请求消息。  
  
     中的语句**PollingInput**仅当没有数据可用于轮询，它由绑定属性执行**PolledDataAvailableStatement**步骤 2 中的绑定属性。  
  
5.  适配器客户端必须指定中的轮询操作的一项操作**PollingAction**绑定属性。 针对特定操作的轮询操作由使用适配器服务外接程序使用的操作生成的元数据。  
  
6.  适配器客户端可以使用**PollWhileDataFound**绑定忽略轮询间隔，并持续轮询数据，和时可用的属性。  
  
    > [!IMPORTANT]
    >  如果你设置的值**PollWhileDataFound**绑定属性为 True，适配器客户端持续轮询数据从 Oracle 和进程中打开和关闭连接到 Oracle 数据库在循环中。 如 ODP.NET 打开连接的速率大于正在关闭的连接，连接获取耗尽一段时间后，将引发异常。 作为替代，请确保值**UseOracleConnectionPool**设置为 True，和中提到了适当的值**IncrPoolSize**绑定属性控制的连接数可以打开适配器客户端。  
  
7.  适配器客户端可以为指定的后轮询语句，Oracle PL/SQL 块**PostPollStatement**绑定属性。 此绑定属性中指定的语句执行的语句中指定后**PollingInput**绑定属性执行。  
  
    > [!NOTE]
    >  适配器执行的语句中指定**PollingInput**和**PostPollStatement**将属性绑定在事务中。 有关详细信息中的事务有关[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[原理适配器处理事务？](https://msdn.microsoft.com/library/dd788428.aspx)。  
  
 适配器禁止显示来自 Oracle E-business Suite 的任何空轮询响应。  
  
 下图提供有关中的轮询工作流信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 轮询工作流的两种方案图所示：  
  
1.  时的值**PollWhileDataFound**设置为"False"（默认设置）。  
  
2.  时的值**PollWhileDataFound**设置为"True"。  
  
 ![轮询方案 &#40;PollWhileDataFound &#61;False &#41;] (../../adapters-and-accelerators/adapter-oracle-ebs/media/e5f00f4c-cc76-4e8b-9991-b4471f9d4865.gif "e5f00f4c-cc76-4e8b-9991-b4471f9d4865") ![轮询方案 &#40;PollWhileDataFound &#61;True &#41;] (../../adapters-and-accelerators/adapter-oracle-ebs/media/ebecf64c-a770-4525-9c75-62fdb71e1fb1.gif "ebecf64c-a770-4525-9c75-62fdb71e1fb1")  
  
## <a name="differences-between-polling-and-notification"></a>轮询和通知之间的差异  
 尽管轮询和通知是这两个入站的操作，Oracle 数据库中的数据更改通知适配器客户端下, 表列出这两者之间的一些差异。 以下差异将帮助你决定在具体取决于你的要求操作：  
  
|轮询|通知|  
|-------------|------------------|  
|所有支持的 Oracle 数据库版本支持轮询[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。|对于 Oracle 数据库版本 10.2 及更高版本才支持通知。|  
|你可以配置的轮询间隔来检查可用于按固定时间间隔轮询数据或即时的方式，以及何时有可用的数据。 **提示：**轮询可以为你提供更佳的吞吐量在数据更改发生连续，并且不希望为每项更改的和发生时要通知的情况下。 作为替代，你指定要在其后的发生是因为最后一个更改通知的所有更改的通知轮询间隔。|数据更改通知始终是即时的。|  
|轮询启动的适配器。 适配器执行 SQL 语句以验证是否数据可用于轮询，并随后通过执行轮询语句，如果某些数据可用于轮询开始轮询。|Oracle 数据库发出通知。 只需适配器发出的通知语句指示要在该语句结果集中的更改的情况下启动通知的数据库。 通知是 Oracle 数据库的一项功能。|  
|轮询语句可用于读取或更新的 Oracle 数据库中的数据。|可以使用通知语句仅具有读取 Oracle 数据库中的数据。|  
|轮询通知你有关已更改的实际数据信息。|通知会告知仅如 Insert、 数据中的更改类型的更新和删除。|  
  
 有关详细信息：  
  
-   绑定属性与轮询，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
-   接收基于轮询的消息使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[Oracle E-business Suite 使用 BizTalk 服务器进行轮询](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)