---
title: SAP 适配器示例 |Microsoft 文档
description: 为 SAP 使用 BizTalk Server、 WCF 服务模型，WCF 通道模型和数据提供程序使用的 mySAP WCF 适配器示例
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4654c458-83be-417f-ae54-5c3a8f6ab81f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d163c573003f40b2049f7e921e5edc4997b4e115
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014916"
---
# <a name="samples-for-the-sap-adapter"></a>SAP 适配器的示例
示例[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]分为：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 示例  
  
-   WCF 服务模型示例  
  
-   WCF 通道模型示例  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 示例  

  
 这些示例位于[BizTalk 适配器包 2010年: SAP 适配器示例](https://www.microsoft.com/download/details.aspx?id=1314)。 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
 以下列表介绍这些示例。
  
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
  
 
## <a name="see-also"></a>另请参阅  
[开发 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)