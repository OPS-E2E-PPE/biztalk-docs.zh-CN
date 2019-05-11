---
title: Siebel 适配器的 SiebelClientFactory 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelClientFactory
- Data Provider for Siebel, SiebelClientFactory
- SiebelClientFactory, supported properties and methods
ms.assetid: f3a807d3-a030-47d8-b145-e18075ec353c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c732d029e1c3866caf5d20f11a790b80bc40cf68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370706"
---
# <a name="siebelclientfactory-class-in-the-siebel-adapter"></a><span data-ttu-id="42215-102">Siebel 适配器的 SiebelClientFactory 类</span><span class="sxs-lookup"><span data-stu-id="42215-102">SiebelClientFactory class in the Siebel adapter</span></span>
<span data-ttu-id="42215-103">ADO.NET 客户端访问[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用泛型 ADO.NET 类和接口。</span><span class="sxs-lookup"><span data-stu-id="42215-103">An ADO.NET client accesses the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] using generic ADO.NET classes and interfaces.</span></span> <span data-ttu-id="42215-104">若要启用此功能[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]继承**System.Data.Common.DbProviderFactory**类。</span><span class="sxs-lookup"><span data-stu-id="42215-104">To enable this feature, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] inherits the **System.Data.Common.DbProviderFactory** class.</span></span> <span data-ttu-id="42215-105">客户端程序使用客户端，如下所示：</span><span class="sxs-lookup"><span data-stu-id="42215-105">The client program consumes the client as follows:</span></span>  
  
```  
  
DbProviderFactory factory = DbProviderFactories.GetFactory("Microsoft.Data.SiebelClient");  
DbConnection connection = factory.CreateConnection();  
```  
  
 <span data-ttu-id="42215-106">另一种方法是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="42215-106">An alternative approach is as follows:</span></span>  
  
```  
SiebelClientFactory factory = SiebelClientFactory.Instance;  
DbConnection connection = factory.CreateConnection();  
```  
  
 <span data-ttu-id="42215-107">SiebelClientFactory Microsoft.Data.SiebelClient 的命名空间中存在。</span><span class="sxs-lookup"><span data-stu-id="42215-107">SiebelClientFactory exists in the namespace Microsoft.Data.SiebelClient.</span></span>  
  
## <a name="supported-members"></a><span data-ttu-id="42215-108">受支持的成员</span><span class="sxs-lookup"><span data-stu-id="42215-108">Supported Members</span></span>  
 <span data-ttu-id="42215-109">**SiebelClientFactory**扩展**System.Data.CommonDbProviderFactory**。</span><span class="sxs-lookup"><span data-stu-id="42215-109">**SiebelClientFactory** extends **System.Data.CommonDbProviderFactory**.</span></span>  <span data-ttu-id="42215-110">下表提供的成员的说明**SiebelClientFactory**重写。</span><span class="sxs-lookup"><span data-stu-id="42215-110">The following table provides a description of the members that **SiebelClientFactory** overrides.</span></span>  
  
|<span data-ttu-id="42215-111">“属性”</span><span class="sxs-lookup"><span data-stu-id="42215-111">Name</span></span>|<span data-ttu-id="42215-112">Description</span><span class="sxs-lookup"><span data-stu-id="42215-112">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="42215-113">**实例**</span><span class="sxs-lookup"><span data-stu-id="42215-113">**Instance**</span></span>|<span data-ttu-id="42215-114">这是一个成员变量。</span><span class="sxs-lookup"><span data-stu-id="42215-114">This is a member variable.</span></span>  <span data-ttu-id="42215-115">它提供了 SiebelClientFactory 的单一实例。</span><span class="sxs-lookup"><span data-stu-id="42215-115">It provides a singleton instance of SiebelClientFactory.</span></span>|  
|<span data-ttu-id="42215-116">**CreateCommand()**</span><span class="sxs-lookup"><span data-stu-id="42215-116">**CreateCommand()**</span></span>|<span data-ttu-id="42215-117">创建 SiebelCommand 的实例。</span><span class="sxs-lookup"><span data-stu-id="42215-117">Creates an instance of SiebelCommand.</span></span>|  
|<span data-ttu-id="42215-118">**CreateConnection()**</span><span class="sxs-lookup"><span data-stu-id="42215-118">**CreateConnection()**</span></span>|<span data-ttu-id="42215-119">创建 SiebelConnection 的实例。</span><span class="sxs-lookup"><span data-stu-id="42215-119">Creates an instance of SiebelConnection.</span></span>|  
|<span data-ttu-id="42215-120">**CreateConnectionStringBuilder()**</span><span class="sxs-lookup"><span data-stu-id="42215-120">**CreateConnectionStringBuilder()**</span></span>|<span data-ttu-id="42215-121">创建 SiebelConnectionStringBuilder 的实例。</span><span class="sxs-lookup"><span data-stu-id="42215-121">Creates an instance of SiebelConnectionStringBuilder.</span></span>|  
|<span data-ttu-id="42215-122">**CreateParameter()**</span><span class="sxs-lookup"><span data-stu-id="42215-122">**CreateParameter()**</span></span>|<span data-ttu-id="42215-123">创建 SiebelParameter 的实例。</span><span class="sxs-lookup"><span data-stu-id="42215-123">Creates an instance of SiebelParameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42215-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="42215-124">See Also</span></span>  
 [<span data-ttu-id="42215-125">使用 Siebel 适配器扩展 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="42215-125">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)