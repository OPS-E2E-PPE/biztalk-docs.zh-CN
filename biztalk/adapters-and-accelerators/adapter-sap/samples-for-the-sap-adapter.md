---
title: "SAP 适配器的示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- samples, Data Provider for SAP
- samples, migration
- samples, BizTalk
- samples, WCF service model
- samples, WCF channel model
- samples
ms.assetid: 4654c458-83be-417f-ae54-5c3a8f6ab81f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0374aada037282a68e7575136b8671bba5ca181d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="samples-for-the-sap-adapter"></a>SAP 适配器的示例
示例[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]分为：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 示例  
  
-   WCF 服务模型示例  
  
-   WCF 通道模型示例  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 示例  
  
-   迁移示例  
  
 这些示例位于[http://go.microsoft.com/fwlink/?LinkID=196854](http://go.microsoft.com/fwlink/?LinkID=196854)。  
  
 以下列表包含的名称和描述的示例[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="biztalk-server-samples"></a>BizTalk Server 示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|IDOCSend|演示如何将 IDOC 发送到 SAP 系统。|  
|ReceiveIDOC|演示如何从某个 SAP 系统接收 IDOC。|  
|ReceiveIDOC_SYSREL|演示如何从某个 SAP 系统接收 IDOC。 所收到的 IDOC 的版本号小于 SAP SYSREL。|  
|RFCServer|演示如何从 SAP 系统接收的 RFC 服务器调用。|  
|SAPTransaction|演示如何在 SAP 系统使用中执行事务。|  
|tRFCClient|演示如何在 SAP 系统上进行 tRFC 客户端调用。|  
  
## <a name="wcf-service-model-samples"></a>WCF 服务模型示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|SapIdocStringClientSM|演示如何将 IDOC 发送到 SAP 系统，通过调用 SendIdoc 操作。|  
|SapRfcServerSM|演示如何从某个 SAP 系统接收的 RFC 服务器调用。|  
|SapBapiTxClientSM|演示如何在 SAP 系统上事务内调用 BAPIs。|  
|SapTrfcClientSM|演示如何调用 tRFC SAP 系统上的客户端调用。|  
  
## <a name="wcf-channel-model-samples"></a>WCF 通道模型示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|SapIdocReceiveCM|演示如何从某个 SAP 系统接收到的 Idoc|  
|SapRfcServerCM|演示如何从 SAP 系统接收的 RFC 服务器调用。|  
  
## <a name="data-provider-for-sap-samples"></a>用于 SAP 示例数据提供程序  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|sap ado|演示如何使用[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。|  
  
## <a name="migration-samples"></a>迁移示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|SAP_RFC_Migration|演示如何使用使用以前版本的 SAP 适配器创建的 BizTalk 项目并使其适用于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 BizTalk 项目包含要调用 SD_RFC_CUSTOMER_GET RFC 业务流程。|  
|SendIDOC_Migration|演示如何使用使用以前版本的 SAP 适配器创建的 BizTalk 项目并使其适用于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 BizTalk 项目包含业务流程以将 IDOC 发送到 SAP 系统。|  
|ReceiveIDOC_Migration|演示如何使用使用以前版本的 SAP 适配器创建的 BizTalk 项目并使其适用于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 BizTalk 项目包含要调用接收从 SAP 系统的 IDOC 的业务流程。|  
  
## <a name="see-also"></a>另请参阅  
[开发您的 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)