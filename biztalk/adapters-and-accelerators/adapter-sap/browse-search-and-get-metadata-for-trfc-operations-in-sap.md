---
title: "浏览、 搜索和 SAP 中的 tRFC 操作中获取元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tRFC operations
- tRFC operations, browsing
- searching, tRFC operations
- tRFC operations, searching
- browsing, tRFC operations
ms.assetid: cf4a16d1-7bbf-4dea-b54d-b5315fbcd552
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5124eb4b3a56df70ec55d157ee80a394d6bff83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-metadata-for-trfc-operations-in-sap"></a><span data-ttu-id="04d9b-102">浏览、 搜索和 SAP 中的 tRFC 操作中获取元数据</span><span class="sxs-lookup"><span data-stu-id="04d9b-102">Browse, search, and get metadata for tRFC operations in SAP</span></span>
<span data-ttu-id="04d9b-103">tRFCs 不是一个单独的项目的 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="04d9b-103">tRFCs are not a separate artifact in an SAP system.</span></span> <span data-ttu-id="04d9b-104">这些分为在通过单独的节点下[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]因为其元数据特征是不同的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="04d9b-104">These are categorized under a separate node by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] because their metadata characteristics are different from that of RFCs.</span></span> <span data-ttu-id="04d9b-105">但是的浏览体验，搜索和检索元数据 tRFCs 等同于的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="04d9b-105">However, the experience of browsing, searching, and retrieving metadata for tRFCs is identical to that of the RFCs.</span></span> <span data-ttu-id="04d9b-106">请参阅[浏览、 搜索和 SAP 中的 RFC 操作的 get 元数据](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)有关使用信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]浏览，搜索，并从 SAP 系统中检索 tRFCs 的元数据。</span><span class="sxs-lookup"><span data-stu-id="04d9b-106">Refer to [Browse, search, and get metadata for RFC operations in SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) for information about using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to browse, search, and retrieve metadata for tRFCs from an SAP system.</span></span>  
  
 <span data-ttu-id="04d9b-107">请注意，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现特殊操作**RfcConfirmTransID**下**TRFC**节点。</span><span class="sxs-lookup"><span data-stu-id="04d9b-107">Note that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a special operation **RfcConfirmTransID** under the **TRFC** node.</span></span> <span data-ttu-id="04d9b-108">SAP 适配器使用此操作提交到 SAP 服务器所做的 tRFC 调用。</span><span class="sxs-lookup"><span data-stu-id="04d9b-108">The SAP adapter uses this operation to commit tRFC calls made to the SAP server.</span></span> <span data-ttu-id="04d9b-109">有关此操作的详细信息，请参阅[对 tRFCs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="04d9b-109">For more information about this operation, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d9b-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04d9b-110">See Also</span></span>  
 [<span data-ttu-id="04d9b-111">获取 Visual Studio 中的 SAP 操作的元数据</span><span class="sxs-lookup"><span data-stu-id="04d9b-111">Get Metadata for SAP Operations in Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)