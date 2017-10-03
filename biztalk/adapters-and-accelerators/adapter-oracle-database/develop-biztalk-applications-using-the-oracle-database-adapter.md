---
title: "开发使用 Oracle 数据库适配器的 BizTalk 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Content-Based Routing (CBR)
- BizTalk orchestrations, using orchestrations to perform operations
ms.assetid: 65689c83-4a57-4aad-b0e9-f1bad901a7b9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa1b3f688987c0c8339a2fd81c1b1ddf67128818
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-oracle-database-adapter"></a>开发使用 Oracle 数据库适配器的 BizTalk 应用程序
开发 BizTalk 应用程序涉及到创建中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成 XML 架构。 一旦你已生成架构，你可以使用基于内容的路由 (CBR)，或创建 BizTalk 业务流程，以发送和接收符合生成架构的消息。  
  
 CBR 可以用于的方案发送到 Oracle 数据库的消息不需要任何密集型处理。 例如，如果你知道接收端口将接收仅特定类型的消息，可以将筛选器添加到要将路由到发送端口筛选器表达式匹配的消息的发送端口中。  
  
 在 BizTalk 业务流程中创建发送和接收端口发送和接收消息，并从[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这反过来将消息发送到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 本部分提供有关使用 BizTalk 业务流程执行对 Oracle 数据库使用的操作的信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]反过来使用[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这可以与的 WCF 绑定进行交互。  
  
> [!IMPORTANT]
>  若要使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，始终必须设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。 有关如何设置绑定属性的说明，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。  
  
> [!IMPORTANT]
>  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理控制台中未列出。 中的适配器[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]是基于 WCF 的并使用 WCF 的自定义绑定。 BizTalk Server 管理控制台显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]。 它不会自动显示 WCF 自定义绑定，并因此不会显示基于 WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
> 
> 此外，若要生成元数据，请使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。 不要使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 有关使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请参阅[为 Visual Studio 中的 Oracle 数据库操作获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)。 
> 
> 有关其他适配器版本之间的差异，请参阅[迁移 BizTalk 项目创建使用 Oracle 数据库的 BizTalk ODBC 适配器](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)。  
  
  
  
## <a name="see-also"></a>另请参阅  
[开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)