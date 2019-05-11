---
title: 接收 Oracle 数据库更改通知 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ffabf27-7223-4473-b33e-af6f2990cb96
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cf6c56df7f72a92c41f4c1d206d4244d67829da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376210"
---
# <a name="receive-oracle-database-change-notifications"></a>接收 Oracle 数据库更改通知
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]支持 ODP.NET 数据库更改通知功能。 使用此功能，适配器客户端可以将注册的 SELECT 语句为通知查询上，对数据库和数据库将通知发送到适配器客户端和结果集的 SELECT 语句更改。 在适配器使用 OracleDependency 类中实现数据库更改通知。 有关 ODP.NET 和 OracleDependency 类中的数据库的更改支持功能的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=124801 ](http://go.microsoft.com/fwlink/?LinkId=124801)。  

 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开的入站的操作，通知，以支持数据库更改通知。 但是，数据库的更改通知，以使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，必须确保以下：  

- 连接到 Oracle 数据库与基础 Oracle 数据库版本 10.2 或更高版本。 10.2 之前的 oracle 数据库版本不支持通知。  

- 以有权创建通知注册更改通知的用户身份连接到 Oracle 数据库。 若要向用户授予更改通知权限，以具有管理权限的用户身份连接到 Oracle 数据库，并在 SQL 提示符处运行以下命令：  

  ```  
  grant change notification to <user name>  
  ```  

- 决定 ODP.NET 可用于从 Oracle 数据库接收数据库更改通知的 TCP 端口。 将 TCP 端口添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959)。 必须提供的同一 TCP 端口号**NotificationPort**属性绑定。 有关绑定属性的详细信息，请参阅[使用的绑定属性](https://msdn.microsoft.com/library/dd788467.aspx)。  

  典型的数据库更改通知使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]涉及以下：  

1.  适配器客户端必须指定`Notification`中的入站操作**InboundOperationType**属性绑定。 轮询此绑定属性的默认值。  

2.  适配器客户端必须指定 SQL SELECT 语句中的数据库更改通知注册**NotificationStatement**属性绑定。 适配器客户端收到一条通知，从 Oracle 数据库作为和的结果集的指定的 SQL 语句更改。  

3.  适配器客户端必须指定适配器是否一旦启动侦听器在向适配器客户端发送了通知**NotifyOnListenerStart**属性绑定。  

4.  通知发送到作为适配器客户端，如果结果集的 SELECT 语句中指定**NotificationStatement**绑定属性发生更改。  

> [!CAUTION]
>  如果没有在 Oracle 数据库和适配器客户端之间的网络中断，通知将不会发送到适配器客户端的网络中断期间对 Oracle 数据库进行的更改，此后。 因此，您必须使用轮询操作而不是关键方案的通知操作。  

## <a name="differences-between-notification-and-polling"></a>通知和轮询之间的差异  
 尽管通知和轮询是这两个入站的操作，并在 Oracle 数据库中的数据更改通知适配器客户端下, 表说明了这两个之间的一些差异。 以下差异将帮助你决定具体取决于您的要求操作：  


|                                                                                                                              通知                                                                                                                               |                                                                                                                                                                                                                                                      轮询                                                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                               通知是仅支持 Oracle 数据库版本 10.2 和更高版本。                                                                                               |                                                                                                                                                                          对于所有支持的 Oracle 数据库版本支持轮询[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。                                                                                                                                                                           |
|                                                                                                          数据更改通知始终是瞬间完成的。                                                                                                          | 你可以配置轮询间隔来检查可用的固定时间间隔轮询的数据或在瞬间完成，以及何时有可用的数据。 **提示：** 轮询可以提供更好的吞吐量中情况下，数据更改发生的连续，并且不希望为每个更改的和发生时收到通知。 相反，您指定要在其后的发生是因为最后一个更改通知的所有更改通知的轮询间隔。 |
| Oracle 数据库发出通知。 只需在适配器发出的通知语句指示要在没有语句的结果集中的更改的情况下启动通知的数据库。 通知是 Oracle 数据库的一项功能。 |                                                                                                                                         由适配器启动轮询。 适配器执行 SQL 语句，以验证是否可用于轮询，然后通过执行轮询语句，如果某些数据可用于轮询启动轮询数据。                                                                                                                                         |
|                                                                                             通知语句可用于只读取 Oracle 数据库中的数据。                                                                                             |                                                                                                                                                                                                                 轮询语句可用于读取或更新 Oracle 数据库中的数据。                                                                                                                                                                                                                  |
|                                                                                   通知只告知如 Insert、 数据更改的类型更新和删除。                                                                                    |                                                                                                                                                                                                                            轮询通知您已更改的实际数据。                                                                                                                                                                                                                            |

 有关详细信息：  

- 绑定属性通知与操作相关的请参阅[使用的绑定属性](https://msdn.microsoft.com/library/dd788467.aspx)。  

- 如何使用中的通知操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[接收 Oracle 数据库更改通知使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)。  

## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)