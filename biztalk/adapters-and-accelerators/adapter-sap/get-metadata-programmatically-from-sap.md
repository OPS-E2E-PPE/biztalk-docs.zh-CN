---
title: 从 SAP 以编程方式获取元数据 |Microsoft 文档
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
ms.openlocfilehash: 4c856b3629d7d7dcd3f9aa5431c0406f6c822e54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216829"
---
# <a name="get-metadata-programmatically-from-sap"></a><span data-ttu-id="2ab28-102">从 SAP 以编程方式获取元数据</span><span class="sxs-lookup"><span data-stu-id="2ab28-102">Get Metadata Programmatically from SAP</span></span>
<span data-ttu-id="2ab28-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是公开作为 WCF 服务的 SAP 系统的自定义 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="2ab28-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a custom WCF binding that exposes an SAP system as a WCF service.</span></span> <span data-ttu-id="2ab28-104">适配器将作为自描述服务; 公开 SAP 系统即，它能够发布元数据，它支持的操作有关的服务。</span><span class="sxs-lookup"><span data-stu-id="2ab28-104">The adapter exposes the SAP system as a self-describing service; that is, a service that is capable of publishing metadata about the operations that it supports.</span></span> <span data-ttu-id="2ab28-105">元数据描述 WCF 服务; 的逻辑接口即，服务协定、 消息和消息架构，必须用于与服务交互。</span><span class="sxs-lookup"><span data-stu-id="2ab28-105">Metadata describes the logical interface to a WCF service; that is, the service contract, messages, and message schemas that must be used to interact with the service.</span></span>  
  
 <span data-ttu-id="2ab28-106">此元数据是由工具中使用，如：</span><span class="sxs-lookup"><span data-stu-id="2ab28-106">This metadata is used by tools such as:</span></span>  
  
-   <span data-ttu-id="2ab28-107">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成的服务协定中，托管的代码表示形式和</span><span class="sxs-lookup"><span data-stu-id="2ab28-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate managed code representations of the service contract, and</span></span>  
  
-   <span data-ttu-id="2ab28-108">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成消息架构。</span><span class="sxs-lookup"><span data-stu-id="2ab28-108">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate message schemas.</span></span>  
  
 <span data-ttu-id="2ab28-109">但是，你还可以检索元数据以编程方式从适配器。</span><span class="sxs-lookup"><span data-stu-id="2ab28-109">However, you can also retrieve metadata programmatically from the adapter.</span></span> <span data-ttu-id="2ab28-110">例如，你可能想要执行此操作可创建要在现有应用程序中使用一个自定义元数据检索工具。</span><span class="sxs-lookup"><span data-stu-id="2ab28-110">For example, you might want to do this to create a custom metadata retrieval tool to use in an existing application.</span></span>  
  
 <span data-ttu-id="2ab28-111">适配器发布元数据通过两个终结点：</span><span class="sxs-lookup"><span data-stu-id="2ab28-111">The adapter publishes metadata through two endpoints:</span></span>  
  
-   <span data-ttu-id="2ab28-112">WS 元数据交换 (MEX) 终结点。</span><span class="sxs-lookup"><span data-stu-id="2ab28-112">A WS-Metadata Exchange (MEX) endpoint.</span></span> <span data-ttu-id="2ab28-113">WCF 自动提供的所有 WCF 绑定的 MEX 终结点。</span><span class="sxs-lookup"><span data-stu-id="2ab28-113">WCF automatically provides a MEX endpoint for all WCF bindings.</span></span> <span data-ttu-id="2ab28-114">可以使用元数据交换来检索元数据为基础的 SAP 系统上的适配器支持的操作。</span><span class="sxs-lookup"><span data-stu-id="2ab28-114">You can use metadata exchange to retrieve metadata for operations supported by the adapter on the underlying SAP system.</span></span>  
  
-   <span data-ttu-id="2ab28-115">**IMetadataRetrievalContract**终结点。</span><span class="sxs-lookup"><span data-stu-id="2ab28-115">An **IMetadataRetrievalContract** endpoint.</span></span> <span data-ttu-id="2ab28-116">**IMetadataRetrievalContract**接口由实现[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2ab28-116">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="2ab28-117">它对多个逻辑级别的 SAP 系统项目进行分类并使它们表现为元数据节点树。</span><span class="sxs-lookup"><span data-stu-id="2ab28-117">It categorizes SAP system artifacts at multiple logical levels and presents them as a tree of metadata nodes.</span></span> <span data-ttu-id="2ab28-118">你可以使用公开的方法**IMetadataRetrievalContract**界面，用于浏览和搜索此树的节点和以返回你感兴趣的操作的元数据。</span><span class="sxs-lookup"><span data-stu-id="2ab28-118">You can use methods exposed by the **IMetadataRetrievalContract** interface to browse and search the nodes of this tree and to return metadata for operations in which you are interested.</span></span>  
  
 <span data-ttu-id="2ab28-119">本部分中的主题介绍如何使用 MEX 和**IMetadataRetrievalContract**要从适配器以编程方式检索元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="2ab28-119">The topics in this section describe how to use MEX and **IMetadataRetrievalContract** endpoints to retrieve metadata programmatically from the adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ab28-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="2ab28-120">In This Section</span></span>  
  
-   [<span data-ttu-id="2ab28-121">在 SAP 中使用 Ws-metadata Exchange 检索元数据</span><span class="sxs-lookup"><span data-stu-id="2ab28-121">Retrieving Metadata Using WS-Metadata Exchange in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-using-ws-metadata-exchange-in-sap.md)  
  
-   [<span data-ttu-id="2ab28-122">SAP 使用 IMetadataRetrievalContract 中检索元数据</span><span class="sxs-lookup"><span data-stu-id="2ab28-122">Retrieving Metadata in SAP Using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ab28-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ab28-123">See Also</span></span>  
[<span data-ttu-id="2ab28-124">开发您的 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="2ab28-124">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)