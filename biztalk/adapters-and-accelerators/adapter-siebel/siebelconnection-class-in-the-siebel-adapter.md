---
title: "Siebel 适配器中的 SiebelConnection 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, SiebelConnection
- SiebelConnection, supported properties and methods
- SiebelConnection
ms.assetid: 661d9876-4c14-4748-b05f-cc4fd1c4ebcf
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fc99c2e3f019f2ddf88647b0faeb7e41644fd0e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="siebelconnection-class-in-the-siebel-adapter"></a><span data-ttu-id="d0fca-102">Siebel 适配器中 SiebelConnection 类</span><span class="sxs-lookup"><span data-stu-id="d0fca-102">SiebelConnection class in the Siebel adapter</span></span>
<span data-ttu-id="d0fca-103">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]访问基础[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] `Binding`、 `ConnectionFactory`，和`Channel`以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="d0fca-103">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] accesses the underlying [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]`Binding`, the `ConnectionFactory`, and `Channel` to connect to the Siebel system.</span></span> <span data-ttu-id="d0fca-104">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]实现`DbConnection`类，以支持上述功能。</span><span class="sxs-lookup"><span data-stu-id="d0fca-104">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] implements the `DbConnection` class to support the preceding features.</span></span>  
  
 <span data-ttu-id="d0fca-105">使用的实例`Microsoft.Data.SiebelClient.SiebelClientFactory`，客户端程序可以获取的实例`System.Data.Common.DbConnection`类连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="d0fca-105">Using an instance of `Microsoft.Data.SiebelClient.SiebelClientFactory`, a client program can obtain an instance of the `System.Data.Common.DbConnection` class to connect to the Siebel system.</span></span>  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbConnection connection = factory.CreateConnection();  
```  
  
 <span data-ttu-id="d0fca-106">或者，可以使用以下方法创建的连接：</span><span class="sxs-lookup"><span data-stu-id="d0fca-106">Alternatively, the following approach can be used to create a connection:</span></span>  
  
```  
  
