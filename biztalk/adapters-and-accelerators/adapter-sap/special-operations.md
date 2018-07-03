---
title: 特殊操作 |Microsoft Docs
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
ms.openlocfilehash: 2bada45064e588748b25947e08b104dc79838ee0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975982"
---
# <a name="special-operations"></a>特殊操作
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]显示多个特殊操作。 这些操作不基于 SAP 系统项目。 它们会显示为适配器客户端应用程序提供的功能。 特殊的操作包括：  
  
- **RfcGetAttributes**。 此操作在 RFC 节点下显示，并公开 RFC SDK 的功能。 它提供了有关 RFC 连接的以下信息：  
  
  - 系统 ID  
  
  - 合作伙伴代码页  
  
  - 语言  
  
    有关包括其消息架构 RfcGetAttributes 操作的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。  
  
- **RfcConfirmTransID**。 此操作 TRFC 节点下显示，并公开 RFC SDK 功能。 使用此操作以确认 SAP 系统上的 SAP 事务 Id。  
  
   详细了解如何使用 RfcConfirmTransID 操作和有关其消息架构，请参阅[Trfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。  
  
- **字符串 SapAdapterUtilities.ConvertGuidToTid(Guid)**。 这是 SAP 适配器程序集公开的公共方法。 （不是由适配器的操作。）它将返回 SAP 事务 ID (TID) 映射到指定的 GUID。  
  
   在内部，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]映射到 GUID 在 SAP 系统上的 SAP 事务 ID (TID)，用于标识工作 (LUW) 的逻辑单元。 此 GUID 是向适配器客户端公开，以便它们可以提交一个 tRFC (LUW) 通过调用 RfcConfirmTransID 操作以确认其 TID SAP 系统上。  
  
   但是，对于某些情况下，可能需要与 tRFC TID。 例如，你可能想要识别 LUW 上的 SAP 系统以解决问题。 对于这种情况，您可以调用**ConvertGuidToTid**。 若要使用**ConvertGuidToTid**在代码中，必须将 SAP 适配器程序集的引用添加到你的项目。  
  
   调用 Trfc 的详细信息，请参阅[Trfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。 下面的示例演示如何调用**ConvertGuidToTid**。  
  
  ```  
  // messageGuid is the GUID associated with a tRFC or IDOC  
  
  string tid = SapAdapterUtilities.ConvertGuidToTid(messageGuid);  
  ```  
  
## <a name="see-also"></a>请参阅  
 [消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)