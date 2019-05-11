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
# <a name="what-operations-are-supported-by-the-sap-adapter"></a><span data-ttu-id="893cc-102">SAP 适配器支持哪些操作</span><span class="sxs-lookup"><span data-stu-id="893cc-102">What operations are supported by the SAP adapter</span></span>
<span data-ttu-id="893cc-103">适配器客户端可以创建 BizTalk 项目、 使用 WCF 通道模型，或使用 WCF 服务模型执行 SAP 系统的操作。</span><span class="sxs-lookup"><span data-stu-id="893cc-103">Adapter clients can perform operations on the SAP system by creating BizTalk projects, by using the WCF channel model, or by using the WCF service model.</span></span> <span data-ttu-id="893cc-104">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。</span><span class="sxs-lookup"><span data-stu-id="893cc-104">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="893cc-105">通过通道发送 SOAP 消息来调用这些操作。</span><span class="sxs-lookup"><span data-stu-id="893cc-105">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="893cc-106">如果响应是必需的它通过同一通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="893cc-106">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="893cc-107">有关消息结构和与每个操作关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="893cc-107">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>  
  
 <span data-ttu-id="893cc-108">本部分提供有关在 SAP 系统使用支持的操作信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="893cc-108">This section provides information about the operations supported on the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="893cc-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="893cc-109">In This Section</span></span>  
  
-   [<span data-ttu-id="893cc-110">在 SAP 中的 Rfc 的操作</span><span class="sxs-lookup"><span data-stu-id="893cc-110">Operations on RFCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)  
  
-   [<span data-ttu-id="893cc-111">在 SAP 中 Trfc 的操作</span><span class="sxs-lookup"><span data-stu-id="893cc-111">Operations on tRFCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)  
  
-   [<span data-ttu-id="893cc-112">在 SAP 中的 Bapi 的操作</span><span class="sxs-lookup"><span data-stu-id="893cc-112">Operations on BAPIs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)  
  
-   [<span data-ttu-id="893cc-113">在 SAP 中的 Idoc 的操作</span><span class="sxs-lookup"><span data-stu-id="893cc-113">Operations on IDOCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)