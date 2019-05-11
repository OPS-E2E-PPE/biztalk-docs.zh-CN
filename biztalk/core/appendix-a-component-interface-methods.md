---
title: 附录 A：组件接口方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, methods
- methods, component interfaces
- component interface methods
ms.assetid: c8377589-fbdf-4287-b822-53263a00381d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48487071e0c4099158a10b0a7cfb922ad8d75717
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359611"
---
# <a name="appendix-a-component-interface-methods"></a><span data-ttu-id="00b6c-102">附录 A：组件接口方法</span><span class="sxs-lookup"><span data-stu-id="00b6c-102">Appendix A: Component Interface Methods</span></span>
<span data-ttu-id="00b6c-103">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器提供了组件接口的标准方法。</span><span class="sxs-lookup"><span data-stu-id="00b6c-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise provides standard methods for component interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00b6c-104">`interactiveMode`参数的方法的 Ex 版本中有助于调试对后端的调用 (`Create/CreateEx`， `Update/UpdateEx`，和`DeleteOnly`)。</span><span class="sxs-lookup"><span data-stu-id="00b6c-104">The `interactiveMode` parameter, in the Ex-version of the methods, assists in debugging a call to the back-end (`Create/CreateEx`, `Update/UpdateEx`, and `DeleteOnly`).</span></span> <span data-ttu-id="00b6c-105">中的每项 \* Ex 调用到后端分别调用，以便您知道哪一项完全失败。</span><span class="sxs-lookup"><span data-stu-id="00b6c-105">Each item in the \*Ex call to the back-end is called separately, so you know exactly which item failed.</span></span> <span data-ttu-id="00b6c-106">存在使用时是性能降低\*Ex 方法因为每个属性的项都会接收单独调用。</span><span class="sxs-lookup"><span data-stu-id="00b6c-106">There is a decrease in performance when you use an \*Ex method because each property's item receives a separate call.</span></span> <span data-ttu-id="00b6c-107">可以使用开发\*Ex 方法，然后切换到 main 方法 (例如， `Create`) 用于生产。</span><span class="sxs-lookup"><span data-stu-id="00b6c-107">You can develop with \*Ex method and then switch to the main method (for example, `Create`) for production.</span></span> <span data-ttu-id="00b6c-108">您还可以使用在用于生产调试开关使用的方法之间进行切换和\*Ex 方法。</span><span class="sxs-lookup"><span data-stu-id="00b6c-108">You can also use a debug switch at production to switch between using the method and the \*Ex method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="00b6c-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="00b6c-109">In This Section</span></span>  
  
-   [<span data-ttu-id="00b6c-110">CreateEx 方法</span><span class="sxs-lookup"><span data-stu-id="00b6c-110">CreateEx Method</span></span>](../core/createex-method.md)  
  
-   [<span data-ttu-id="00b6c-111">DeleteOnly 方法</span><span class="sxs-lookup"><span data-stu-id="00b6c-111">DeleteOnly Method</span></span>](../core/deleteonly-method.md)  
  
-   [<span data-ttu-id="00b6c-112">Find 方法</span><span class="sxs-lookup"><span data-stu-id="00b6c-112">Find Method</span></span>](../core/find-method.md)  
  
-   [<span data-ttu-id="00b6c-113">Get 方法</span><span class="sxs-lookup"><span data-stu-id="00b6c-113">Get Method</span></span>](../core/get-method.md)  
  
-   [<span data-ttu-id="00b6c-114">UpdateEx 方法</span><span class="sxs-lookup"><span data-stu-id="00b6c-114">UpdateEx Method</span></span>](../core/updateex-method.md)  
  
-   [<span data-ttu-id="00b6c-115">组件接口用户定义的方法</span><span class="sxs-lookup"><span data-stu-id="00b6c-115">Component Interface User-Defined Methods</span></span>](../core/component-interface-user-defined-methods.md)  
  
-   [<span data-ttu-id="00b6c-116">“有效日期”属性</span><span class="sxs-lookup"><span data-stu-id="00b6c-116">Effective Date Properties</span></span>](../core/effective-date-properties.md)