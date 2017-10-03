---
title: "附录 a： 组件接口方法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- component interfaces, methods
- methods, component interfaces
- component interface methods
ms.assetid: c8377589-fbdf-4287-b822-53263a00381d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cb5b87cb063f22c889291b8eff3b2be50d64a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-a-component-interface-methods"></a><span data-ttu-id="26bf8-102">附录 a： 组件接口方法</span><span class="sxs-lookup"><span data-stu-id="26bf8-102">Appendix A: Component Interface Methods</span></span>
<span data-ttu-id="26bf8-103">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器提供了组件接口的标准方法。</span><span class="sxs-lookup"><span data-stu-id="26bf8-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise provides standard methods for component interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26bf8-104">各种方法的 Ex 版本中的 `interactiveMode` 参数有助于调试对后端（`Create/CreateEx`、`Update/UpdateEx` 和 `DeleteOnly`）的调用。</span><span class="sxs-lookup"><span data-stu-id="26bf8-104">The `interactiveMode` parameter, in the Ex-version of the methods, assists in debugging a call to the back-end (`Create/CreateEx`, `Update/UpdateEx`, and `DeleteOnly`).</span></span> <span data-ttu-id="26bf8-105">对后端的 *Ex 调用中的每个项都是单独调用的，因此您完全知道哪个项失败。</span><span class="sxs-lookup"><span data-stu-id="26bf8-105">Each item in the *Ex call to the back-end is called separately, so you know exactly which item failed.</span></span> <span data-ttu-id="26bf8-106">当你使用存在将导致性能降低\*Ex 方法因为每个属性项收到一个单独的调用。</span><span class="sxs-lookup"><span data-stu-id="26bf8-106">There is a decrease in performance when you use an \*Ex method because each property's item receives a separate call.</span></span> <span data-ttu-id="26bf8-107">你可以开发\*Ex 方法，然后切换到 main 方法 (例如， `Create`) 用于生产。</span><span class="sxs-lookup"><span data-stu-id="26bf8-107">You can develop with \*Ex method and then switch to the main method (for example, `Create`) for production.</span></span> <span data-ttu-id="26bf8-108">你还可以使用在用于生产调试交换机切换使用方法和\*Ex 方法。</span><span class="sxs-lookup"><span data-stu-id="26bf8-108">You can also use a debug switch at production to switch between using the method and the \*Ex method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="26bf8-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="26bf8-109">In This Section</span></span>  
  
-   [<span data-ttu-id="26bf8-110">CreateEx 方法</span><span class="sxs-lookup"><span data-stu-id="26bf8-110">CreateEx Method</span></span>](../core/createex-method.md)  
  
-   [<span data-ttu-id="26bf8-111">DeleteOnly 方法</span><span class="sxs-lookup"><span data-stu-id="26bf8-111">DeleteOnly Method</span></span>](../core/deleteonly-method.md)  
  
-   [<span data-ttu-id="26bf8-112">Find 方法</span><span class="sxs-lookup"><span data-stu-id="26bf8-112">Find Method</span></span>](../core/find-method.md)  
  
-   [<span data-ttu-id="26bf8-113">Get 方法</span><span class="sxs-lookup"><span data-stu-id="26bf8-113">Get Method</span></span>](../core/get-method.md)  
  
-   [<span data-ttu-id="26bf8-114">UpdateEx 方法</span><span class="sxs-lookup"><span data-stu-id="26bf8-114">UpdateEx Method</span></span>](../core/updateex-method.md)  
  
-   [<span data-ttu-id="26bf8-115">组件接口用户定义的方法</span><span class="sxs-lookup"><span data-stu-id="26bf8-115">Component Interface User-Defined Methods</span></span>](../core/component-interface-user-defined-methods.md)  
  
-   [<span data-ttu-id="26bf8-116">生效日期属性</span><span class="sxs-lookup"><span data-stu-id="26bf8-116">Effective Date Properties</span></span>](../core/effective-date-properties.md)