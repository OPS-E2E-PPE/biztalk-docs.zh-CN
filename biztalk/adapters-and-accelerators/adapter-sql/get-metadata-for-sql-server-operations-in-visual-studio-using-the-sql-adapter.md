---
title: 获取 Visual Studio 中使用 SQL 适配器中的 SQL Server 操作的元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7ac720-e573-4564-8d15-8212a815f1f7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35733d7d90bca30218901f145acfefc763b8ccda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369439"
---
# <a name="get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter"></a><span data-ttu-id="ce2bf-102">获取 Visual Studio 中使用 SQL 适配器中的 SQL Server 操作的元数据</span><span class="sxs-lookup"><span data-stu-id="ce2bf-102">Get metadata for SQL Server operations in Visual Studio using the SQL adapter</span></span>
<span data-ttu-id="ce2bf-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]提供三种[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可用于帮助您开发使用该适配器的解决方案的组件 — [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ce2bf-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] provides three [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter—the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="ce2bf-104">适配器客户端必须使用这些组件连接到 SQL Server，然后生成他们想要执行的操作的元数据。</span><span class="sxs-lookup"><span data-stu-id="ce2bf-104">Adapter clients must use these components to connect to SQL Server and then generate metadata for the operations they want to perform.</span></span>  
  
 <span data-ttu-id="ce2bf-105">所有这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件简化的开发：</span><span class="sxs-lookup"><span data-stu-id="ce2bf-105">All these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
- <span data-ttu-id="ce2bf-106">为想要使用它在解决方案中的操作提供的 Microsoft Windows 界面，通过它您可以浏览和搜索。</span><span class="sxs-lookup"><span data-stu-id="ce2bf-106">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
- <span data-ttu-id="ce2bf-107">检索由这些目标操作该适配器公开的元数据。</span><span class="sxs-lookup"><span data-stu-id="ce2bf-107">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
- <span data-ttu-id="ce2bf-108">转换的元数据，这表示为 Web 服务描述语言 (WSDL) 文档适配器，可以使用你的解决方案 （的 BizTalk 项目的 XSD 消息架构或 WCF 服务协定的.NET 对象表示形式中的形式服务模型） 并将其添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="ce2bf-108">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
  <span data-ttu-id="ce2bf-109">本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ce2bf-109">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
