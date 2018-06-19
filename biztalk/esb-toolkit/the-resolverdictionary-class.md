---
title: ResolverDictionary 类 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46deb8a0-0523-4a5c-ac6b-45c506de7a72
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dfe0082ffc7f7b68c5c56811a28d5ccd20e93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294997"
---
# <a name="the-resolverdictionary-class"></a><span data-ttu-id="60777-102">ResolverDictionary 类</span><span class="sxs-lookup"><span data-stu-id="60777-102">The ResolverDictionary Class</span></span>
<span data-ttu-id="60777-103">**ResolverDictionary**类是**字典**-基于可以存储的实例的类**冲突解决程序**类作为**字符串**名称 /值对。</span><span class="sxs-lookup"><span data-stu-id="60777-103">The **ResolverDictionary** class is a **Dictionary**-based class that can store instances of the **Resolver** class as **String** name/value pairs.</span></span> <span data-ttu-id="60777-104">创建的实例时**ResolverDictionary**类，你必须提供对现有的引用**字典**实例。</span><span class="sxs-lookup"><span data-stu-id="60777-104">When creating instances of the **ResolverDictionary** class, you must provide a reference to an existing **Dictionary** instance.</span></span> <span data-ttu-id="60777-105">**ResolverDictionary**类提供的数据**冲突解决程序**时它执行运行时解析类使用。</span><span class="sxs-lookup"><span data-stu-id="60777-105">The **ResolverDictionary** class provides the data that the **Resolver** class uses when it performs run-time resolution.</span></span>  
  
 <span data-ttu-id="60777-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]安装程序安装并注册**Microsoft.Practices.ESB.Resolver.dll**具有程序集**ResolverDictionary**全局程序集缓存中的类。</span><span class="sxs-lookup"><span data-stu-id="60777-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with the **ResolverDictionary** class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="60777-107">**ResolverDictionary**该类会公开一种方法和一个属性：</span><span class="sxs-lookup"><span data-stu-id="60777-107">The **ResolverDictionary** class exposes one method and one property:</span></span>  
  
-   <span data-ttu-id="60777-108">**项 (** 密钥 **)**。</span><span class="sxs-lookup"><span data-stu-id="60777-108">**Item(** key **)**.</span></span> <span data-ttu-id="60777-109">此方法采用包含键名称的字符串值。</span><span class="sxs-lookup"><span data-stu-id="60777-109">This method takes a string value that contains a key name.</span></span> <span data-ttu-id="60777-110">它将返回相应的字符串值或空字符串如果该项不存在于基础**字典**实例。</span><span class="sxs-lookup"><span data-stu-id="60777-110">It returns the corresponding string value or an empty string if the item does not exist in the underlying **Dictionary** instance.</span></span>  
  
-   <span data-ttu-id="60777-111">**BaseDictionary**。</span><span class="sxs-lookup"><span data-stu-id="60777-111">**BaseDictionary**.</span></span> <span data-ttu-id="60777-112">此属性返回对基础的引用**字典**实例。</span><span class="sxs-lookup"><span data-stu-id="60777-112">This property returns a reference to the underlying **Dictionary** instance.</span></span>