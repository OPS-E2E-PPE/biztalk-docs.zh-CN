---
title: Resolver 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9ebd6c2-fd86-471a-bc50-b1b89f701fab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f4ad2846396e3e59cd4729d3410038495b2edcd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399714"
---
# <a name="the-resolver-class"></a><span data-ttu-id="5dcbc-102">冲突解决程序类</span><span class="sxs-lookup"><span data-stu-id="5dcbc-102">The Resolver Class</span></span>
<span data-ttu-id="5dcbc-103">**冲突解决程序**类是公开的名称/值对的简单结构。</span><span class="sxs-lookup"><span data-stu-id="5dcbc-103">The **Resolver** class is a simple structure that exposes a name/value pair.</span></span> <span data-ttu-id="5dcbc-104">解析程序 Web 服务从其方法返回此类的实例的泛型集合。</span><span class="sxs-lookup"><span data-stu-id="5dcbc-104">The Resolver Web service returns a generic collection of instances of this class from its methods.</span></span>  
  
 <span data-ttu-id="5dcbc-105">ESB 核心安装程序安装并注册**Microsoft.Practices.ESB.Resolver.dll**与全局程序集缓存中的冲突解决程序类的程序集。</span><span class="sxs-lookup"><span data-stu-id="5dcbc-105">The ESB Core installer installs and registers the **Microsoft.Practices.ESB.Resolver.dll** assembly with Resolver class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="5dcbc-106">使用基于字典的名称/值方法的使其更易于在将来添加新项释放并避免依赖于该解析方法和当前的冲突解决程序类型的非相关属性的包含解析结果的大小降至最低。</span><span class="sxs-lookup"><span data-stu-id="5dcbc-106">The use of a dictionary-based name/value approach makes it easier to add new items in future releases and minimizes the size of the resolution result by avoiding inclusion of non-relevant properties that depend on the resolution method and the current resolver type.</span></span>  
  
 <span data-ttu-id="5dcbc-107">**冲突解决程序**类公开两个属性：</span><span class="sxs-lookup"><span data-stu-id="5dcbc-107">The **Resolver** class exposes two properties:</span></span>  
  
-   <span data-ttu-id="5dcbc-108">**名称**。</span><span class="sxs-lookup"><span data-stu-id="5dcbc-108">**Name**.</span></span> <span data-ttu-id="5dcbc-109">这是包含解决的连接字符串后返回的信息的名称/值对的名称。</span><span class="sxs-lookup"><span data-stu-id="5dcbc-109">This is the name of a name/value pair that contains information that is returned after a connection string is resolved.</span></span>  
  
-   <span data-ttu-id="5dcbc-110">**值**。</span><span class="sxs-lookup"><span data-stu-id="5dcbc-110">**Value**.</span></span> <span data-ttu-id="5dcbc-111">这是名称/值对的名称对应的值。</span><span class="sxs-lookup"><span data-stu-id="5dcbc-111">This is the value that corresponds to the name of the name/value pair.</span></span>