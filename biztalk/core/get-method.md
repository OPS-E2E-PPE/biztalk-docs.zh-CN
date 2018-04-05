---
title: Get 方法 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Get method
ms.assetid: 0e621077-f0ef-495c-ba6b-0c6154f48113
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d56b060cc261f707a4aa7b0d6a496a62707c4dca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-method"></a><span data-ttu-id="3c464-102">Get 方法</span><span class="sxs-lookup"><span data-stu-id="3c464-102">Get Method</span></span>
<span data-ttu-id="3c464-103">用于检索属性基于输入的密钥参数 (key1、 key2，...</span><span class="sxs-lookup"><span data-stu-id="3c464-103">Used to retrieve properties based on the input key parameters (key1, key2, …</span></span> <span data-ttu-id="3c464-104">keyn)。</span><span class="sxs-lookup"><span data-stu-id="3c464-104">keyn).</span></span> <span data-ttu-id="3c464-105">输出参数是一个结构，该结构包含与关键字参数匹配的记录的属性。</span><span class="sxs-lookup"><span data-stu-id="3c464-105">The output parameter is a structure containing the properties of the record that matches the key parameters.</span></span> <span data-ttu-id="3c464-106">如果组件接口具有只有一个实例 （即，没有任何键） 的 Get 函数中不包含任何关键参数。</span><span class="sxs-lookup"><span data-stu-id="3c464-106">If the component interface has only one instance (that is, there is no key), the Get function does not contain any key parameter.</span></span> <span data-ttu-id="3c464-107">另请参阅[Find 方法](../core/find-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3c464-107">Also see [Find Method](../core/find-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c464-108">语法</span><span class="sxs-lookup"><span data-stu-id="3c464-108">Syntax</span></span>  
  
```  
Get (key1, key2, ... keyn, properties)  
Get (key1, key2, ... keyn, getHistoryItems, properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c464-109">Parameters</span><span class="sxs-lookup"><span data-stu-id="3c464-109">Parameters</span></span>  
  
|<span data-ttu-id="3c464-110">参数</span><span class="sxs-lookup"><span data-stu-id="3c464-110">Parameter</span></span>|<span data-ttu-id="3c464-111">Description</span><span class="sxs-lookup"><span data-stu-id="3c464-111">Description</span></span>|  
|---------------|-----------------|  
|`key`|<span data-ttu-id="3c464-112">一组必须存在于服务器数据库中; 的参数否则将出现错误。</span><span class="sxs-lookup"><span data-stu-id="3c464-112">A set of parameters that must exist in the server database; otherwise an error occurs.</span></span> <span data-ttu-id="3c464-113">按照对特殊组件接口进行的定义，这些关键字对应于 Get 关键字组。</span><span class="sxs-lookup"><span data-stu-id="3c464-113">These keys correspond to the set of Get Keys as defined for the particular Component Interface.</span></span>|  
|`properties`|<span data-ttu-id="3c464-114">包含组件接口属性的完整结构，在调用完成时会返回此结构。</span><span class="sxs-lookup"><span data-stu-id="3c464-114">Contains a complete structure of the component interface properties, which is returned upon completion of the call.</span></span>|  
|`getHistoryItems`|<span data-ttu-id="3c464-115">一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="3c464-115">A Boolean value.</span></span> <span data-ttu-id="3c464-116">如果组件接口的属性包含级别 0 以下的有效日期项（即，名为 EFFDT 的关键字段），则还需要附加参数 `getHistoryItems`。</span><span class="sxs-lookup"><span data-stu-id="3c464-116">If the properties of the component interface contain effective-dated items below level 0 (that is, a key field with a name of EFFDT) the `getHistoryItems` additional parameter is required.</span></span><br /><br /> <span data-ttu-id="3c464-117">如果值为：</span><span class="sxs-lookup"><span data-stu-id="3c464-117">If the value is:</span></span><br /><br /> <span data-ttu-id="3c464-118">-True-所有有效的发布日期为项返回为一系列 （它无法在任何级别中嵌入）。</span><span class="sxs-lookup"><span data-stu-id="3c464-118">-   True—All effective dated items are returned as a sequence (which could be embedded in any level).</span></span> <span data-ttu-id="3c464-119">其中包括所有过去的有效日期项、当前的有效日期项以及所有将来的有效日期项</span><span class="sxs-lookup"><span data-stu-id="3c464-119">These include all past effective dated items, the current effective dated item, as well as all future effective dated items</span></span><br /><span data-ttu-id="3c464-120">-False-返回仅当前和将来的所有有效过时的项目。</span><span class="sxs-lookup"><span data-stu-id="3c464-120">-   False—Only the current and all future effective dated items are returned.</span></span> <span data-ttu-id="3c464-121">如果在同一个实例上更新的后续调用将进行，然后`getHistoryItems`应设置为 False。</span><span class="sxs-lookup"><span data-stu-id="3c464-121">If subsequent calls to update on the same instance will be made, then `getHistoryItems` should be set to False.</span></span>|  
  
### <a name="remarks"></a><span data-ttu-id="3c464-122">注释</span><span class="sxs-lookup"><span data-stu-id="3c464-122">Remarks</span></span>  
 <span data-ttu-id="3c464-123">如果组件接口的属性包含级别 0 以下的有效日期项（即，名为 EFFDT 的关键字段），则还需要一个附加参数 `getHistoryItems`。</span><span class="sxs-lookup"><span data-stu-id="3c464-123">If the properties of the component interface contain effective dated items below level 0 (that is, a key field with a name of EFFDT), an additional parameter, `getHistoryItems`, is required.</span></span> <span data-ttu-id="3c464-124">此参数为布尔型。</span><span class="sxs-lookup"><span data-stu-id="3c464-124">This parameter is of type Boolean.</span></span> <span data-ttu-id="3c464-125">如果将其设置为 True，则所有有效日期项将作为一个序列（可嵌入到任意级别）返回。</span><span class="sxs-lookup"><span data-stu-id="3c464-125">If it is set to True, all effective dated items are returned as a sequence (which could be embedded in any level).</span></span> <span data-ttu-id="3c464-126">其中包括所有过去的有效日期项、当前的有效日期项以及所有将来的有效日期项。</span><span class="sxs-lookup"><span data-stu-id="3c464-126">These include all past effective dated items, the current effective dated item, as well as all future effective dated items.</span></span> <span data-ttu-id="3c464-127">如果将 `getHistoryItems` 参数设置为 False，则只会返回当前和所有将来的有效日期项。</span><span class="sxs-lookup"><span data-stu-id="3c464-127">If the `getHistoryItems` parameter is set to False, only the current and all future effective dated items are returned.</span></span> <span data-ttu-id="3c464-128">如果将来还会对同一实例调用更新，则应将 `getHistoryItems` 设置为 False。</span><span class="sxs-lookup"><span data-stu-id="3c464-128">If subsequent calls to update on the same instance are to be made, then `getHistoryItems` should be set to False.</span></span> <span data-ttu-id="3c464-129">另请参阅[UpdateEx 方法](../core/updateex-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3c464-129">See also [UpdateEx Method](../core/updateex-method.md).</span></span>  
  
 <span data-ttu-id="3c464-130">如果组件接口没有关键字（即，仅存在一个实例），则 `Get()` 方法的形式如下：</span><span class="sxs-lookup"><span data-stu-id="3c464-130">If the component interface does not have a key, as in the case where only one instance can exist, then the `Get()` method has the form:</span></span>  
  
```  
Get(properties)  
```  
  
 <span data-ttu-id="3c464-131">有关有效日期项的详细信息，请参阅 PeopleSoft Enterprise 文档。</span><span class="sxs-lookup"><span data-stu-id="3c464-131">For more information on effective dated items, see the PeopleSoft Enterprise documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c464-132">PeopleSoft 企业 BizTalk 适配器`Get()`提供方法是，如果 PeopleSoft`Get`启用组件界面中的函数。</span><span class="sxs-lookup"><span data-stu-id="3c464-132">The BizTalk Adapter for PeopleSoft Enterprise `Get()` method is provided if the PeopleSoft `Get` function in the component interface is enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c464-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c464-133">See Also</span></span>  
 [<span data-ttu-id="3c464-134">附录 a： 组件接口方法</span><span class="sxs-lookup"><span data-stu-id="3c464-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)