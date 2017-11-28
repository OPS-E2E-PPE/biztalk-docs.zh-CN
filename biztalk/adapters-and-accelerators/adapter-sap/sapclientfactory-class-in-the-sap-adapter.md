---
title: "SAP 适配器中的 SAPClientFactory 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPClientFactory, supported methods and classes
ms.assetid: e64de5e4-e53f-4708-ab02-9e12774e94cd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c82e4bea6a16085608ebf1f8fe10ea95b4db394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sapclientfactory-class-in-the-sap-adapter"></a><span data-ttu-id="34fcf-102">SAP 适配器中 SAPClientFactory 类</span><span class="sxs-lookup"><span data-stu-id="34fcf-102">SAPClientFactory class in the SAP adapter</span></span>
<span data-ttu-id="34fcf-103">以下部分列出的方法和属性**SAPClientFactory**类。</span><span class="sxs-lookup"><span data-stu-id="34fcf-103">The following section lists the methods and properties for the **SAPClientFactory** class.</span></span> <span data-ttu-id="34fcf-104">该项派生自**System.Data.Common.DbProviderFactory**。</span><span class="sxs-lookup"><span data-stu-id="34fcf-104">This is derived from **System.Data.Common.DbProviderFactory**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="34fcf-105">受支持的属性</span><span class="sxs-lookup"><span data-stu-id="34fcf-105">Supported Properties</span></span>  
  
|<span data-ttu-id="34fcf-106">Name</span><span class="sxs-lookup"><span data-stu-id="34fcf-106">Name</span></span>|<span data-ttu-id="34fcf-107">Get/Set</span><span class="sxs-lookup"><span data-stu-id="34fcf-107">Get/Set</span></span>|<span data-ttu-id="34fcf-108">Description</span><span class="sxs-lookup"><span data-stu-id="34fcf-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="34fcf-109">**实例**</span><span class="sxs-lookup"><span data-stu-id="34fcf-109">**Instance**</span></span>|-|<span data-ttu-id="34fcf-110">SAPClientFactory 单一实例</span><span class="sxs-lookup"><span data-stu-id="34fcf-110">Singleton instance of SAPClientFactory</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="34fcf-111">支持的方法</span><span class="sxs-lookup"><span data-stu-id="34fcf-111">Supported Methods</span></span>  
  
|<span data-ttu-id="34fcf-112">Name</span><span class="sxs-lookup"><span data-stu-id="34fcf-112">Name</span></span>|<span data-ttu-id="34fcf-113">Description</span><span class="sxs-lookup"><span data-stu-id="34fcf-113">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="34fcf-114">**CreateCommand()**</span><span class="sxs-lookup"><span data-stu-id="34fcf-114">**CreateCommand()**</span></span>|<span data-ttu-id="34fcf-115">创建 SAPCommand 的实例</span><span class="sxs-lookup"><span data-stu-id="34fcf-115">Creates an instance of SAPCommand</span></span>|  
|<span data-ttu-id="34fcf-116">**CreateConnection()**</span><span class="sxs-lookup"><span data-stu-id="34fcf-116">**CreateConnection()**</span></span>|<span data-ttu-id="34fcf-117">创建 SAPConnection 的实例</span><span class="sxs-lookup"><span data-stu-id="34fcf-117">Creates an instance of SAPConnection</span></span>|  
|<span data-ttu-id="34fcf-118">**CreateConnectionStringBuilder()**</span><span class="sxs-lookup"><span data-stu-id="34fcf-118">**CreateConnectionStringBuilder()**</span></span>|<span data-ttu-id="34fcf-119">创建 SAPConnectionStringBuilder 的实例</span><span class="sxs-lookup"><span data-stu-id="34fcf-119">Creates an instance of SAPConnectionStringBuilder</span></span>|  
|<span data-ttu-id="34fcf-120">**CreateParameter()**</span><span class="sxs-lookup"><span data-stu-id="34fcf-120">**CreateParameter()**</span></span>|<span data-ttu-id="34fcf-121">创建 SAPParameter 的实例</span><span class="sxs-lookup"><span data-stu-id="34fcf-121">Creates an instance of SAPParameter</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34fcf-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34fcf-122">See Also</span></span>  
 [<span data-ttu-id="34fcf-123">使用 SAP 适配器扩展 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="34fcf-123">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)