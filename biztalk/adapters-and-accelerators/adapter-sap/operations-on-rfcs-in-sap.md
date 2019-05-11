---
title: 在 SAP 中的 Rfc 的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, operations on RFCs
- adapters, operations on IDOCs
- RFC, receiving inbound RFC calls from an SAP system
- RFCs, invoking RFCs on an SAP system
- adapters, operations on BAPIs
- RFC client
- adapters, operations on tRFCs
- RFC server
ms.assetid: ca1b7b00-a9cf-41bc-b87c-2e7ce8cff65c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5370ec67511088b070568218320e0d015cfd25f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373169"
---
# <a name="operations-on-rfcs-in-sap"></a>在 SAP 中的 Rfc 的操作
可以使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]作为 RFC 客户端和 RFC 服务器。 在 RFC 客户端方案中，你的应用程序调用 Rfc SAP 系统上通过在调用 RFC 操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 在 RFC 服务器方案中将 SAP 系统调用 Rfc 上[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，其中，反过来，以在应用程序上操作的方式调用 RFC。  
  
## <a name="rfc-operations"></a>RFC 操作  
 Rfc 按名称显示为通过的 RFC 的元数据类别节点下的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 (您可以浏览或搜索在 Rfc **RFC**当你使用的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。)  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ，可能会出现，它可以从 SAP 系统中检索元数据这些 Rfc。 适配器使用 RFC SDK 来检索此元数据，因此它不能呈现包含 RFC SDK 不支持的数据类型的参数的 Rfc。 例如，适配器不能出现包含 ITAB II 类型结构或表的 Rfc。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Rfc 上支持以下各项：  
  
- 导入参数  
  
- 导出参数  
  
- 更改参数  
  
  有关消息结构和适配器为 Rfc 使用的 SOAP 操作的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。  
  
## <a name="invoking-rfcs-on-an-sap-system"></a>SAP 系统上调用 Rfc  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Rfc 显示为单独的操作，SAP 系统上采用 RFC 的名称。 若要调用 RFC SAP 系统上的，您调用在适配器上适当命名的 RFC 操作。  
  
 有关详细信息：  
  
-   调用 RFC 使用 BizTalk Server 中，请参阅[通过使用 BizTalk Server 调用 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)。  
  
-   调用 RFC 使用 WCF 服务模型，请参阅[调用中使用 WCF 服务模型的 SAP 的 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)。  
  
-   调用 RFC 使用 WCF 通道模型，请参阅[通过使用 WCF 通道模型 SAP 系统的调用操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)。  
  
## <a name="receiving-inbound-rfc-calls-from-an-sap-system"></a>接收来自 SAP 系统的入站的 RFC 调用  
 很可能适用于 SAP 充当客户端并调用外部 RFC 服务器上的函数模块。 此功能可以：  
  
- 若要将通知推送到外部系统，而无需外部系统无需通知通过调用 Rfc 连续轮询 SAP 的 SAP。  
  
- SAP 系统外部的业务逻辑的实现。 然后，SAP 系统可以对 RFC 服务器调用外部程序。  
  
  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以充当一个 RFC 服务器用于从 SAP 系统接收此类的入站的 RFC 调用。 当适配器接收来自 SAP RFC 调用时，它调用 RFC 操作对应用程序。  
  
  为使适配器为 RFC 服务器执行：  
  
- RFC 必须声明上的 SAP 系统。 这是因此适配器可以检索描述从 SAP 系统的 RFC 的元数据。 在你的应用程序中实际实现 RFC。  
  
- 适配器必须注册 SAP 网关上的 RFC 目标。 注册基于逻辑名称称为程序 id。 提供的连接 URI 指定的程序 ID，SAP 网关和 SAP 此注册的服务器中的参数。  
  
  下面的示例显示了调用通过程序 ID，MYDEST RFC 所需的 ABAP 代码。  
  
```  
CALL FUNCTION ‘ABC’ DESTINATION ‘MYDEST’  
```  
  
 有关详细信息：  
  
-   接收 RFC 服务器调用使用 BizTalk Server 中，请参阅[通过使用 BizTalk Server 接收的入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)。  
  
-   接收 RFC 服务器调用使用 WCF 服务模型，请参阅[SAP 使用 WCF 服务模型中接收的入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)。  
  
-   接收 RFC 服务器调用使用 WCF 通道模型，请参阅[接收从使用 WCF 通道模型 SAP 系统的入站操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)。  
  
## <a name="special-rfc-operations"></a>特殊 RFC 操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还可以执行某些特殊的 RFC 操作上的 SAP 系统。 一个此类操作，RfcGetAttributes。  
  
- **RfcGetAttributes**。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]此操作用于获取有关 RFC 连接参数，例如系统 ID、 合作伙伴的代码页和语言的信息。 此操作不可用的情况下**RFC**节点时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
  有关消息结构和 SOAP 操作的调用上的 SAP 系统的某个 RfcGetAttributes 操作的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)