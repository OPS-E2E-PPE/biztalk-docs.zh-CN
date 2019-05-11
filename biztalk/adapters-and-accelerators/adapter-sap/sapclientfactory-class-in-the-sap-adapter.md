---
title: SAP 适配器 SAPClientFactory 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPClientFactory, supported methods and classes
ms.assetid: e64de5e4-e53f-4708-ab02-9e12774e94cd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9920403c0ce260bed686640227c4d05923563f4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372981"
---
# <a name="sapclientfactory-class-in-the-sap-adapter"></a><span data-ttu-id="5a69e-102">SAP 适配器 SAPClientFactory 类</span><span class="sxs-lookup"><span data-stu-id="5a69e-102">SAPClientFactory class in the SAP adapter</span></span>
<span data-ttu-id="5a69e-103">以下部分列出的方法和属性**SAPClientFactory**类。</span><span class="sxs-lookup"><span data-stu-id="5a69e-103">The following section lists the methods and properties for the **SAPClientFactory** class.</span></span> <span data-ttu-id="5a69e-104">这派生自**System.Data.Common.DbProviderFactory**。</span><span class="sxs-lookup"><span data-stu-id="5a69e-104">This is derived from **System.Data.Common.DbProviderFactory**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="5a69e-105">支持的属性</span><span class="sxs-lookup"><span data-stu-id="5a69e-105">Supported Properties</span></span>  
  
|<span data-ttu-id="5a69e-106">“属性”</span><span class="sxs-lookup"><span data-stu-id="5a69e-106">Name</span></span>|<span data-ttu-id="5a69e-107">获取/设置</span><span class="sxs-lookup"><span data-stu-id="5a69e-107">Get/Set</span></span>|<span data-ttu-id="5a69e-108">Description</span><span class="sxs-lookup"><span data-stu-id="5a69e-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="5a69e-109">**实例**</span><span class="sxs-lookup"><span data-stu-id="5a69e-109">**Instance**</span></span>|-|<span data-ttu-id="5a69e-110">SAPClientFactory 单一实例</span><span class="sxs-lookup"><span data-stu-id="5a69e-110">Singleton instance of SAPClientFactory</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="5a69e-111">受支持的方法</span><span class="sxs-lookup"><span data-stu-id="5a69e-111">Supported Methods</span></span>  
  
|<span data-ttu-id="5a69e-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="5a69e-112">Name</span></span>|<span data-ttu-id="5a69e-113">Description</span><span class="sxs-lookup"><span data-stu-id="5a69e-113">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5a69e-114">**CreateCommand()**</span><span class="sxs-lookup"><span data-stu-id="5a69e-114">**CreateCommand()**</span></span>|<span data-ttu-id="5a69e-115">创建 SAPCommand 的实例</span><span class="sxs-lookup"><span data-stu-id="5a69e-115">Creates an instance of SAPCommand</span></span>|  
|<span data-ttu-id="5a69e-116">**CreateConnection()**</span><span class="sxs-lookup"><span data-stu-id="5a69e-116">**CreateConnection()**</span></span>|<span data-ttu-id="5a69e-117">创建 SAPConnection 的实例</span><span class="sxs-lookup"><span data-stu-id="5a69e-117">Creates an instance of SAPConnection</span></span>|  
|<span data-ttu-id="5a69e-118">**CreateConnectionStringBuilder()**</span><span class="sxs-lookup"><span data-stu-id="5a69e-118">**CreateConnectionStringBuilder()**</span></span>|<span data-ttu-id="5a69e-119">创建 SAPConnectionStringBuilder 的实例</span><span class="sxs-lookup"><span data-stu-id="5a69e-119">Creates an instance of SAPConnectionStringBuilder</span></span>|  
|<span data-ttu-id="5a69e-120">**CreateParameter()**</span><span class="sxs-lookup"><span data-stu-id="5a69e-120">**CreateParameter()**</span></span>|<span data-ttu-id="5a69e-121">创建 SAPParameter 的实例</span><span class="sxs-lookup"><span data-stu-id="5a69e-121">Creates an instance of SAPParameter</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a69e-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a69e-122">See Also</span></span>  
 [<span data-ttu-id="5a69e-123">扩展 ADO.NET 接口，与 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="5a69e-123">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)