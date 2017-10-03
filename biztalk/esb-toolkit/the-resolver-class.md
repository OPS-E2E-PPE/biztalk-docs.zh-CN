---
title: "解析程序类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9ebd6c2-fd86-471a-bc50-b1b89f701fab
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1359bcbb9c6c918fc0ee6d5e67bacb8e3559c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolver-class"></a><span data-ttu-id="2e4f3-102">解析程序类</span><span class="sxs-lookup"><span data-stu-id="2e4f3-102">The Resolver Class</span></span>
<span data-ttu-id="2e4f3-103">**冲突解决程序**类是一个简单结构，它公开一个名称/值对。</span><span class="sxs-lookup"><span data-stu-id="2e4f3-103">The **Resolver** class is a simple structure that exposes a name/value pair.</span></span> <span data-ttu-id="2e4f3-104">冲突解决程序 Web 服务从其方法返回此类的实例的泛型集合。</span><span class="sxs-lookup"><span data-stu-id="2e4f3-104">The Resolver Web service returns a generic collection of instances of this class from its methods.</span></span>  
  
 <span data-ttu-id="2e4f3-105">ESB 核心安装程序安装并注册**Microsoft.Practices.ESB.Resolver.dll**与在全局程序集缓存中的解析程序类的程序集。</span><span class="sxs-lookup"><span data-stu-id="2e4f3-105">The ESB Core installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with Resolver class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="2e4f3-106">使用基于字典的名称/值接近的使其更易于在将来添加新项，释放并避免包含依赖于的解析方法和当前的冲突解决程序类型的非相关属性的解析结果的大小降至最低。</span><span class="sxs-lookup"><span data-stu-id="2e4f3-106">The use of a dictionary-based name/value approach makes it easier to add new items in future releases and minimizes the size of the resolution result by avoiding inclusion of non-relevant properties that depend on the resolution method and the current resolver type.</span></span>  
  
 <span data-ttu-id="2e4f3-107">**冲突解决程序**类公开两个属性：</span><span class="sxs-lookup"><span data-stu-id="2e4f3-107">The **Resolver** class exposes two properties:</span></span>  
  
-   <span data-ttu-id="2e4f3-108">**名称**。</span><span class="sxs-lookup"><span data-stu-id="2e4f3-108">**Name**.</span></span> <span data-ttu-id="2e4f3-109">这是一个名称/值对，包含解决连接字符串后返回的信息的名称。</span><span class="sxs-lookup"><span data-stu-id="2e4f3-109">This is the name of a name/value pair that contains information that is returned after a connection string is resolved.</span></span>  
  
-   <span data-ttu-id="2e4f3-110">**值**。</span><span class="sxs-lookup"><span data-stu-id="2e4f3-110">**Value**.</span></span> <span data-ttu-id="2e4f3-111">这是名称/值对的名称对应的值。</span><span class="sxs-lookup"><span data-stu-id="2e4f3-111">This is the value that corresponds to the name of the name/value pair.</span></span>