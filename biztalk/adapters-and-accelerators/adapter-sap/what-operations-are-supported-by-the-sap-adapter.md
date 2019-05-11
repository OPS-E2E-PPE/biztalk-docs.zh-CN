---
title: SAP 适配器支持哪些操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, performing operations
ms.assetid: 4b676336-526d-42b9-9ff2-1a4f27df1a78
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6b42afcdc1c42febe208230307f6d4cd7cbede5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372043"
---
# <a name="what-operations-are-supported-by-the-sap-adapter"></a>SAP 适配器支持哪些操作
适配器客户端可以创建 BizTalk 项目、 使用 WCF 通道模型，或使用 WCF 服务模型执行 SAP 系统的操作。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。 通过通道发送 SOAP 消息来调用这些操作。 如果响应是必需的它通过同一通道返回 SOAP 消息中。 有关消息结构和与每个操作关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。  
  
 本部分提供有关在 SAP 系统使用支持的操作信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在 SAP 中的 Rfc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)  
  
-   [在 SAP 中 Trfc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)  
  
-   [在 SAP 中的 Bapi 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)  
  
-   [在 SAP 中的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)