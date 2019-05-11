---
title: 附录 C：使用组件接口 |Microsoft Docs
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
ms.openlocfilehash: 1f15e64837f16701332ff5f527cd14548fbb9974
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359481"
---
# <a name="appendix-c-using-component-interfaces"></a><span data-ttu-id="6feba-102">附录 C：使用组件接口</span><span class="sxs-lookup"><span data-stu-id="6feba-102">Appendix C: Using Component Interfaces</span></span>
<span data-ttu-id="6feba-103">在本部分中的主题介绍如何创建新的组件接口，以及如何修改现有组件接口 — 用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器一起使用。</span><span class="sxs-lookup"><span data-stu-id="6feba-103">The topics in this section describe how to create new component interfaces—and how to modify existing component interfaces—for use with Microsoft BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="6feba-104">它们还描述如何将安全性应用于这些组件接口以及如何对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="6feba-104">They also describe how to apply security to those component interfaces and how to test them.</span></span>  
  
 <span data-ttu-id="6feba-105">您可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6feba-105">You can do the following:</span></span>  
  
- <span data-ttu-id="6feba-106">使用与你的应用程序提供的 PeopleSoft 组件接口。</span><span class="sxs-lookup"><span data-stu-id="6feba-106">Use component interfaces supplied by PeopleSoft with your application.</span></span>  
  
   <span data-ttu-id="6feba-107">组件接口也称作企业集成点 (EIP)。</span><span class="sxs-lookup"><span data-stu-id="6feba-107">Component interfaces also are known as Enterprise Integration Points (EIP).</span></span>  
  
- <span data-ttu-id="6feba-108">修改现有组件接口。</span><span class="sxs-lookup"><span data-stu-id="6feba-108">Modify an existing component interface.</span></span>  
  
- <span data-ttu-id="6feba-109">创建一个新组件接口。</span><span class="sxs-lookup"><span data-stu-id="6feba-109">Create a new component interface.</span></span>  
  
  <span data-ttu-id="6feba-110">然后再使用组件接口，必须将应用和测试安全。</span><span class="sxs-lookup"><span data-stu-id="6feba-110">Before using your component interface, you must apply and test security.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6feba-111">本部分被用于有用补充;它不能代替 PeopleSoft 文档。</span><span class="sxs-lookup"><span data-stu-id="6feba-111">This section is intended as a helpful supplement; it is not a substitute for PeopleSoft documentation.</span></span> <span data-ttu-id="6feba-112">有关 PeopleSoft 组件接口的完整且最新信息，请参阅 PeopleSoft Online Library。</span><span class="sxs-lookup"><span data-stu-id="6feba-112">For complete and up-to-date information about PeopleSoft component interfaces, see the PeopleSoft Online Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6feba-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="6feba-113">In This Section</span></span>  
  
-   [<span data-ttu-id="6feba-114">如何创建组件接口</span><span class="sxs-lookup"><span data-stu-id="6feba-114">How to Create Component Interfaces</span></span>](../core/how-to-create-component-interfaces.md)  
  
-   [<span data-ttu-id="6feba-115">组件接口中的标准方法</span><span class="sxs-lookup"><span data-stu-id="6feba-115">Standard Methods in Component Interfaces</span></span>](../core/standard-methods-in-component-interfaces.md)  
  
-   [<span data-ttu-id="6feba-116">如何帮助保护组件接口</span><span class="sxs-lookup"><span data-stu-id="6feba-116">How to Help Secure Component Interfaces</span></span>](../core/how-to-help-secure-component-interfaces.md)  
  
-   [<span data-ttu-id="6feba-117">如何测试组件接口</span><span class="sxs-lookup"><span data-stu-id="6feba-117">How to Test Component Interfaces</span></span>](../core/how-to-test-component-interfaces.md)