SiebelConnection connection = new SiebelConnection();  
connection.ConnectionString = connectionString;  
```  
  
 <span data-ttu-id="d0fca-107">`SiebelConnection`类继承自`DbConnection`。</span><span class="sxs-lookup"><span data-stu-id="d0fca-107">The `SiebelConnection` class inherits from `DbConnection`.</span></span> <span data-ttu-id="d0fca-108">命名空间中存在`Microsoft.Data.SiebelClient`。</span><span class="sxs-lookup"><span data-stu-id="d0fca-108">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="d0fca-109">受支持的属性</span><span class="sxs-lookup"><span data-stu-id="d0fca-109">Supported Properties</span></span>  
 <span data-ttu-id="d0fca-110">`SiebelConnection`类支持以下`DbConnection`属性。</span><span class="sxs-lookup"><span data-stu-id="d0fca-110">The `SiebelConnection` class supports the following `DbConnection` properties.</span></span>  
  
|<span data-ttu-id="d0fca-111">Name</span><span class="sxs-lookup"><span data-stu-id="d0fca-111">Name</span></span>|<span data-ttu-id="d0fca-112">Get/Set</span><span class="sxs-lookup"><span data-stu-id="d0fca-112">Get/Set</span></span>|<span data-ttu-id="d0fca-113">Description</span><span class="sxs-lookup"><span data-stu-id="d0fca-113">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="d0fca-114">**ConnectionString**</span><span class="sxs-lookup"><span data-stu-id="d0fca-114">**ConnectionString**</span></span>|<span data-ttu-id="d0fca-115">获取和设置</span><span class="sxs-lookup"><span data-stu-id="d0fca-115">Get and Set</span></span>|<span data-ttu-id="d0fca-116">获取或设置用于打开连接的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0fca-116">Gets or sets the string used to open the connection.</span></span>|  
|<span data-ttu-id="d0fca-117">**数据库**</span><span class="sxs-lookup"><span data-stu-id="d0fca-117">**Database**</span></span>|<span data-ttu-id="d0fca-118">获取</span><span class="sxs-lookup"><span data-stu-id="d0fca-118">Get</span></span>|<span data-ttu-id="d0fca-119">获取当前数据库后打开某个连接的名称或打开连接之前，连接字符串中指定的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="d0fca-119">Gets the name of the current database after a connection is opened, or the database name specified in the connection string before the connection is opened.</span></span> <span data-ttu-id="d0fca-120">这应该是 Siebel 存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="d0fca-120">This should be the Siebel repository name.</span></span>|  
|<span data-ttu-id="d0fca-121">**DataSource**</span><span class="sxs-lookup"><span data-stu-id="d0fca-121">**DataSource**</span></span>|<span data-ttu-id="d0fca-122">获取</span><span class="sxs-lookup"><span data-stu-id="d0fca-122">Get</span></span>|<span data-ttu-id="d0fca-123">获取此连接 Siebel 网关的名称。</span><span class="sxs-lookup"><span data-stu-id="d0fca-123">Gets the name of the Siebel gateway for this connection.</span></span>|  
|<span data-ttu-id="d0fca-124">**ServerVersion**</span><span class="sxs-lookup"><span data-stu-id="d0fca-124">**ServerVersion**</span></span>|<span data-ttu-id="d0fca-125">获取</span><span class="sxs-lookup"><span data-stu-id="d0fca-125">Get</span></span>|<span data-ttu-id="d0fca-126">中的当前版本[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，此属性返回硬编码值，该值不表示 Siebel 服务器的实际版本。</span><span class="sxs-lookup"><span data-stu-id="d0fca-126">In the current version of [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], this property returns a hard-coded value, which does not represent the actual version of the Siebel server.</span></span>|  
|<span data-ttu-id="d0fca-127">**State**</span><span class="sxs-lookup"><span data-stu-id="d0fca-127">**State**</span></span>|<span data-ttu-id="d0fca-128">获取</span><span class="sxs-lookup"><span data-stu-id="d0fca-128">Get</span></span>|<span data-ttu-id="d0fca-129">获取说明连接状态的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0fca-129">Gets a string that describes the state of the connection.</span></span> <span data-ttu-id="d0fca-130">此文件可以包含三个可能值： 打开、 中断或已关闭。</span><span class="sxs-lookup"><span data-stu-id="d0fca-130">This can contain three possible values: OPEN, BROKEN, or CLOSED.</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="d0fca-131">支持的方法</span><span class="sxs-lookup"><span data-stu-id="d0fca-131">Supported Methods</span></span>  
 <span data-ttu-id="d0fca-132">`SiebelConnection`类支持以下`DbConnection`方法。</span><span class="sxs-lookup"><span data-stu-id="d0fca-132">The `SiebelConnection` class supports the following `DbConnection` methods.</span></span>  
  
|<span data-ttu-id="d0fca-133">Name</span><span class="sxs-lookup"><span data-stu-id="d0fca-133">Name</span></span>|<span data-ttu-id="d0fca-134">Description</span><span class="sxs-lookup"><span data-stu-id="d0fca-134">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d0fca-135">**CreateDbCommand**</span><span class="sxs-lookup"><span data-stu-id="d0fca-135">**CreateDbCommand**</span></span>|<span data-ttu-id="d0fca-136">此受保护的方法提供的新 DbCommand 实例。</span><span class="sxs-lookup"><span data-stu-id="d0fca-136">This protected method provides a new DbCommand instance.</span></span>|  
|<span data-ttu-id="d0fca-137">**ChangeDatabase**</span><span class="sxs-lookup"><span data-stu-id="d0fca-137">**ChangeDatabase**</span></span>|<span data-ttu-id="d0fca-138">此公共方法不受支持，并将引发异常，如果调用。</span><span class="sxs-lookup"><span data-stu-id="d0fca-138">This public method is not supported, and will throw an exception if called.</span></span>|  
|<span data-ttu-id="d0fca-139">**打开**</span><span class="sxs-lookup"><span data-stu-id="d0fca-139">**Open**</span></span>|<span data-ttu-id="d0fca-140">通过创建 WCF 通道 Siebel 系统与打开的连接。</span><span class="sxs-lookup"><span data-stu-id="d0fca-140">Opens a connection with the Siebel system by creating a WCF channel.</span></span>|  
|<span data-ttu-id="d0fca-141">**关闭**</span><span class="sxs-lookup"><span data-stu-id="d0fca-141">**Close**</span></span>|<span data-ttu-id="d0fca-142">通过关闭 WCF 通道来关闭与 Siebel 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="d0fca-142">Closes a connection with the Siebel system by closing a WCF channel.</span></span>|  
|<span data-ttu-id="d0fca-143">**CreateCommand**</span><span class="sxs-lookup"><span data-stu-id="d0fca-143">**CreateCommand**</span></span>|<span data-ttu-id="d0fca-144">创建命令对象。</span><span class="sxs-lookup"><span data-stu-id="d0fca-144">Creates a command object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0fca-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0fca-145">See Also</span></span>  
 [<span data-ttu-id="d0fca-146">扩展 Siebel 适配器 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="d0fca-146">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)