---
title: 开发使用 SAP 适配器的 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
ms.assetid: 4aa10897-a08e-4fc3-9c1f-40485d204273
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 508a1050cde10e8407121036ee6e6f1038b00eb9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373515"
---
# <a name="develop-biztalk-applications-using-the-sap-adapter"></a>开发 BizTalk 应用程序使用 SAP 适配器
开发 BizTalk 应用程序涉及到创建的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成 XML 架构。 后生成架构后，你可以使用基于内容的路由 (CBR)，或创建 BizTalk 业务流程发送和接收符合所生成的架构的消息。  
  
 CBR 可以在发送到 SAP 系统的消息不需要任何密集型处理方案中使用。 例如，如果您知道，将在接收端口接收消息仅特定类型的可以将筛选器添加到要将路由到发送端口筛选器表达式匹配的消息的发送端口。  
  
 BizTalk 业务流程中创建发送和接收端口以发送和接收消息来回[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，后者又将发送到消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 本部分提供有关使用 BizTalk 业务流程执行对 SAP 系统使用的操作信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]又使用[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]可以与 WCF 绑定的适配器。  
  
> [!IMPORTANT]
>  若要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你必须始终设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。 有关如何设置绑定属性的信息，请参阅[配置的 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建 SAP 应用程序的先决条件](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
-   [生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)
  
-   [调用中使用 BizTalk Server 的 SAP Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)  
  
-   [接收来自 SAP 使用 BizTalk Server 的入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)  
  
-   [调用 Trfc SAP 使用 BizTalk Server 中](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)  
  
-   [接收来自 SAP 使用 BizTalk Server 的入站的 tRFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)  
  
-   [在 SAP 中使用 BizTalk Server 运行 BAPI 事务](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)  
  
-   [向使用 BizTalk Server 的 SAP 发送 Idoc](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)  
  
-   [接收来自使用 BizTalk Server 的 SAP 的 Idoc](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)  
  
-   [接收来自事务性上下文中使用 BizTalk Server 中的 SAP 的 Idoc](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)  
  
## <a name="see-also"></a>请参阅  
[开发 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)