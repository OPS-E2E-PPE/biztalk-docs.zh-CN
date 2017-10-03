---
title: "CreateEx 方法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: CreateEx method
ms.assetid: b62bbe25-b24d-42a7-a44c-c83521a6f0a6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b163bfbe7811c37208297aa0a61bfe91cabacde4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="createex-method"></a><span data-ttu-id="6c2d2-102">CreateEx 方法</span><span class="sxs-lookup"><span data-stu-id="6c2d2-102">CreateEx Method</span></span>
<span data-ttu-id="6c2d2-103">使用一组唯一的项和指定的属性创建新记录。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-103">Creates a new record using a set of unique keys and specified properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c2d2-104">语法</span><span class="sxs-lookup"><span data-stu-id="6c2d2-104">Syntax</span></span>  
  
```  
CreateEx  
(key1, key2, ..., keyn, interactiveMode, properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c2d2-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6c2d2-105">Parameters</span></span>  
  
|<span data-ttu-id="6c2d2-106">参数</span><span class="sxs-lookup"><span data-stu-id="6c2d2-106">Parameter</span></span>|<span data-ttu-id="6c2d2-107">Description</span><span class="sxs-lookup"><span data-stu-id="6c2d2-107">Description</span></span>|  
|---------------|-----------------|  
|`Key in/out parameter`|<span data-ttu-id="6c2d2-108">各个项参数（key1、key2...keyn），必须提供。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-108">Individual key parameters (key1, key2, ... keyn), which must be supplied.</span></span><br /><br /> <span data-ttu-id="6c2d2-109">此项集不得存在于服务器数据库中，即它们必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-109">This set of keys must not exist in the server database, that is, they must be unique.</span></span><br /><br /> <span data-ttu-id="6c2d2-110">这些项对应于为特定组件接口定义的“CreateEx”项集。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-110">These keys correspond to the set of CreateEx Keys as defined for the particular component interface.</span></span>|  
|`interactiveMode`|<span data-ttu-id="6c2d2-111">错误处理。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-111">Error handling.</span></span><br /><br /> <span data-ttu-id="6c2d2-112">访问组件接口中的属性时，用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用 PeopleSoft 提供的 API，这些 API 可以读取和写入组件接口中的各个字段；但是，这些更改不会一次一个地传播到 PeopleSoft 服务器上。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-112">When accessing properties in a component interface, Microsoft BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft-provided APIs, which read and write individual fields in the component interface; however, these changes are not propagated to the PeopleSoft server one at a time.</span></span> <span data-ttu-id="6c2d2-113">相反，（与之 PeopleSoft 企业 BizTalk 适配器交互） psjoa.jar 包的所有更改，并将所做的更改发送到一个包中的服务器。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-113">Instead, the psjoa.jar (with which the BizTalk Adapter for PeopleSoft Enterprise interacts) packages all the changes and sends the changes to the server in one package.</span></span><br /><br /> <span data-ttu-id="6c2d2-114">如果各个更新中有任何一个失败，则会返回一般错误，但未指明确切问题。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-114">If any of the individual updates fail, a generic error is returned, which does not pinpoint the actual error.</span></span> <span data-ttu-id="6c2d2-115">将交互模式设置为 TRUE 时，每个字段更新都会单独发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-115">With the interactive mode set to TRUE, every field update is sent to the server individually.</span></span> <span data-ttu-id="6c2d2-116">这样会对性能产生实质影响，但是在更新失败的情况下（例如，如果使用无效的值设置字段）会提供特定错误信息。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-116">This has a substantial impact on performance, but it does provide specific error information if the update fails (for example, if an invalid value is used for setting a field).</span></span><br /><br /> <span data-ttu-id="6c2d2-117">interactiveMode 提供最佳性能，并在字段更新级别提供错误报告。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-117">The interactiveMode provides maximum performance and provides error reporting at the field update level.</span></span> <span data-ttu-id="6c2d2-118">若要正确使用此功能，建议将 interactiveMode 设置为 FALSE 的情况下进行正常调用。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-118">To use this feature properly, it is recommended that normal calls be made with the interactiveMode set to FALSE.</span></span> <span data-ttu-id="6c2d2-119">这应该不会对性能带来影响。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-119">There should be no impact on performance.</span></span> <span data-ttu-id="6c2d2-120">如果返回错误，相同的调用可以重试 interactiveMode 标志设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-120">If an error is returned, the same call can be retried with the interactiveMode flag set to TRUE.</span></span> <span data-ttu-id="6c2d2-121">调用失败时，服务器将返回更准确的错误消息。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-121">When the call fails, the server returns a more precise error message.</span></span>|  
|`properties`|<span data-ttu-id="6c2d2-122">包含组件接口所有属性的结构。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-122">A structure that contains all the properties of the component interface.</span></span> <span data-ttu-id="6c2d2-123">当调用 `CreateEx` 方法时，这些属性会插入到使用特定项创建的记录中。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-123">When the `CreateEx` method is called, these properties are inserted into the record created with the specified key(s).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c2d2-124">注释</span><span class="sxs-lookup"><span data-stu-id="6c2d2-124">Remarks</span></span>  
 <span data-ttu-id="6c2d2-125">在某些情况下，通常的做法是在不具有显示项集的情况下调用 `CreateEx()`，由 `CreateEx` 函数返回这些项。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-125">In some situations, it is common practice to call `CreateEx()` without a set of explicit keys, but the `CreateEx` function returns the keys.</span></span> <span data-ttu-id="6c2d2-126">在服务器上触发的 PeopleCode 支持此行为。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-126">This behavior is supported with PeopleCode that gets triggered on the server.</span></span> <span data-ttu-id="6c2d2-127">例如，若要创建采购订单，客户端可能不知道下一个可用的 PO 编号。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-127">For example, to create a purchase order, the client may not know what the next available PO number is.</span></span> <span data-ttu-id="6c2d2-128">通过将 NEXT 指定为 PO 编号项，调用会触发 PeopleCode，这将确定下一个可用 PO 编号。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-128">By specifying NEXT as the PO number key, the call triggers PeopleCode, which determines the next available PO number.</span></span> <span data-ttu-id="6c2d2-129">此信息必须返回到调用客户端（使用 in/out 项参数）。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-129">This information must be returned to the calling client, using the in/out key parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c2d2-130">此机制发挥作用，键还必须是 0 级的属性。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-130">For this mechanism to work, the key must also be a property at level 0.</span></span> <span data-ttu-id="6c2d2-131">否则，返回原始的密钥。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-131">Otherwise, the original key is returned.</span></span>  
  
 <span data-ttu-id="6c2d2-132">如果启用组件接口中的 PeopleSoft 创建和保存功能，则会提供用于 PeopleSoft Enterprise 的 BizTalk 适配器 `CreateEx()` 方法。</span><span class="sxs-lookup"><span data-stu-id="6c2d2-132">The BizTalk Adapter for PeopleSoft Enterprise `CreateEx()` method is provided if the PeopleSoft Create and Save functions in the component interface are enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c2d2-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c2d2-133">See Also</span></span>  
 [<span data-ttu-id="6c2d2-134">附录 a： 组件接口方法</span><span class="sxs-lookup"><span data-stu-id="6c2d2-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)