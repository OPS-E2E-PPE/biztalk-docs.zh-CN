---
title: 开发使用 SQL 适配器的 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5471f28e-bce1-4295-b56d-954690e60749
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03920a8ec5d2861bd5c8a19206053e80bb2cdec3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369880"
---
# <a name="develop-biztalk-applications-using-the-sql-adapter"></a>开发使用 SQL 适配器的 BizTalk 应用程序
开发 BizTalk 应用程序涉及到创建的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成 XML 架构。 后生成架构后，你可以使用基于内容的路由 (CBR)，或创建 BizTalk 业务流程发送和接收符合所生成的架构的消息。  
  
 CBR 可以在发送到 SQL Server 的消息不需要任何密集型处理方案中使用。 例如，如果您知道接收端口将收到仅将某些类型的消息，可以将筛选器添加到消息路由到发送端口的筛选器表达式匹配的发送端口。  
  
 BizTalk 业务流程中创建发送和接收端口以发送和接收消息来回[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，后者又将发送到消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 本部分提供有关使用 BizTalk 业务流程使用 SQL Server 上执行操作的信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]又使用[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这可以与 WCF 绑定进行交互。  
  
> [!IMPORTANT]
>  若要使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你必须始终设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。 有关如何设置绑定属性的信息，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建 SQL 应用程序使用 SQL 适配器的先决条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md) 
  
-   [若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md) 
  
-   [Insert、 Update、 Delete 和选择表和视图与 SQL 适配器操作](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)  
  
-   [使用 SQL 适配器的大型数据类型包含运行操作表和视图](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md)  
  
-   [通过使用 BizTalk Server 在 SQL Server 中执行存储的过程](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)  
  
-   [执行与单个 XML 参数的存储的过程](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-with-a-single-xml-parameter-in-sql-using-biztalk.md)  
  
-   [执行存储过程具有 FOR XML 子句中使用 BizTalk server 的 SQL Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)  
  
-   [通过使用 BizTalk Server 运行 SQL Server 上的复合操作](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)  
  
-   [通过使用 BizTalk Server 调用 SQL Server 中的标量函数](../../adapters-and-accelerators/adapter-sql/invoke-scalar-functions-in-sql-server-using-biztalk-server.md)  
  
-   [使用 BizTalk Server 调用 SQL Server 中的表值函数](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md) 
  
-   [通过使用 BizTalk Server 执行 ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)  
  
-   [通过使用 SQL 适配器与 BizTalk Server 轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)  
  
-   [通过使用 BizTalk Server 接收 SQL 查询通知](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)  
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)