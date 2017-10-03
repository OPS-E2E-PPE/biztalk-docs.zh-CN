---
title: "SAP 适配器中的 SAPClientFactory 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPClientFactory, supported methods and classes
ms.assetid: e64de5e4-e53f-4708-ab02-9e12774e94cd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c82e4bea6a16085608ebf1f8fe10ea95b4db394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sapclientfactory-class-in-the-sap-adapter"></a>SAP 适配器中 SAPClientFactory 类
以下部分列出的方法和属性**SAPClientFactory**类。 该项派生自**System.Data.Common.DbProviderFactory**。  
  
## <a name="supported-properties"></a>受支持的属性  
  
|Name|Get/Set|Description|  
|----------|--------------|-----------------|  
|**实例**|-|SAPClientFactory 单一实例|  
  
## <a name="supported-methods"></a>支持的方法  
  
|Name|Description|  
|----------|-----------------|  
|**CreateCommand()**|创建 SAPCommand 的实例|  
|**CreateConnection()**|创建 SAPConnection 的实例|  
|**CreateConnectionStringBuilder()**|创建 SAPConnectionStringBuilder 的实例|  
|**CreateParameter()**|创建 SAPParameter 的实例|  
  
## <a name="see-also"></a>另请参阅  
 [使用 SAP 适配器扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)