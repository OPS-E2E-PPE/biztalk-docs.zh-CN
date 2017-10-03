---
title: "接收数据库更改通知 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be1eacf1-7fba-4eca-b35b-9770904d9ebd
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cdc28a49b99f4869bf1471c1c05de1c057838fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-database-change-notifications"></a>接收数据库更改通知
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]支持 ODP.NET 数据库更改通知功能。 使用此功能，适配器客户端可以将注册的 SELECT 语句为在数据库中，通知查询并数据库以对适配器客户端及其在结果集的 SELECT 语句更改时发送通知。 在使用 OracleDependency 类适配器中实现数据库更改通知。 有关 ODP.NET 和 OracleDependency 类中的数据库更改支持功能的更多特定于 Oracle 的信息，请转到[http://go.microsoft.com/fwlink/p/?LinkId=124801](http://go.microsoft.com/fwlink/p/?LinkId=124801)。  

## <a name="prerequisites"></a>先决条件  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开的入站的操作，通知，以支持数据库更改通知。 但是，数据库的更改通知用于[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须确保以下：  
  
-   使用的基础的 Oracle 数据库版本 10.2 或更高版本连接到 Oracle E-business Suite。 10.2 之前的 oracle 数据库版本不支持通知。  
  
-   以有权创建通知注册更改通知的用户身份连接到 Oracle E-business Suite。 若要向用户授予更改通知特权，以具有管理权限的用户身份连接到 Oracle 数据库并在 SQL 提示符处运行以下命令：  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   决定 ODP.NET 可以用于接收从 Oracle 数据库的数据库更改通知的 TCP 端口。 将 TCP 端口添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)。 必须提供相同的 TCP 端口号，供**NotificationPort**绑定属性。 有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
 典型的数据库更改通知使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]涉及下列：  
  
1.  适配器客户端必须指定`Notification`中的入站操作作为**InboundOperationType**绑定属性。 正在轮询此绑定属性的默认值。  
  
2.  适配器客户端必须指定 SQL SELECT 语句中的数据库更改通知注册**NotificationStatement**绑定属性。 从 Oracle 数据库作为和的结果集指定的 SQL 语句更改，则适配器客户端获取通知。  
  
3.  适配器客户端必须指定适配器是否在中启动侦听器时，就会立即在向适配器客户端发送了通知**NotifyOnListenerStart**绑定属性。  
  
4.  向作为适配器客户端发送通知，当结果集的 SELECT 语句中指定**NotificationStatement**绑定属性更改。  
  
> [!CAUTION]
>  如果没有在 Oracle 数据库和适配器客户端之间的网络中断，通知将不发送到适配器客户端的网络中断期间对 Oracle 数据库进行的更改并且之后。 因此，你必须使用轮询操作而不是关键方案的通知操作。  
  
## <a name="differences-between-notification-and-polling"></a>通知和轮询之间的差异  
 尽管通知和轮询是这两个入站的操作，Oracle 数据库中的数据更改通知适配器客户端下, 表说明了这两个之间的一些差异。 以下差异将帮助你决定在具体取决于你的要求操作：  
  
|通知|轮询|  
|------------------|-------------|  
|通知是仅支持 Oracle 数据库版本 10.2 及更高版本。|所有支持的 Oracle 数据库版本支持轮询[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。|  
|数据更改通知始终是即时的。|你可以配置的轮询间隔来检查可用于按固定时间间隔轮询数据或即时的方式，以及何时有可用的数据。 **提示：**轮询可以为你提供更佳的吞吐量在数据更改发生连续，并且不希望为每项更改的和发生时要通知的情况下。 作为替代，你指定要在其后的发生是因为最后一个更改通知的所有更改的通知轮询间隔。|  
|Oracle 数据库发出通知。 只需适配器发出的通知语句指示要在该语句结果集中的更改的情况下启动通知的数据库。 通知是 Oracle 数据库的一项功能。|轮询启动的适配器。 适配器执行 SQL 语句以验证是否数据可用于轮询，并随后通过执行轮询语句，如果某些数据可用于轮询开始轮询。|  
|可以使用通知语句仅具有读取 Oracle 数据库中的数据。|轮询语句可用于读取或更新的 Oracle 数据库中的数据。|  
|通知会告知仅如 Insert、 数据中的更改类型的更新和删除。|轮询通知你有关已更改的实际数据信息。|  
  
 有关详细信息：  
  
-   绑定属性与此通知操作，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
-   如何使用中的通知操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[Reaceive 的数据库已由更改通知使用的 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)