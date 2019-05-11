---
title: Siebel 适配器的 SiebelCommand 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelCommand
- Data Provider for Siebel, SiebelCommand
- SiebelCommand, supported methods and properties
ms.assetid: 7cba0e47-634b-4878-b480-80fbcbbf5c90
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e35ecc56dd95fdd413827bc7744c1a02745eaa87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370582"
---
# <a name="siebelcommand-class-in-the-siebel-adapter"></a><span data-ttu-id="760cb-102">Siebel 适配器的 SiebelCommand 类</span><span class="sxs-lookup"><span data-stu-id="760cb-102">SiebelCommand class in the Siebel adapter</span></span>
<span data-ttu-id="760cb-103">建立与 Siebel 系统的连接后[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]分析 Siebel 命令字符串和提供的 ADO.NET 客户端的命令参数，并将该命令映射到 WCF 请求消息。</span><span class="sxs-lookup"><span data-stu-id="760cb-103">After establishing a connection with the Siebel system, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] parses the Siebel command strings and command parameters provided by the ADO.NET client and maps the command into a WCF request message.</span></span> <span data-ttu-id="760cb-104">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]然后发送到请求[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]并获取响应 XML 以及来自适配器的正文内容。</span><span class="sxs-lookup"><span data-stu-id="760cb-104">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] then sends the request to the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and obtains the response XML and the body contents from the adapter.</span></span> <span data-ttu-id="760cb-105">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]然后使用`XMLDataReader`从 XML 正文中检索的关系数据。</span><span class="sxs-lookup"><span data-stu-id="760cb-105">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] then uses the `XMLDataReader` to retrieve the relational data from the XML body.</span></span>  
  
 <span data-ttu-id="760cb-106">使用的实例`Microsoft.Data.SiebelClient.SiebelClientFactory`，客户端程序可以获取的实例`System.Data.Common.DbCommand`类来构造 Siebel 命令。</span><span class="sxs-lookup"><span data-stu-id="760cb-106">Using an instance of `Microsoft.Data.SiebelClient.SiebelClientFactory`, a client program can obtain an instance of the `System.Data.Common.DbCommand` class to construct a Siebel command.</span></span>  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbCommand command = factory.CreateCommand();  
