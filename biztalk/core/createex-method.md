---
title: CreateEx 方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CreateEx method
ms.assetid: b62bbe25-b24d-42a7-a44c-c83521a6f0a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23163739b18febd5642a704a6910241928e85730
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390119"
---
# <a name="createex-method"></a><span data-ttu-id="e0d4b-102">CreateEx 方法</span><span class="sxs-lookup"><span data-stu-id="e0d4b-102">CreateEx Method</span></span>
<span data-ttu-id="e0d4b-103">创建新记录使用一组的唯一键和指定的属性。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-103">Creates a new record using a set of unique keys and specified properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0d4b-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0d4b-104">Syntax</span></span>  
  
```  
CreateEx  
(key1, key2, ..., keyn, interactiveMode, properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0d4b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="e0d4b-105">Parameters</span></span>  
  
|<span data-ttu-id="e0d4b-106">参数</span><span class="sxs-lookup"><span data-stu-id="e0d4b-106">Parameter</span></span>|<span data-ttu-id="e0d4b-107">Description</span><span class="sxs-lookup"><span data-stu-id="e0d4b-107">Description</span></span>|  
|---------------|-----------------|  
|`Key in/out parameter`|<span data-ttu-id="e0d4b-108">各个项参数 （key1、 key2，...keyn)，必须提供。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-108">Individual key parameters (key1, key2, ... keyn), which must be supplied.</span></span><br /><br /> <span data-ttu-id="e0d4b-109">服务器数据库中不存在此项集，必须也就是说，它们必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-109">This set of keys must not exist in the server database, that is, they must be unique.</span></span><br /><br /> <span data-ttu-id="e0d4b-110">这些密钥与为特定组件接口定义的 CreateEx 键集相对应。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-110">These keys correspond to the set of CreateEx Keys as defined for the particular component interface.</span></span>|  
|`interactiveMode`|<span data-ttu-id="e0d4b-111">错误处理。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-111">Error handling.</span></span><br /><br /> <span data-ttu-id="e0d4b-112">访问组件接口中的属性时，适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用 PeopleSoft 提供的 Api，它读取和写入组件接口; 中的各个字段但是，这些更改将不会传播到 PeopleSoft 服务器一次。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-112">When accessing properties in a component interface, Microsoft BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft-provided APIs, which read and write individual fields in the component interface; however, these changes are not propagated to the PeopleSoft server one at a time.</span></span> <span data-ttu-id="e0d4b-113">相反，psjoa.jar （与用于 PeopleSoft Enterprise 的 BizTalk 适配器进行交互） 包的所有更改，并将所做的更改发送到一个包中的服务器。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-113">Instead, the psjoa.jar (with which the BizTalk Adapter for PeopleSoft Enterprise interacts) packages all the changes and sends the changes to the server in one package.</span></span><br /><br /> <span data-ttu-id="e0d4b-114">如果任何单个更新失败，一般会返回错误，这不会不找出实际的错误。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-114">If any of the individual updates fail, a generic error is returned, which does not pinpoint the actual error.</span></span> <span data-ttu-id="e0d4b-115">将交互模式设置为 TRUE 时，每个字段更新为发送到服务器单独。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-115">With the interactive mode set to TRUE, every field update is sent to the server individually.</span></span> <span data-ttu-id="e0d4b-116">这对性能，有重大影响，但如果更新失败 （例如，如果无效的值用于设置的字段） 提供特定错误的信息。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-116">This has a substantial impact on performance, but it does provide specific error information if the update fails (for example, if an invalid value is used for setting a field).</span></span><br /><br /> <span data-ttu-id="e0d4b-117">InteractiveMode 提供最佳性能，并提供错误报告字段更新级别。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-117">The interactiveMode provides maximum performance and provides error reporting at the field update level.</span></span> <span data-ttu-id="e0d4b-118">若要正确使用此功能，建议使用 interactiveMode 设置为 FALSE 进行正常调用。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-118">To use this feature properly, it is recommended that normal calls be made with the interactiveMode set to FALSE.</span></span> <span data-ttu-id="e0d4b-119">在性能上应该有任何影响。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-119">There should be no impact on performance.</span></span> <span data-ttu-id="e0d4b-120">如果返回错误，则相同的调用可以重试 interactiveMode 标志设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-120">If an error is returned, the same call can be retried with the interactiveMode flag set to TRUE.</span></span> <span data-ttu-id="e0d4b-121">当调用失败时，服务器将返回更精确的错误消息。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-121">When the call fails, the server returns a more precise error message.</span></span>|  
|`properties`|<span data-ttu-id="e0d4b-122">包含的组件接口的所有属性的结构。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-122">A structure that contains all the properties of the component interface.</span></span> <span data-ttu-id="e0d4b-123">当`CreateEx`方法调用时，这些属性插入到使用特定项创建的记录。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-123">When the `CreateEx` method is called, these properties are inserted into the record created with the specified key(s).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0d4b-124">备注</span><span class="sxs-lookup"><span data-stu-id="e0d4b-124">Remarks</span></span>  
 <span data-ttu-id="e0d4b-125">在某些情况下，它是常见做法调用`CreateEx()`而无需显示项集的但`CreateEx`函数返回的键。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-125">In some situations, it is common practice to call `CreateEx()` without a set of explicit keys, but the `CreateEx` function returns the keys.</span></span> <span data-ttu-id="e0d4b-126">在服务器上触发的 PeopleCode 支持此行为。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-126">This behavior is supported with PeopleCode that gets triggered on the server.</span></span> <span data-ttu-id="e0d4b-127">例如，若要创建采购订单，客户端可能不知道什么是下一个可用 PO 编号。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-127">For example, to create a purchase order, the client may not know what the next available PO number is.</span></span> <span data-ttu-id="e0d4b-128">通过指定为 PO 编号项下一步，调用会触发 PeopleCode，这将确定下一个可用 PO 编号。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-128">By specifying NEXT as the PO number key, the call triggers PeopleCode, which determines the next available PO number.</span></span> <span data-ttu-id="e0d4b-129">此信息必须返回到调用客户端，使用在/out 项参数。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-129">This information must be returned to the calling client, using the in/out key parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0d4b-130">若要运行此机制，该密钥还必须是在级别 0 的属性。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-130">For this mechanism to work, the key must also be a property at level 0.</span></span> <span data-ttu-id="e0d4b-131">否则，返回原始密钥。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-131">Otherwise, the original key is returned.</span></span>  
  
 <span data-ttu-id="e0d4b-132">用于 PeopleSoft Enterprise 的 BizTalk 适配器`CreateEx()`如果启用了组件接口中的 PeopleSoft 创建和保存函数提供方法。</span><span class="sxs-lookup"><span data-stu-id="e0d4b-132">The BizTalk Adapter for PeopleSoft Enterprise `CreateEx()` method is provided if the PeopleSoft Create and Save functions in the component interface are enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d4b-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0d4b-133">See Also</span></span>  
 [<span data-ttu-id="e0d4b-134">附录 a:组件接口方法</span><span class="sxs-lookup"><span data-stu-id="e0d4b-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)