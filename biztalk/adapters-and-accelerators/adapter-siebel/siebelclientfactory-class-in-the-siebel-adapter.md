---
title: "Siebel 适配器中的 SiebelClientFactory 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SiebelClientFactory
- Data Provider for Siebel, SiebelClientFactory
- SiebelClientFactory, supported properties and methods
ms.assetid: f3a807d3-a030-47d8-b145-e18075ec353c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50e47b22c1d5a2575b0da3fae432acd79886e2c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="siebelclientfactory-class-in-the-siebel-adapter"></a><span data-ttu-id="4309c-102">Siebel 适配器中 SiebelClientFactory 类</span><span class="sxs-lookup"><span data-stu-id="4309c-102">SiebelClientFactory class in the Siebel adapter</span></span>
<span data-ttu-id="4309c-103">ADO.NET 客户端访问[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用泛型的 ADO.NET 类和接口。</span><span class="sxs-lookup"><span data-stu-id="4309c-103">An ADO.NET client accesses the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] using generic ADO.NET classes and interfaces.</span></span> <span data-ttu-id="4309c-104">若要启用此功能，[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]继承**System.Data.Common.DbProviderFactory**类。</span><span class="sxs-lookup"><span data-stu-id="4309c-104">To enable this feature, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] inherits the **System.Data.Common.DbProviderFactory** class.</span></span> <span data-ttu-id="4309c-105">客户端程序使用客户端，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4309c-105">The client program consumes the client as follows:</span></span>  
  
```  
  
DbProviderFactory factory = DbProviderFactories.GetFactory("Microsoft.Data.SiebelClient");  
DbConnection connection = factory.CreateConnection();  
```  
  
 <span data-ttu-id="4309c-106">替代方法是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4309c-106">An alternative approach is as follows:</span></span>  
  
```  
SiebelClientFactory factory = SiebelClientFactory.Instance;  
DbConnection connection = factory.CreateConnection();  
```  
  
 <span data-ttu-id="4309c-107">命名空间 Microsoft.Data.SiebelClient 中存在 SiebelClientFactory。</span><span class="sxs-lookup"><span data-stu-id="4309c-107">SiebelClientFactory exists in the namespace Microsoft.Data.SiebelClient.</span></span>  
  
## <a name="supported-members"></a><span data-ttu-id="4309c-108">受支持的成员</span><span class="sxs-lookup"><span data-stu-id="4309c-108">Supported Members</span></span>  
 <span data-ttu-id="4309c-109">**SiebelClientFactory**扩展**System.Data.CommonDbProviderFactory**。</span><span class="sxs-lookup"><span data-stu-id="4309c-109">**SiebelClientFactory** extends **System.Data.CommonDbProviderFactory**.</span></span>  <span data-ttu-id="4309c-110">下表提供的成员的说明**SiebelClientFactory**重写。</span><span class="sxs-lookup"><span data-stu-id="4309c-110">The following table provides a description of the members that **SiebelClientFactory** overrides.</span></span>  
  
|<span data-ttu-id="4309c-111">Name</span><span class="sxs-lookup"><span data-stu-id="4309c-111">Name</span></span>|<span data-ttu-id="4309c-112">Description</span><span class="sxs-lookup"><span data-stu-id="4309c-112">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="4309c-113">**实例**</span><span class="sxs-lookup"><span data-stu-id="4309c-113">**Instance**</span></span>|<span data-ttu-id="4309c-114">这是一个成员变量。</span><span class="sxs-lookup"><span data-stu-id="4309c-114">This is a member variable.</span></span>  <span data-ttu-id="4309c-115">它提供了 SiebelClientFactory 的单一实例。</span><span class="sxs-lookup"><span data-stu-id="4309c-115">It provides a singleton instance of SiebelClientFactory.</span></span>|  
|<span data-ttu-id="4309c-116">**CreateCommand()**</span><span class="sxs-lookup"><span data-stu-id="4309c-116">**CreateCommand()**</span></span>|<span data-ttu-id="4309c-117">创建 SiebelCommand 的实例。</span><span class="sxs-lookup"><span data-stu-id="4309c-117">Creates an instance of SiebelCommand.</span></span>|  
|<span data-ttu-id="4309c-118">**CreateConnection()**</span><span class="sxs-lookup"><span data-stu-id="4309c-118">**CreateConnection()**</span></span>|<span data-ttu-id="4309c-119">创建 SiebelConnection 的实例。</span><span class="sxs-lookup"><span data-stu-id="4309c-119">Creates an instance of SiebelConnection.</span></span>|  
|<span data-ttu-id="4309c-120">**CreateConnectionStringBuilder()**</span><span class="sxs-lookup"><span data-stu-id="4309c-120">**CreateConnectionStringBuilder()**</span></span>|<span data-ttu-id="4309c-121">创建 SiebelConnectionStringBuilder 的实例。</span><span class="sxs-lookup"><span data-stu-id="4309c-121">Creates an instance of SiebelConnectionStringBuilder.</span></span>|  
|<span data-ttu-id="4309c-122">**CreateParameter()**</span><span class="sxs-lookup"><span data-stu-id="4309c-122">**CreateParameter()**</span></span>|<span data-ttu-id="4309c-123">创建 SiebelParameter 的实例。</span><span class="sxs-lookup"><span data-stu-id="4309c-123">Creates an instance of SiebelParameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4309c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4309c-124">See Also</span></span>  
 [<span data-ttu-id="4309c-125">扩展 Siebel 适配器 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="4309c-125">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)