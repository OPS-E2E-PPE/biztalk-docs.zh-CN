---
title: 附录 c： 使用组件接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enterprise Integration Points
- EIP
- component interfaces
ms.assetid: 2e3bc5ef-24ea-4e09-8e95-31feefaf5536
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df03df6a1e36fd988109ebe85913512916b4222e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968902"
---
# <a name="appendix-c-using-component-interfaces"></a><span data-ttu-id="94d67-102">附录 c： 使用组件接口</span><span class="sxs-lookup"><span data-stu-id="94d67-102">Appendix C: Using Component Interfaces</span></span>
<span data-ttu-id="94d67-103">本部分中的主题介绍如何创建新的组件接口以及如何修改现有组件接口，以便与用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器一起使用。</span><span class="sxs-lookup"><span data-stu-id="94d67-103">The topics in this section describe how to create new component interfaces—and how to modify existing component interfaces—for use with Microsoft BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="94d67-104">这些主题还介绍了如何对这些组件接口应用安全设置以及如何测试它们。</span><span class="sxs-lookup"><span data-stu-id="94d67-104">They also describe how to apply security to those component interfaces and how to test them.</span></span>  
  
 <span data-ttu-id="94d67-105">您可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="94d67-105">You can do the following:</span></span>  
  
- <span data-ttu-id="94d67-106">将 PeopleSoft 提供的组件接口与应用程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="94d67-106">Use component interfaces supplied by PeopleSoft with your application.</span></span>  
  
   <span data-ttu-id="94d67-107">组件接口也称作“企业集成点”(EIP)。</span><span class="sxs-lookup"><span data-stu-id="94d67-107">Component interfaces also are known as Enterprise Integration Points (EIP).</span></span>  
  
- <span data-ttu-id="94d67-108">修改现有的组件接口。</span><span class="sxs-lookup"><span data-stu-id="94d67-108">Modify an existing component interface.</span></span>  
  
- <span data-ttu-id="94d67-109">创建新的组件接口。</span><span class="sxs-lookup"><span data-stu-id="94d67-109">Create a new component interface.</span></span>  
  
  <span data-ttu-id="94d67-110">在使用组件接口前，必须应用并测试安全设置。</span><span class="sxs-lookup"><span data-stu-id="94d67-110">Before using your component interface, you must apply and test security.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94d67-111">本部分仅为补充内容，用于提供帮助，不能代替 PeopleSoft 文档使用。</span><span class="sxs-lookup"><span data-stu-id="94d67-111">This section is intended as a helpful supplement; it is not a substitute for PeopleSoft documentation.</span></span> <span data-ttu-id="94d67-112">有关 PeopleSoft 组件接口的完整的最新信息，请参阅 PeopleSoft Online Library。</span><span class="sxs-lookup"><span data-stu-id="94d67-112">For complete and up-to-date information about PeopleSoft component interfaces, see the PeopleSoft Online Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94d67-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="94d67-113">In This Section</span></span>  
  
-   [<span data-ttu-id="94d67-114">如何创建组件接口</span><span class="sxs-lookup"><span data-stu-id="94d67-114">How to Create Component Interfaces</span></span>](../core/how-to-create-component-interfaces.md)  
  
-   [<span data-ttu-id="94d67-115">组件接口中的标准方法</span><span class="sxs-lookup"><span data-stu-id="94d67-115">Standard Methods in Component Interfaces</span></span>](../core/standard-methods-in-component-interfaces.md)  
  
-   [<span data-ttu-id="94d67-116">如何帮助保护组件接口</span><span class="sxs-lookup"><span data-stu-id="94d67-116">How to Help Secure Component Interfaces</span></span>](../core/how-to-help-secure-component-interfaces.md)  
  
-   [<span data-ttu-id="94d67-117">如何测试组件接口</span><span class="sxs-lookup"><span data-stu-id="94d67-117">How to Test Component Interfaces</span></span>](../core/how-to-test-component-interfaces.md)