```  
  
 <span data-ttu-id="760cb-107">或者，可以使用以下方法创建命令：</span><span class="sxs-lookup"><span data-stu-id="760cb-107">Alternatively, the following approach can be used to create a command:</span></span>  
  
```  
//Here connection is an instance of SiebelConnection  
SiebelCommand cmd = (SiebelCommand) connection.CreateCommand();  
cmd.CommandText = "SELECT [Name] as MyName, [City], [Country]  from Account.Account WHERE Name LIKE '3Com*' OPTION 'ViewMode 1'";  
```  
  
 <span data-ttu-id="760cb-108">`SiebelCommand`类继承自`DbCommand`。</span><span class="sxs-lookup"><span data-stu-id="760cb-108">The `SiebelCommand` class inherits from `DbCommand`.</span></span>  <span data-ttu-id="760cb-109">命名空间中存在`Microsoft.Data.SiebelClient`。</span><span class="sxs-lookup"><span data-stu-id="760cb-109">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="760cb-110">支持的属性</span><span class="sxs-lookup"><span data-stu-id="760cb-110">Supported Properties</span></span>  
 <span data-ttu-id="760cb-111">**SiebelCommand**类支持以下`DbCommand`*保护*属性：</span><span class="sxs-lookup"><span data-stu-id="760cb-111">The **SiebelCommand** class supports the following `DbCommand`*protected* properties:</span></span>  
  
|<span data-ttu-id="760cb-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="760cb-112">Name</span></span>|<span data-ttu-id="760cb-113">获取/设置</span><span class="sxs-lookup"><span data-stu-id="760cb-113">Get/Set</span></span>|<span data-ttu-id="760cb-114">Description</span><span class="sxs-lookup"><span data-stu-id="760cb-114">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="760cb-115">**DbConnection**</span><span class="sxs-lookup"><span data-stu-id="760cb-115">**DbConnection**</span></span>|<span data-ttu-id="760cb-116">获取和设置</span><span class="sxs-lookup"><span data-stu-id="760cb-116">Get and Set</span></span>|<span data-ttu-id="760cb-117">此文件应包含基础`DbConnection`从中实例`DbCommand`获取实例。</span><span class="sxs-lookup"><span data-stu-id="760cb-117">This should contain the underlying `DbConnection` instance from which this `DbCommand` instance is obtained.</span></span>|  
|<span data-ttu-id="760cb-118">**DbParameterCollection**</span><span class="sxs-lookup"><span data-stu-id="760cb-118">**DbParameterCollection**</span></span>|<span data-ttu-id="760cb-119">获取</span><span class="sxs-lookup"><span data-stu-id="760cb-119">Get</span></span>|<span data-ttu-id="760cb-120">获取集合的`DbParameter`对象。</span><span class="sxs-lookup"><span data-stu-id="760cb-120">Gets the collection of `DbParameter` objects.</span></span>|  
  
 <span data-ttu-id="760cb-121">`SiebelCommand` 此外支持以下`DbCommand`*公共*属性：</span><span class="sxs-lookup"><span data-stu-id="760cb-121">`SiebelCommand` also supports the following `DbCommand`*public* properties:</span></span>  
  
|<span data-ttu-id="760cb-122">“属性”</span><span class="sxs-lookup"><span data-stu-id="760cb-122">Name</span></span>|<span data-ttu-id="760cb-123">获取/设置</span><span class="sxs-lookup"><span data-stu-id="760cb-123">Get/Set</span></span>|<span data-ttu-id="760cb-124">Description</span><span class="sxs-lookup"><span data-stu-id="760cb-124">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="760cb-125">**CommandText**</span><span class="sxs-lookup"><span data-stu-id="760cb-125">**CommandText**</span></span>|<span data-ttu-id="760cb-126">获取和设置</span><span class="sxs-lookup"><span data-stu-id="760cb-126">Get and Set</span></span>|<span data-ttu-id="760cb-127">此文件包含 ADO.NET 客户端想要执行的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="760cb-127">This contain the SQL statement that the ADO.NET client wishes to execute.</span></span>|  
|<span data-ttu-id="760cb-128">**CommandType**</span><span class="sxs-lookup"><span data-stu-id="760cb-128">**CommandType**</span></span>|<span data-ttu-id="760cb-129">获取和设置</span><span class="sxs-lookup"><span data-stu-id="760cb-129">Get and Set</span></span>|<span data-ttu-id="760cb-130">仅`CommandType.Text`支持。</span><span class="sxs-lookup"><span data-stu-id="760cb-130">Only `CommandType.Text` is supported.</span></span>|  
|<span data-ttu-id="760cb-131">**“连接”**</span><span class="sxs-lookup"><span data-stu-id="760cb-131">**Connection**</span></span>|<span data-ttu-id="760cb-132">获取和设置</span><span class="sxs-lookup"><span data-stu-id="760cb-132">Get and Set</span></span>|<span data-ttu-id="760cb-133">这将使用`DbConnection`成员。</span><span class="sxs-lookup"><span data-stu-id="760cb-133">This uses the `DbConnection` member.</span></span>|  
|<span data-ttu-id="760cb-134">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="760cb-134">**Parameters**</span></span>|<span data-ttu-id="760cb-135">获取</span><span class="sxs-lookup"><span data-stu-id="760cb-135">Get</span></span>|<span data-ttu-id="760cb-136">这将使用`DbParameterCollection`成员。</span><span class="sxs-lookup"><span data-stu-id="760cb-136">This uses the `DbParameterCollection` member.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="760cb-137">`SiebelCommand`类将忽略`CommandTimeout`， `DesignTimeVisible`，和`DbTransaction`属性。</span><span class="sxs-lookup"><span data-stu-id="760cb-137">The `SiebelCommand` class ignores the `CommandTimeout`, `DesignTimeVisible`, and `DbTransaction` properties.</span></span>  
  
## <a name="supported-methods"></a><span data-ttu-id="760cb-138">受支持的方法</span><span class="sxs-lookup"><span data-stu-id="760cb-138">Supported Methods</span></span>  
 <span data-ttu-id="760cb-139">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持以下`DbCommand`*保护*方法：</span><span class="sxs-lookup"><span data-stu-id="760cb-139">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports the following `DbCommand`*protected* methods:</span></span>  
  
|<span data-ttu-id="760cb-140">“属性”</span><span class="sxs-lookup"><span data-stu-id="760cb-140">Name</span></span>|<span data-ttu-id="760cb-141">Description</span><span class="sxs-lookup"><span data-stu-id="760cb-141">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="760cb-142">**CreateDbParameter**</span><span class="sxs-lookup"><span data-stu-id="760cb-142">**CreateDbParameter**</span></span>|<span data-ttu-id="760cb-143">创建一个新`DbParameter`实例。</span><span class="sxs-lookup"><span data-stu-id="760cb-143">Creates a new `DbParameter` instance.</span></span>|  
|<span data-ttu-id="760cb-144">**ExecuteDbDataReader**</span><span class="sxs-lookup"><span data-stu-id="760cb-144">**ExecuteDbDataReader**</span></span>|<span data-ttu-id="760cb-145">这将运行的 SELECT 和 EXEC 命令并返回`DbDataReader`。</span><span class="sxs-lookup"><span data-stu-id="760cb-145">This executes the SELECT and EXEC commands and returns a `DbDataReader`.</span></span>|  
  
 <span data-ttu-id="760cb-146">`SiebelCommand` 此外支持以下`DbCommand`*公共*方法：</span><span class="sxs-lookup"><span data-stu-id="760cb-146">`SiebelCommand` also supports the following `DbCommand`*public* methods:</span></span>  
  
|<span data-ttu-id="760cb-147">“属性”</span><span class="sxs-lookup"><span data-stu-id="760cb-147">Name</span></span>|<span data-ttu-id="760cb-148">Description</span><span class="sxs-lookup"><span data-stu-id="760cb-148">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="760cb-149">**CreateParameter**</span><span class="sxs-lookup"><span data-stu-id="760cb-149">**CreateParameter**</span></span>|<span data-ttu-id="760cb-150">创建一个新`DbParameter`实例通过 `CreateDbParameter().`</span><span class="sxs-lookup"><span data-stu-id="760cb-150">Creates a new `DbParameter` instance through `CreateDbParameter().`</span></span>|  
|<span data-ttu-id="760cb-151">**ExecuteReader**</span><span class="sxs-lookup"><span data-stu-id="760cb-151">**ExecuteReader**</span></span>|<span data-ttu-id="760cb-152">执行`CommandText`针对`Connection`，并返回`DbDataReader`通过`ExecuteDbDataReader()`。</span><span class="sxs-lookup"><span data-stu-id="760cb-152">Executes `CommandText` against the `Connection` and returns `DbDataReader` through `ExecuteDbDataReader()`.</span></span>|  
|<span data-ttu-id="760cb-153">**准备**</span><span class="sxs-lookup"><span data-stu-id="760cb-153">**Prepare**</span></span>|<span data-ttu-id="760cb-154">这将解析`CommandText`和生成的 SQL 命令分析树。</span><span class="sxs-lookup"><span data-stu-id="760cb-154">This parses the `CommandText` and builds the SQL command parse tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="760cb-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="760cb-155">See Also</span></span>  
 [<span data-ttu-id="760cb-156">使用 Siebel 适配器扩展 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="760cb-156">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)