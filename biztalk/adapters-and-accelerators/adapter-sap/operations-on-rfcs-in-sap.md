---
title: SAP 中的 Rfc 上的操作 |Microsoft 文档
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
ms.openlocfilehash: cd4ebbb33e9f9791589a3ef271412c8ae20090f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217061"
---
# <a name="operations-on-rfcs-in-sap"></a>SAP 中的 Rfc 上的操作
你可以使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]同时作为 RFC 客户端和 RFC 服务器。 在 RFC 客户端的情况下，你的应用程序时，将调用 Rfc SAP 系统上通过上调用 RFC 操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 在 RFC 服务器方案中 SAP 系统时，将调用 Rfc 上[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，这样，就反过来，作为对你的应用程序的操作可调用 RFC。  
  
## <a name="rfc-operations"></a>RFC 操作  
 Rfc 作为 RFC 元数据类别节点下的操作进行展示按名称[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 (你可以浏览或搜索在 Rfc **RFC**节点使用时[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。)  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可能显示为其它能够从 SAP 系统中检索元数据这些 Rfc。 适配器使用 RFC SDK 检索此元数据，因此它不能呈现包含 RFC SDK 不支持的数据类型的参数的 Rfc。 例如，该适配器不能出现包含 ITAB II 类型结构或表的 Rfc。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在 Rfc 上支持以下：  
  
-   导入参数  
  
-   导出参数  
  
-   更改参数  
  
 有关消息结构和用于 Rfc 适配器的 SOAP 操作的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。  
  
## <a name="invoking-rfcs-on-an-sap-system"></a>调用上的 SAP 系统的 Rfc  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]显示为 SAP 系统对其执行的 RFC 名称的各个操作的 Rfc。 若要调用 RFC SAP 系统上的，你调用该适配器上的相应命名的 RFC 操作。  
  
 有关详细信息：  
  
-   调用 RFC 使用 BizTalk Server 中，请参阅[使用 BizTalk server 调用 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)。  
  
-   调用 RFC 使用 WCF 服务模型时，请参阅[调用中使用 WCF 服务模型的 SAP 的 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)。  
  
-   调用 RFC 使用 WCF 通道模型，请参阅[调用通过使用 WCF 通道模型 SAP 系统的操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)。  
  
## <a name="receiving-inbound-rfc-calls-from-an-sap-system"></a>从 SAP 系统的接收入站的 RFC 调用  
 很可能适用于 SAP 充当客户端并调用外部 RFC 服务器上的函数模块。 借助此功能：  
  
-   SAP 以将通知推送到外部系统，而无需外部的系统无需持续轮询 SAP 通知通过调用 Rfc。  
  
-   在 SAP 系统范围之外的业务逻辑的实现。 然后，SAP 系统可以在 RFC 服务器上调用外部程序。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以用作 RFC 服务器从 SAP 系统接收此类的入站的 RFC 调用。 当适配器在 SAP 中收到的 RFC 调用时，将调用该 RFC 操作对应用程序。  
  
 作为 RFC 服务器运行的适配器：  
  
-   RFC 必须声明 SAP 系统上。 这是因此该适配器可以检索元数据描述从 SAP 系统的 RFC。 RFC 实际是在你的应用程序中实现的。  
  
-   适配器必须注册上的 SAP 网关的 RFC 目标。 注册基于逻辑名称称为程序 id。 提供连接 URI 指定的程序 ID，SAP 网关和 SAP 此注册的服务器中的参数。  
  
 下面的示例显示调用通过程序 ID，MYDEST RFC 所必需的 ABAP 代码。  
  
```  
CALL FUNCTION ‘ABC’ DESTINATION ‘MYDEST’  
```  
  
 有关详细信息：  
  
-   接收的 RFC 服务器调用使用 BizTalk Server 中，请参阅[使用 BizTalk server 接收入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)。  
  
-   接收的 RFC 服务器调用使用 WCF 服务模型时，请参阅[SAP 使用 WCF 服务模型中接收入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)。  
  
-   接收的 RFC 服务器调用使用 WCF 通道模型，请参阅[接收从使用 WCF 通道模型 SAP 系统的入站操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)。  
  
## <a name="special-rfc-operations"></a>特殊 RFC 操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还可以执行某些特殊的 RFC 操作 SAP 系统上。 此类的一个操作是 RfcGetAttributes。  
  
-   **RfcGetAttributes**。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用此操作以获取有关 RFC 连接参数，如系统 ID、 合作伙伴代码页和语言的信息。 此操作才可用下**RFC**节点时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
 有关消息结构和调用对 SAP 系统的 RfcGetAttributes 操作的 SOAP 操作的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)