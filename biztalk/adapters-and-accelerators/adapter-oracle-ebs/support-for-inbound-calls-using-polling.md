---
title: 支持使用轮询的入站调用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae02a93a-808f-4774-a2c4-efdf39a4d49a
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 868e56730f21235e3f73f6ab91a463ea4589bafd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984662"
---
# <a name="support-for-inbound-calls-using-polling"></a>支持使用轮询的入站调用
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ，客户端程序可以接收来自 Oracle E-business Suite 告知他们对 Oracle E-business Suite 中的数据的更改的消息。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持接收适配器指定的 SQL 语句、 存储的过程、 函数或在包中的过程将执行其中的"基于轮询的"消息中检索数据，并到客户端的定期提供的结果时间。  

> [!NOTE]
>  此外可以设置中的轮询操作的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 它是必需的接口表或界面视图上执行该操作将轮询操作的应用程序上下文。 有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

 典型轮询操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]涉及以下：  

1. 适配器客户端必须指定`Polling`中的入站操作**InboundOperationType**属性绑定。 此绑定属性的默认值是**轮询**。  

2. 适配器客户端必须指定 SELECT 语句，以**PolledDataAvailableStatement**属性以确定是否存在可用于轮询数据绑定。 如果第一个返回的结果集上执行此语句的第一行的第一列包含一个正整数值，则日期可用于轮询。  

3. 适配器客户端必须指定为一个轮询间隔**PollingInterval**绑定属性，以秒为单位中指定的语句定义间隔**PolledDataAvailableStatement**执行属性绑定。 在每个轮询间隔结束时，执行轮询的数据可用语句，并返回的结果集。  

4. 适配器客户端必须指定 SELECT 语句或存储的过程**PollingInput**属性绑定。 如果你想要轮询的表或视图，则必须指定此绑定属性的 SELECT 语句。 如果你想要使用的存储的过程轮询，则必须指定此绑定属性的整个请求消息。  

    中的语句**PollingInput**仅当没有可用于轮询，由数据绑定属性执行**PolledDataAvailableStatement**属性绑定在步骤 2 中。  

5. 适配器客户端必须指定操作中轮询操作**PollingAction**属性绑定。 有关使用适配器服务外接程序使用的操作生成的元数据确定特定操作的轮询操作。  

6. 适配器客户端可以使用**PollWhileDataFound**属性要忽略的轮询间隔，并连续轮询数据，以及可用时绑定。  

   > [!IMPORTANT]
   >  如果设置的值**PollWhileDataFound**绑定属性设为 True，连续轮询适配器客户端数据从 Oracle 或进程中打开和关闭连接到 Oracle 数据库在循环中。 如 ODP.NET 打开连接的速率大于连接处于关闭状态，连接用尽段时间后，并引发异常。 作为替代方案，请确保的值**UseOracleConnectionPool**设置为 True，并适当的值中提及**IncrPoolSize**绑定属性来控制连接数可以通过适配器客户端打开的。  

7. 适配器客户端可以为指定的轮询后语句，Oracle PL/SQL 块中， **PostPollStatement**属性绑定。 在此绑定属性中指定的语句执行后的语句中指定**PollingInput**执行绑定属性。  

   > [!NOTE]
   >  适配器执行的语句中指定**PollingInput**并**PostPollStatement**属性绑定在事务中。 有关中的事务的详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[原理适配器处理事务？](https://msdn.microsoft.com/library/dd788428.aspx)。  

   适配器禁止显示来自 Oracle E-business Suite 的任何空轮询响应。  

   下图提供了有关中的轮询工作流信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 轮询工作流的两种方案是所示：  

8. 时的值**PollWhileDataFound**设置为"False"（默认设置）。  

9. 时的值**PollWhileDataFound**设置为"True。  

   ![轮询方案&#40;PollWhileDataFound&#61;False&#41;](../../adapters-and-accelerators/adapter-oracle-ebs/media/e5f00f4c-cc76-4e8b-9991-b4471f9d4865.gif "e5f00f4c-cc76-4e8b-9991-b4471f9d4865") ![轮询方案&#40;PollWhileDataFound &#61; True&#41; ] (../../adapters-and-accelerators/adapter-oracle-ebs/media/ebecf64c-a770-4525-9c75-62fdb71e1fb1.gif "ebecf64c-a770-4525-9c75-62fdb71e1fb1")  

## <a name="differences-between-polling-and-notification"></a>轮询和通知之间的差异  
 尽管轮询和通知这两个入站操作，并在 Oracle 数据库中的数据更改通知适配器客户端下, 表列出了两者之间的一些差异。 以下差异将帮助你决定具体取决于您的要求操作：  


|                                                                                                                                                                                                                                                      轮询                                                                                                                                                                                                                                                      |                                                                                                                              通知                                                                                                                               |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                   对于所有支持的 Oracle 数据库版本支持轮询[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。                                                                                                                                                                    |                                                                                               特定 Oracle 数据库版本 10.2 和更高版本才支持通知。                                                                                               |
| 你可以配置轮询间隔来检查可用的固定时间间隔轮询的数据或在瞬间完成，以及何时有可用的数据。 **提示：** 轮询可以为您提供更好的吞吐量中情况下，数据更改发生的连续，并且不希望为每个更改的和发生时收到通知。 相反，您指定要在其后的发生是因为最后一个更改通知的所有更改通知的轮询间隔。 |                                                                                                          数据更改通知始终是瞬间完成的。                                                                                                          |
|                                                                                                                                         由适配器启动轮询。 适配器执行 SQL 语句，以验证是否可用于轮询，然后通过执行轮询语句，如果某些数据可用于轮询启动轮询数据。                                                                                                                                         | Oracle 数据库发出通知。 只需在适配器发出的通知语句指示要在没有语句的结果集中的更改的情况下启动通知的数据库。 通知是 Oracle 数据库的一项功能。 |
|                                                                                                                                                                                                                 轮询语句可用于读取或更新 Oracle 数据库中的数据。                                                                                                                                                                                                                  |                                                                                             通知语句可用于只读取 Oracle 数据库中的数据。                                                                                             |
|                                                                                                                                                                                                                            轮询通知您已更改的实际数据。                                                                                                                                                                                                                            |                                                                                   通知只告知如 Insert、 数据更改的类型更新和删除。                                                                                    |

 有关详细信息：  

- 绑定属性与轮询，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  

- 接收基于轮询的消息使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[轮询 Oracle E-business Suite 使用 BizTalk Server 进行](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)。  

## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)