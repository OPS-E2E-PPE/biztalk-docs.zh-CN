---
title: "Siebel 适配器中的 SiebelConnectionStringBuilder 类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SiebelConnectionStringBuilder, supported properties and methods
- Data Provider for Siebel, SiebelConnectionStringBuilder
- SiebelConnectionStringBuilder
ms.assetid: 4995fce8-7e62-4af9-a731-47b16438067c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 088748c63983e76e64d32f54b3e999fadd88d23a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="siebelconnectionstringbuilder-class-in-the-siebel-adapter"></a><span data-ttu-id="a9e51-102">Siebel 适配器中 SiebelConnectionStringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="a9e51-102">SiebelConnectionStringBuilder class in the Siebel adapter</span></span>
<span data-ttu-id="a9e51-103">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供`DbConnectionStringBuilder`实现以启用 SQL Server Integration Services (SSIS) 和 Visual Studio 资源管理器工具环境中，以获取的连接属性[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]并将其显示形式的 GUI 由驱动属性网格。</span><span class="sxs-lookup"><span data-stu-id="a9e51-103">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] provides a `DbConnectionStringBuilder` implementation to enable SQL Server Integration Services (SSIS) and Visual Studio explorer tools environments to get the connection properties of the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] and display them in the form of a GUI driven by the PropertyGrid.</span></span>  
  
 <span data-ttu-id="a9e51-104">若要创建 SiebelConnectionStringBuilder，请使用以下方法：</span><span class="sxs-lookup"><span data-stu-id="a9e51-104">To create a SiebelConnectionStringBuilder, use the following approach:</span></span>  
  
```  
  
//In this example, factory is an instance of SiebelClientFactory  
SiebelConnectionStringBuilder bldr = (SiebelConnectionStringBuilder)factory.CreateConnectionStringBuilder();  
bldr.ConnectionString = connstr;  
```  
  
 <span data-ttu-id="a9e51-105">或者，只需：</span><span class="sxs-lookup"><span data-stu-id="a9e51-105">Or, simply:</span></span>  
  
```  
  
SiebelConnectionStringBuilder bldr = new SiebelConnectionStringBuilder();  
```  
  
 <span data-ttu-id="a9e51-106">若要查看的键和值的一部分支持`DbConnectionStringBuilder`，请参阅[Siebel 连接字符串的数据提供程序属性](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="a9e51-106">To see the keys and values supported as part of the `DbConnectionStringBuilder`, see [Data Provider properties for the Siebel Connection String](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e51-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9e51-107">See Also</span></span>  
 [<span data-ttu-id="a9e51-108">扩展 Siebel 适配器 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="a9e51-108">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)