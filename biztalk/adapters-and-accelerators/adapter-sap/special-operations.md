---
title: 特殊操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, special operations surfaced by the SAP adapter
ms.assetid: 8725fe63-6ff4-49c8-b386-d4c67e2be440
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe2472d905e9e726b827d44da79bdfe840233354
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="special-operations"></a>特殊的操作
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现几个特殊操作。 这些操作不基于 SAP 系统项目的影响。 它们将显示为适配器客户端应用程序提供功能。 进行的特殊操作：  
  
-   **RfcGetAttributes**。 此操作在 RFC 节点下显示，并公开的 RFC sdk 的功能。 它提供有关 RFC 连接的以下信息：  
  
    -   系统 ID  
  
    -   合作伙伴代码页  
  
    -   语言  
  
     有关包括其消息架构 RfcGetAttributes 操作的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。  
  
-   **RfcConfirmTransID**。 此操作在 TRFC 节点下显示，并公开 RFC SDK 功能。 你可以使用此操作以确认 SAP 系统上的 SAP 事务 Id。  
  
     有关如何使用 RfcConfirmTransID 操作和有关其消息架构，请参阅详细信息[对 tRFCs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。  
  
-   **字符串 SapAdapterUtilities.ConvertGuidToTid(Guid)**。 这是由 SAP 适配器程序集公开的公共方法。 （不是适配器中加以表示的操作。）它将返回 SAP 事务 ID (TID) 映射到指定的 GUID。  
  
     在内部，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]映射为 GUID SAP 系统上的 SAP 事务 ID (TID) 标识的工作 (LUW) 逻辑单元。 此 GUID 是向适配器客户端公开，以便他们可以承诺 tRFC (LUW) 通过调用 RfcConfirmTransID 操作，以确认其 TID SAP 系统上。  
  
     但是，在某些情况下，你可能需要与 tRFC 关联 TID。 例如，你可能想要确定 SAP 系统上的 LUW，以解决问题。 对于这些情况你可以调用**ConvertGuidToTid**。 若要使用**ConvertGuidToTid**在代码中，你必须将 SAP 适配器程序集的引用添加到你的项目。  
  
     有关调用 tRFCs 的详细信息，请参阅[对 tRFCs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。 下面的示例演示如何调用**ConvertGuidToTid**。  
  
    ```  
    // messageGuid is the GUID associated with a tRFC or IDOC  
  
    string tid = SapAdapterUtilities.ConvertGuidToTid(messageGuid);  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 mySAP Business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)