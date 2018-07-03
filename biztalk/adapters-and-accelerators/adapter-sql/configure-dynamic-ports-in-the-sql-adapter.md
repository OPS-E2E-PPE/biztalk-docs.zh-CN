---
title: 在 SQL 适配器配置动态端口 |Microsoft Docs
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
ms.openlocfilehash: c23bce67dbc4eaca8441e6e7d07573724225cc45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976230"
---
# <a name="configure-dynamic-ports-in-the-sql-adapter"></a>在 SQL 适配器配置动态端口
在中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，可以配置有关的动态端口[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]。 因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是基于 WCF 的适配器，您可以动态地配置的端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过使用消息上下文属性。  

## <a name="use-an-expression-shape"></a>使用表达式形状  
 有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，可能会确定传入消息上的属性，然后中指定 URI、 操作和绑定**表达式**形状，如下面的示例中所示：  
  
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
>  使用中的 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您还可以指定的传输类型为`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SQLAdapter"`，其中**SQLAdapter**是添加中的 WCF SQL 适配器的名称[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 在前面的示例中，  
  
- 正在从 Request1 消息创建请求 2 消息。 这两个消息映射到操作架构，这在生成使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
- 发送端口是 BizTalk 业务流程中的逻辑发送端口的名称。  
  
  **表达式**形状是 BizTalk 业务流程的一部分。 部署业务流程还会创建 Wcf-custom 发送端口。  
  
  有关配置动态端口的详细信息，请参阅[配置动态发送端口使用 WCF 适配器上下文属性](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)。
  
## <a name="see-also"></a>请参阅  
[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)