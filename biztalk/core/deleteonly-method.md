---
title: DeleteOnly 方法 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DeleteOnly method
ms.assetid: 99e1d7af-1450-439b-882f-de677e593bee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3982c67b4c2eb572a57a4ad602b1d302f9b53ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239717"
---
# <a name="deleteonly-method"></a><span data-ttu-id="6e06d-102">DeleteOnly 方法</span><span class="sxs-lookup"><span data-stu-id="6e06d-102">DeleteOnly Method</span></span>
<span data-ttu-id="6e06d-103">可以删除集合中的项。</span><span class="sxs-lookup"><span data-stu-id="6e06d-103">Allows you to delete items in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e06d-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e06d-104">Syntax</span></span>  
  
```  
DeleteOnly(key1, key2, ..., keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e06d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6e06d-105">Parameters</span></span>  
  
|<span data-ttu-id="6e06d-106">参数</span><span class="sxs-lookup"><span data-stu-id="6e06d-106">Parameter</span></span>|<span data-ttu-id="6e06d-107">Description</span><span class="sxs-lookup"><span data-stu-id="6e06d-107">Description</span></span>|  
|---------------|-----------------|  
|`key`|<span data-ttu-id="6e06d-108">是一套必须提供的参数。</span><span class="sxs-lookup"><span data-stu-id="6e06d-108">Is a set of parameters that must be supplied.</span></span> <span data-ttu-id="6e06d-109">此组的密钥必须存在于服务器数据库，或发生错误。</span><span class="sxs-lookup"><span data-stu-id="6e06d-109">This set of keys must exist in the server database, or an error occurs.</span></span> <span data-ttu-id="6e06d-110">这些键对应于为特定组件接口定义的一组 Get 键。</span><span class="sxs-lookup"><span data-stu-id="6e06d-110">These keys correspond to the set of Get Keys as defined for the particular component interface.</span></span>|  
|`correctionMode`|<span data-ttu-id="6e06d-111">布尔型标志。</span><span class="sxs-lookup"><span data-stu-id="6e06d-111">A Boolean flag.</span></span> <span data-ttu-id="6e06d-112">何时设置为 true，将集合中允许的过去生效日期的项目的删除。</span><span class="sxs-lookup"><span data-stu-id="6e06d-112">When set to true, allows deletion of past effective-dated items in a collection.</span></span> <span data-ttu-id="6e06d-113">具体而言，它允许在当前的生效日期之前具有 EFFDT 的项删除。</span><span class="sxs-lookup"><span data-stu-id="6e06d-113">Specifically, it allows the deletion of items that have EFFDT prior to the current effective date.</span></span> <span data-ttu-id="6e06d-114">如果此标志未设置为 TRUE，则对这些项目的任何修改将导致从 PeopleSoft 服务器返回错误。</span><span class="sxs-lookup"><span data-stu-id="6e06d-114">Without this flag set to TRUE, any modification to these items results in an error returned from PeopleSoft server.</span></span> <span data-ttu-id="6e06d-115">**注意：** `correctionMode`有关包含有效日期项这些组件接口仅公开自变量。</span><span class="sxs-lookup"><span data-stu-id="6e06d-115">**Note:**  The `correctionMode` argument is only exposed for those component interfaces that contain effective-dated items.</span></span> <span data-ttu-id="6e06d-116">否则它将不显示作为自变量的一部分。</span><span class="sxs-lookup"><span data-stu-id="6e06d-116">Otherwise it is not shown as part of the argument.</span></span>|  
|`interactiveMode`|<span data-ttu-id="6e06d-117">用于处理错误。</span><span class="sxs-lookup"><span data-stu-id="6e06d-117">Used for error handling.</span></span><br /><br /> <span data-ttu-id="6e06d-118">PeopleSoft 企业 BizTalk 适配器时访问组件接口中的属性，使用 PeopleSoft 提供 Api，它读取和写入单个字段中的组件接口;但是，这些更改将不会传播到 PeopleSoft server 一个一次。</span><span class="sxs-lookup"><span data-stu-id="6e06d-118">When accessing properties in a component interface, the BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft-provided APIs, which read and write individual fields in the component interface; however, these changes are not propagated to the PeopleSoft server one at a time.</span></span> <span data-ttu-id="6e06d-119">相反，（与之 PeopleSoft 企业 BizTalk 适配器交互） psjoa.jar 包的所有更改，并将所做的更改发送到一个包中的服务器。</span><span class="sxs-lookup"><span data-stu-id="6e06d-119">Instead, the psjoa.jar (with which the BizTalk Adapter for PeopleSoft Enterprise interacts) packages all the changes and sends the changes to the server in one package.</span></span> <span data-ttu-id="6e06d-120">如果各个更新中有任何一个失败，则会返回一般错误，但未指明确切问题。</span><span class="sxs-lookup"><span data-stu-id="6e06d-120">If any of the individual updates fail, a generic error is returned, which does not pinpoint the actual error.</span></span> <span data-ttu-id="6e06d-121">将交互模式设置为 TRUE 时，每个字段更新都会单独发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="6e06d-121">With the interactive mode set to TRUE, every field update is sent to the server individually.</span></span> <span data-ttu-id="6e06d-122">这样会对性能产生实质影响，但是在更新失败的情况下（例如，如果使用无效的值设置字段）会提供特定错误信息。</span><span class="sxs-lookup"><span data-stu-id="6e06d-122">This has a substantial impact on performance, but it does provide specific error information if the update fails (for example, if an invalid value is used for setting a field).</span></span><br /><br /> <span data-ttu-id="6e06d-123">`interactiveMode` 参数提供了最大的性能，并且可以提供字段更新级别的错误报告。</span><span class="sxs-lookup"><span data-stu-id="6e06d-123">The `interactiveMode` parameter provides maximum performance and provides error reporting at the field-update level.</span></span> <span data-ttu-id="6e06d-124">要正确使用此功能，建议您将 `interactiveMode` 设置为 FALSE 来进行常规调用。</span><span class="sxs-lookup"><span data-stu-id="6e06d-124">To use this feature properly, it is recommended that you make normal calls with `interactiveMode` set to FALSE.</span></span> <span data-ttu-id="6e06d-125">这应该不会对性能带来影响。</span><span class="sxs-lookup"><span data-stu-id="6e06d-125">There should be no impact on performance.</span></span> <span data-ttu-id="6e06d-126">如果返回错误，相同的调用可以重试 interactiveMode 标志设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="6e06d-126">If an error is returned, the same call can be retried with the interactiveMode flag set to TRUE.</span></span> <span data-ttu-id="6e06d-127">调用失败时，服务器将返回更准确的错误消息。</span><span class="sxs-lookup"><span data-stu-id="6e06d-127">When the call fails, the server returns a more precise error message.</span></span>|  
|`properties`|<span data-ttu-id="6e06d-128">包含服务器存在的结构的子集。</span><span class="sxs-lookup"><span data-stu-id="6e06d-128">Contains a subset of the structure that exists on the server.</span></span> <span data-ttu-id="6e06d-129">使所有项将都删除。</span><span class="sxs-lookup"><span data-stu-id="6e06d-129">All items that are leaves are deleted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e06d-130">注释</span><span class="sxs-lookup"><span data-stu-id="6e06d-130">Remarks</span></span>  
 <span data-ttu-id="6e06d-131">属性具有相同的数据类型作为`CreateEx`或`UpdateEx`方法的此组件接口; 但是，只有键的值很重要。</span><span class="sxs-lookup"><span data-stu-id="6e06d-131">The properties have the same data type as the `CreateEx` or `UpdateEx` methods of this component interface; however, only the key values are important.</span></span> <span data-ttu-id="6e06d-132">非键值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="6e06d-132">The non-key values are ignored.</span></span> <span data-ttu-id="6e06d-133">密钥的值必须与那些在服务器上进行匹配，否则将引发异常。</span><span class="sxs-lookup"><span data-stu-id="6e06d-133">The key values must match those on the server, otherwise an exception is raised.</span></span>  
  
 <span data-ttu-id="6e06d-134">下面演示了如何使用密钥的值。</span><span class="sxs-lookup"><span data-stu-id="6e06d-134">The following demonstrates the use of the key values.</span></span> <span data-ttu-id="6e06d-135">如果集合包含的项：</span><span class="sxs-lookup"><span data-stu-id="6e06d-135">If a collection contains the items:</span></span>  
  
-   <span data-ttu-id="6e06d-136">item0</span><span class="sxs-lookup"><span data-stu-id="6e06d-136">item0</span></span>  
  
-   <span data-ttu-id="6e06d-137">item1</span><span class="sxs-lookup"><span data-stu-id="6e06d-137">item1</span></span>  
  
-   <span data-ttu-id="6e06d-138">item2</span><span class="sxs-lookup"><span data-stu-id="6e06d-138">item2</span></span>  
  
-   <span data-ttu-id="6e06d-139">item3</span><span class="sxs-lookup"><span data-stu-id="6e06d-139">item3</span></span>  
  
 <span data-ttu-id="6e06d-140">通过提供 item1 和 item3 属性中的密钥，可以删除 item1 和 item3:</span><span class="sxs-lookup"><span data-stu-id="6e06d-140">You can delete item1 and item3 by providing the keys of item1 and item3 in the properties:</span></span>  
  
-   <span data-ttu-id="6e06d-141">item1</span><span class="sxs-lookup"><span data-stu-id="6e06d-141">item1</span></span>  
  
-   <span data-ttu-id="6e06d-142">item3</span><span class="sxs-lookup"><span data-stu-id="6e06d-142">item3</span></span>  
  
 <span data-ttu-id="6e06d-143">在调用后，服务器集合中具有的剩余的项：</span><span class="sxs-lookup"><span data-stu-id="6e06d-143">After the call, the server has the remaining items in the collection:</span></span>  
  
-   <span data-ttu-id="6e06d-144">item0</span><span class="sxs-lookup"><span data-stu-id="6e06d-144">item0</span></span>  
  
-   <span data-ttu-id="6e06d-145">item2</span><span class="sxs-lookup"><span data-stu-id="6e06d-145">item2</span></span>  
  
 <span data-ttu-id="6e06d-146">第二个示例显示包含其他集合的项：</span><span class="sxs-lookup"><span data-stu-id="6e06d-146">The second example shows the items containing other collections:</span></span>  
  
-   <span data-ttu-id="6e06d-147">item0</span><span class="sxs-lookup"><span data-stu-id="6e06d-147">item0</span></span>  
  
    -   <span data-ttu-id="6e06d-148">item0a</span><span class="sxs-lookup"><span data-stu-id="6e06d-148">item0a</span></span>  
  
-   <span data-ttu-id="6e06d-149">item1</span><span class="sxs-lookup"><span data-stu-id="6e06d-149">item1</span></span>  
  
    -   <span data-ttu-id="6e06d-150">item1a</span><span class="sxs-lookup"><span data-stu-id="6e06d-150">item1a</span></span>  
  
    -   <span data-ttu-id="6e06d-151">item1b</span><span class="sxs-lookup"><span data-stu-id="6e06d-151">item1b</span></span>  
  
    -   <span data-ttu-id="6e06d-152">item1c</span><span class="sxs-lookup"><span data-stu-id="6e06d-152">item1c</span></span>  
  
-   <span data-ttu-id="6e06d-153">item2</span><span class="sxs-lookup"><span data-stu-id="6e06d-153">item2</span></span>  
  
    -   <span data-ttu-id="6e06d-154">item2a</span><span class="sxs-lookup"><span data-stu-id="6e06d-154">item2a</span></span>  
  
    -   <span data-ttu-id="6e06d-155">item2b</span><span class="sxs-lookup"><span data-stu-id="6e06d-155">item2b</span></span>  
  
 <span data-ttu-id="6e06d-156">可以通过从而键提供对 item1b 及 item2 删除 item1b 及其所有 item2:</span><span class="sxs-lookup"><span data-stu-id="6e06d-156">You can delete item1b and all of item2 by giving the keys to item1b and item2:</span></span>  
  
-   <span data-ttu-id="6e06d-157">item1</span><span class="sxs-lookup"><span data-stu-id="6e06d-157">item1</span></span>  
  
    -   <span data-ttu-id="6e06d-158">item1b</span><span class="sxs-lookup"><span data-stu-id="6e06d-158">item1b</span></span>  
  
-   <span data-ttu-id="6e06d-159">item2</span><span class="sxs-lookup"><span data-stu-id="6e06d-159">item2</span></span>  
  
 <span data-ttu-id="6e06d-160">通过提供 item2 空子集合，你将其转换叶和删除该整个子分支。</span><span class="sxs-lookup"><span data-stu-id="6e06d-160">By providing an empty sub-collection for item2, you turn it into a leaf and that entire sub-branch is deleted.</span></span> <span data-ttu-id="6e06d-161">在调用后，服务器具有的剩余的项：</span><span class="sxs-lookup"><span data-stu-id="6e06d-161">After the call, the server has the remaining items:</span></span>  
  
-   <span data-ttu-id="6e06d-162">item0</span><span class="sxs-lookup"><span data-stu-id="6e06d-162">item0</span></span>  
  
    -   <span data-ttu-id="6e06d-163">item0a</span><span class="sxs-lookup"><span data-stu-id="6e06d-163">item0a</span></span>  
  
-   <span data-ttu-id="6e06d-164">item1</span><span class="sxs-lookup"><span data-stu-id="6e06d-164">item1</span></span>  
  
    -   <span data-ttu-id="6e06d-165">item1a</span><span class="sxs-lookup"><span data-stu-id="6e06d-165">item1a</span></span>  
  
    -   <span data-ttu-id="6e06d-166">item1c</span><span class="sxs-lookup"><span data-stu-id="6e06d-166">item1c</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e06d-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e06d-167">See Also</span></span>  
 [<span data-ttu-id="6e06d-168">附录 a： 组件接口方法</span><span class="sxs-lookup"><span data-stu-id="6e06d-168">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)