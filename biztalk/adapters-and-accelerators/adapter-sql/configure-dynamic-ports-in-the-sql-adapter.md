---
title: 在 SQL 适配器中配置动态端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c98b66ed-0bf7-4b24-9d16-9792d033b818
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bb1417280706399728f7bfd59bc4c5ee7a7cc76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222189"
---
# <a name="configure-dynamic-ports-in-the-sql-adapter"></a>在 SQL 适配器中配置动态端口
在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你可以配置为动态端口[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]。 因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是一个基于 WCF 的适配器，你可以动态配置的端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过使用消息上下文属性。  

## <a name="use-an-expression-shape"></a>使用表达式形状  
 有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，URI、 操作和绑定可能确定传入消息时，属性，然后中指定**表达式**形状，如下面的示例中所示：  
  
```  
Request2=Request1;  
Request2(WCF.Action)="TableOp/Insert/dbo/CustomerTable";  
Request2(WCF.BindingType)="sqlBinding";  
Request2(WCF.UserName)="myuser";  
Request2(WCF.Password)="mypass";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="mssql://sql_server/my_instance/my_database";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  如果使用中的 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你还可以指定的传输类型为`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SQLAdapter"`，其中**SQLAdapter**是与其添加中的 WCF SQL 适配器的名称[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 在前面的示例中，  
  
-   正在从 Request1 消息创建次数 2 消息。 这两个消息映射到操作的架构，这在生成使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
-   发送端口是 BizTalk 业务流程中的逻辑发送端口的名称。  
  
 **表达式**形状是 BizTalk 业务流程的一部分。 部署业务流程还会创建 WCF 自定义发送端口。  
  
 有关配置动态端口的详细信息，请参阅[配置动态发送端口使用 WCF 适配器上下文属性](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)。
  
## <a name="see-also"></a>另请参阅  
[开发具有 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)