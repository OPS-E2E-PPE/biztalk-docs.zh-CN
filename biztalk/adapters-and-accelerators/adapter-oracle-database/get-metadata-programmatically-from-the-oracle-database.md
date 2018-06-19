---
title: 从 Oracle 数据库以编程方式获取元数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving programmatically from the Oracle database
ms.assetid: 28a55935-6078-41d0-abfa-ac86e9ca8471
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c36fcd6a791f1d960a4dd4dfd78ca199d2e49cb5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214269"
---
# <a name="get-metadata-programmatically-from-the-oracle-database"></a><span data-ttu-id="93feb-102">从 Oracle 数据库以编程方式获取元数据</span><span class="sxs-lookup"><span data-stu-id="93feb-102">Get Metadata Programmatically from the Oracle Database</span></span>
<span data-ttu-id="93feb-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]是公开作为 WCF 服务的 Oracle 数据库的自定义 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="93feb-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] is a custom WCF binding that exposes an Oracle database as a WCF service.</span></span> <span data-ttu-id="93feb-104">适配器将作为自描述服务; 公开 Oracle 数据库即，它能够发布元数据，它支持的操作有关的服务。</span><span class="sxs-lookup"><span data-stu-id="93feb-104">The adapter exposes the Oracle database as a self-describing service; that is, a service that is capable of publishing metadata about the operations that it supports.</span></span> <span data-ttu-id="93feb-105">元数据描述 WCF 服务; 的逻辑接口即，服务协定、 消息和消息架构，必须用于与服务交互。</span><span class="sxs-lookup"><span data-stu-id="93feb-105">Metadata describes the logical interface to a WCF service; that is, the service contract, messages, and message schemas that must be used to interact with the service.</span></span>  
  
 <span data-ttu-id="93feb-106">此元数据是由工具中使用，如：</span><span class="sxs-lookup"><span data-stu-id="93feb-106">This metadata is used by tools such as:</span></span>  
  
-   <span data-ttu-id="93feb-107">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成的服务协定中，托管的代码表示形式和</span><span class="sxs-lookup"><span data-stu-id="93feb-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate managed code representations of the service contract, and</span></span>  
  
-   <span data-ttu-id="93feb-108">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成消息架构。</span><span class="sxs-lookup"><span data-stu-id="93feb-108">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate message schemas.</span></span>  
  
 <span data-ttu-id="93feb-109">但是，你还可以检索元数据以编程方式从适配器。</span><span class="sxs-lookup"><span data-stu-id="93feb-109">However, you can also retrieve metadata programmatically from the adapter.</span></span> <span data-ttu-id="93feb-110">例如，你可能想要执行此操作可创建要在现有应用程序中使用一个自定义元数据检索工具。</span><span class="sxs-lookup"><span data-stu-id="93feb-110">For example, you might want to do this to create a custom metadata retrieval tool to use in an existing application.</span></span>  
  
 <span data-ttu-id="93feb-111">适配器发布元数据通过两个终结点：</span><span class="sxs-lookup"><span data-stu-id="93feb-111">The adapter publishes metadata through two endpoints:</span></span>  
  
-   <span data-ttu-id="93feb-112">WS 元数据交换 (MEX) 终结点。</span><span class="sxs-lookup"><span data-stu-id="93feb-112">A WS-Metadata Exchange (MEX) endpoint.</span></span> <span data-ttu-id="93feb-113">WCF 自动提供的所有 WCF 绑定的 MEX 终结点。</span><span class="sxs-lookup"><span data-stu-id="93feb-113">WCF automatically provides a MEX endpoint for all WCF bindings.</span></span> <span data-ttu-id="93feb-114">可以使用元数据交换来检索元数据为基础的 Oracle 数据库适配器支持的操作。</span><span class="sxs-lookup"><span data-stu-id="93feb-114">You can use metadata exchange to retrieve metadata for operations supported by the adapter on the underlying Oracle database.</span></span>  
  
-   <span data-ttu-id="93feb-115">**IMetadataRetrievalContract**终结点。</span><span class="sxs-lookup"><span data-stu-id="93feb-115">An **IMetadataRetrievalContract** endpoint.</span></span> <span data-ttu-id="93feb-116">**IMetadataRetrievalContract**接口由实现[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="93feb-116">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="93feb-117">它分类多个逻辑级别的 Oracle 数据库项目，并使它们表现为元数据节点树。</span><span class="sxs-lookup"><span data-stu-id="93feb-117">It categorizes Oracle database artifacts at multiple logical levels and presents them as a tree of metadata nodes.</span></span> <span data-ttu-id="93feb-118">你可以使用公开的方法**IMetadataRetrievalContract**界面，用于浏览和搜索此树的节点和以返回你感兴趣的操作的元数据。</span><span class="sxs-lookup"><span data-stu-id="93feb-118">You can use methods exposed by the **IMetadataRetrievalContract** interface to browse and search the nodes of this tree and to return metadata for operations in which you are interested.</span></span>  
  
 <span data-ttu-id="93feb-119">本部分中的主题介绍如何使用 MEX 和**IMetadataRetrievalContract**要从适配器以编程方式检索元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="93feb-119">The topics in this section describe how to use MEX and **IMetadataRetrievalContract** endpoints to retrieve metadata programmatically from the adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93feb-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="93feb-120">In This Section</span></span>  
  
-   [<span data-ttu-id="93feb-121">获取使用 Ws-metadata Exchange Oracle 数据库中的元数据</span><span class="sxs-lookup"><span data-stu-id="93feb-121">Get Metadata Using WS-Metadata Exchange in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-using-ws-metadata-exchange-in-oracle-database.md)  
  
-   [<span data-ttu-id="93feb-122">使用 IMetadataRetrievalContract 的 Oracle 数据库中获取元数据</span><span class="sxs-lookup"><span data-stu-id="93feb-122">Get Metadata in Oracle Database Using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-in-oracle-database-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a><span data-ttu-id="93feb-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93feb-123">See Also</span></span>  
[<span data-ttu-id="93feb-124">开发 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="93feb-124">Develop your Oracle Database applications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)