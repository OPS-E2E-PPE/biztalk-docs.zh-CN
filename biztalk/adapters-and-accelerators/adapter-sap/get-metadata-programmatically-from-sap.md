---
title: 以编程方式获取元数据从 SAP |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IMetadataRetrievalContract endpoint
- metadata, retrieving programmatically
- WS-Metadata Exchange (MEX) endpoint
ms.assetid: 8d75332e-c103-4bd5-a9a2-56d21747a04e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e03b4ecaee949b3d8fbceeb4929a88b3d5ee004
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373363"
---
# <a name="get-metadata-programmatically-from-sap"></a><span data-ttu-id="4e827-102">从 SAP 以编程方式获取元数据</span><span class="sxs-lookup"><span data-stu-id="4e827-102">Get Metadata Programmatically from SAP</span></span>
<span data-ttu-id="4e827-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是公开为 WCF 服务将 SAP 系统的自定义 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="4e827-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a custom WCF binding that exposes an SAP system as a WCF service.</span></span> <span data-ttu-id="4e827-104">该适配器将 SAP 系统公开为自描述的服务;也就是说，服务能够发布元数据，它支持的操作。</span><span class="sxs-lookup"><span data-stu-id="4e827-104">The adapter exposes the SAP system as a self-describing service; that is, a service that is capable of publishing metadata about the operations that it supports.</span></span> <span data-ttu-id="4e827-105">元数据描述的逻辑接口的 WCF 服务;也就是说，服务协定、 消息和消息架构，必须使用与服务进行交互。</span><span class="sxs-lookup"><span data-stu-id="4e827-105">Metadata describes the logical interface to a WCF service; that is, the service contract, messages, and message schemas that must be used to interact with the service.</span></span>  
  
 <span data-ttu-id="4e827-106">如由工具使用此元数据：</span><span class="sxs-lookup"><span data-stu-id="4e827-106">This metadata is used by tools such as:</span></span>  
  
- <span data-ttu-id="4e827-107">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]来生成服务协定的托管的代码表示形式和</span><span class="sxs-lookup"><span data-stu-id="4e827-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate managed code representations of the service contract, and</span></span>  
  
- <span data-ttu-id="4e827-108">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成消息架构。</span><span class="sxs-lookup"><span data-stu-id="4e827-108">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate message schemas.</span></span>  
  
  <span data-ttu-id="4e827-109">但是，您还可以检索元数据以编程方式从适配器。</span><span class="sxs-lookup"><span data-stu-id="4e827-109">However, you can also retrieve metadata programmatically from the adapter.</span></span> <span data-ttu-id="4e827-110">例如，你可能想要执行此操作以创建要在现有的应用程序中使用的自定义元数据检索工具。</span><span class="sxs-lookup"><span data-stu-id="4e827-110">For example, you might want to do this to create a custom metadata retrieval tool to use in an existing application.</span></span>  
  
  <span data-ttu-id="4e827-111">适配器会发布元数据通过两个终结点：</span><span class="sxs-lookup"><span data-stu-id="4e827-111">The adapter publishes metadata through two endpoints:</span></span>  
  
- <span data-ttu-id="4e827-112">WS-元数据交换 (MEX) 终结点。</span><span class="sxs-lookup"><span data-stu-id="4e827-112">A WS-Metadata Exchange (MEX) endpoint.</span></span> <span data-ttu-id="4e827-113">WCF 自动提供的所有 WCF 绑定的 MEX 终结点。</span><span class="sxs-lookup"><span data-stu-id="4e827-113">WCF automatically provides a MEX endpoint for all WCF bindings.</span></span> <span data-ttu-id="4e827-114">元数据交换可用于检索基础 SAP 系统上的适配器支持的操作的元数据。</span><span class="sxs-lookup"><span data-stu-id="4e827-114">You can use metadata exchange to retrieve metadata for operations supported by the adapter on the underlying SAP system.</span></span>  
  
- <span data-ttu-id="4e827-115">**IMetadataRetrievalContract**终结点。</span><span class="sxs-lookup"><span data-stu-id="4e827-115">An **IMetadataRetrievalContract** endpoint.</span></span> <span data-ttu-id="4e827-116">**IMetadataRetrievalContract**接口由实现[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4e827-116">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="4e827-117">它对多个逻辑级别的 SAP 系统项目进行分类并将其表示为元数据节点的树。</span><span class="sxs-lookup"><span data-stu-id="4e827-117">It categorizes SAP system artifacts at multiple logical levels and presents them as a tree of metadata nodes.</span></span> <span data-ttu-id="4e827-118">可以使用公开的方法**IMetadataRetrievalContract**界面来浏览和搜索此树的节点，并返回你感兴趣的操作的元数据。</span><span class="sxs-lookup"><span data-stu-id="4e827-118">You can use methods exposed by the **IMetadataRetrievalContract** interface to browse and search the nodes of this tree and to return metadata for operations in which you are interested.</span></span>  
  
  <span data-ttu-id="4e827-119">在本部分中的主题介绍如何使用 MEX 和**IMetadataRetrievalContract**终结点，以从适配器以编程方式检索元数据。</span><span class="sxs-lookup"><span data-stu-id="4e827-119">The topics in this section describe how to use MEX and **IMetadataRetrievalContract** endpoints to retrieve metadata programmatically from the adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4e827-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="4e827-120">In This Section</span></span>  
  
-   [<span data-ttu-id="4e827-121">检索元数据在 SAP 中使用 WS-元数据交换</span><span class="sxs-lookup"><span data-stu-id="4e827-121">Retrieving Metadata Using WS-Metadata Exchange in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-using-ws-metadata-exchange-in-sap.md)  
  
-   [<span data-ttu-id="4e827-122">使用 IMetadataRetrievalContract SAP 中检索元数据</span><span class="sxs-lookup"><span data-stu-id="4e827-122">Retrieving Metadata in SAP Using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a><span data-ttu-id="4e827-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e827-123">See Also</span></span>  
[<span data-ttu-id="4e827-124">开发 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="4e827-124">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)