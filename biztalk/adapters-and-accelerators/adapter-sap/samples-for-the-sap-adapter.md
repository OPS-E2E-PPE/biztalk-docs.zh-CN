---
title: SAP 适配器示例 |Microsoft Docs
description: 可用于 BizTalk Server、 WCF 服务模型、 WCF 通道模型和数据访问接口与 SAP mySAP WCF 适配器示例
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
ms.openlocfilehash: c1926c9899d1c1198998c25845d5d6b4189884f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012062"
---
# <a name="samples-for-the-sap-adapter"></a>SAP 适配器的示例
示例[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]分为：  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 示例  

- WCF 服务模型示例  

- WCF 通道模型示例  

- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 示例  


 这些示例目前[BizTalk 适配器包 2010年: SAP 适配器示例](https://www.microsoft.com/download/details.aspx?id=1314)。 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]

 以下列表说明的示例。

## <a name="biztalk-server-samples"></a>BizTalk Server 示例  

|示例目录名称|Description|  
|---------------------------|-----------------|  
|IDOCSend|演示如何将 IDOC 发送到 SAP 系统。|  
|ReceiveIDOC|演示如何从 SAP 系统接收 IDOC。|  
|ReceiveIDOC_SYSREL|演示如何从 SAP 系统接收 IDOC。 所收到的 IDOC 的版本数小于 SAP SYSREL。|  
|RFCServer|演示如何从 SAP 系统接收 RFC 服务器调用。|  
|SAPTransaction|演示如何执行事务中 SAP 系统使用。|  
|tRFCClient|演示如何调用 tRFC 客户端上的 SAP 系统。|  

## <a name="wcf-service-model-samples"></a>WCF 服务模型示例   

|示例目录名称|Description|  
|---------------------------|-----------------|  
|SapIdocStringClientSM|演示如何将 IDOC 发送到 SAP 系统，通过调用 SendIdoc 操作。|  
|SapRfcServerSM|演示如何从 SAP 系统接收 RFC 服务器调用。|  
|SapBapiTxClientSM|演示如何将 SAP 系统上的事务内调用 Bapi。|  
|SapTrfcClientSM|演示如何调用 tRFC 客户端上的 SAP 系统。|  

## <a name="wcf-channel-model-samples"></a>WCF 通道模型示例  

|示例目录名称|Description|  
|---------------------------|-----------------|  
|SapIdocReceiveCM|演示如何从 SAP 系统接收 Idoc|  
|SapRfcServerCM|演示如何从 SAP 系统接收 RFC 服务器调用。|  

## <a name="data-provider-for-sap-samples"></a>用于 SAP 示例数据提供程序  

| 示例目录名称 |                                             Description                                              |
|-----------------------|------------------------------------------------------------------------------------------------------|
|        sap ado        | 演示如何使用[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。 |

## <a name="see-also"></a>请参阅  
[开发 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)