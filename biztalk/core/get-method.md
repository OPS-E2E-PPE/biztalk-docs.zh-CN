---
title: Get 方法 |Microsoft Docs
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
ms.openlocfilehash: 0fbf3b80fce70cac1ac95d21c143cdb64fae6305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345144"
---
# <a name="get-method"></a><span data-ttu-id="625fc-102">Get 方法</span><span class="sxs-lookup"><span data-stu-id="625fc-102">Get Method</span></span>
<span data-ttu-id="625fc-103">用来检索属性基于输入键参数 (key1、 key2，...</span><span class="sxs-lookup"><span data-stu-id="625fc-103">Used to retrieve properties based on the input key parameters (key1, key2, …</span></span> <span data-ttu-id="625fc-104">keyn)。</span><span class="sxs-lookup"><span data-stu-id="625fc-104">keyn).</span></span> <span data-ttu-id="625fc-105">输出参数是记录的一个包含密钥的参数匹配的属性的结构。</span><span class="sxs-lookup"><span data-stu-id="625fc-105">The output parameter is a structure containing the properties of the record that matches the key parameters.</span></span> <span data-ttu-id="625fc-106">如果组件接口只有一个实例 （即，没有任何键），Get 函数不包含任何关键字参数。</span><span class="sxs-lookup"><span data-stu-id="625fc-106">If the component interface has only one instance (that is, there is no key), the Get function does not contain any key parameter.</span></span> <span data-ttu-id="625fc-107">另请参阅[Find 方法](../core/find-method.md)。</span><span class="sxs-lookup"><span data-stu-id="625fc-107">Also see [Find Method](../core/find-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="625fc-108">语法</span><span class="sxs-lookup"><span data-stu-id="625fc-108">Syntax</span></span>  
  
```  
Get (key1, key2, ... keyn, properties)  
Get (key1, key2, ... keyn, getHistoryItems, properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="625fc-109">Parameters</span><span class="sxs-lookup"><span data-stu-id="625fc-109">Parameters</span></span>  
  
|<span data-ttu-id="625fc-110">参数</span><span class="sxs-lookup"><span data-stu-id="625fc-110">Parameter</span></span>|<span data-ttu-id="625fc-111">Description</span><span class="sxs-lookup"><span data-stu-id="625fc-111">Description</span></span>|  
|---------------|-----------------|  
|`key`|<span data-ttu-id="625fc-112">一组必须存在于服务器数据库中; 的参数否则就会出错。</span><span class="sxs-lookup"><span data-stu-id="625fc-112">A set of parameters that must exist in the server database; otherwise an error occurs.</span></span> <span data-ttu-id="625fc-113">这些项对应于 Get 关键字组，为特定组件接口定义。</span><span class="sxs-lookup"><span data-stu-id="625fc-113">These keys correspond to the set of Get Keys as defined for the particular Component Interface.</span></span>|  
|`properties`|<span data-ttu-id="625fc-114">包含组件接口属性，在调用完成时会返回此的完整结构。</span><span class="sxs-lookup"><span data-stu-id="625fc-114">Contains a complete structure of the component interface properties, which is returned upon completion of the call.</span></span>|  
|`getHistoryItems`|<span data-ttu-id="625fc-115">一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="625fc-115">A Boolean value.</span></span> <span data-ttu-id="625fc-116">如果组件接口的属性包含有效日期项级别 0 以下 （即，一个名为 EFFDT 键字段）`getHistoryItems`其他参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="625fc-116">If the properties of the component interface contain effective-dated items below level 0 (that is, a key field with a name of EFFDT) the `getHistoryItems` additional parameter is required.</span></span><br /><br /> <span data-ttu-id="625fc-117">如果值为：</span><span class="sxs-lookup"><span data-stu-id="625fc-117">If the value is:</span></span><br /><br /> <span data-ttu-id="625fc-118">-True-所有有效日期的项返回为一个序列 （可嵌入到任意级别）。</span><span class="sxs-lookup"><span data-stu-id="625fc-118">-   True—All effective dated items are returned as a sequence (which could be embedded in any level).</span></span> <span data-ttu-id="625fc-119">其中包括所有过去的有效日期的项、 当前的有效日期的项，以及所有将来的有效日期的项</span><span class="sxs-lookup"><span data-stu-id="625fc-119">These include all past effective dated items, the current effective dated item, as well as all future effective dated items</span></span><br /><span data-ttu-id="625fc-120">-False，将返回仅当前和所有将来的有效日期的项。</span><span class="sxs-lookup"><span data-stu-id="625fc-120">-   False—Only the current and all future effective dated items are returned.</span></span> <span data-ttu-id="625fc-121">如果在同一实例上更新的后续调用将进行，然后`getHistoryItems`应设置为 False。</span><span class="sxs-lookup"><span data-stu-id="625fc-121">If subsequent calls to update on the same instance will be made, then `getHistoryItems` should be set to False.</span></span>|  
  
### <a name="remarks"></a><span data-ttu-id="625fc-122">备注</span><span class="sxs-lookup"><span data-stu-id="625fc-122">Remarks</span></span>  
 <span data-ttu-id="625fc-123">如果组件接口的属性包含有效日期项级别 0 （即，键字段名称为 EFFDT），以下附加参数， `getHistoryItems`，是必需的。</span><span class="sxs-lookup"><span data-stu-id="625fc-123">If the properties of the component interface contain effective dated items below level 0 (that is, a key field with a name of EFFDT), an additional parameter, `getHistoryItems`, is required.</span></span> <span data-ttu-id="625fc-124">此参数是布尔类型。</span><span class="sxs-lookup"><span data-stu-id="625fc-124">This parameter is of type Boolean.</span></span> <span data-ttu-id="625fc-125">如果设置为 True，所有有效日期的项是作为一个序列 （可嵌入到任意级别） 返回。</span><span class="sxs-lookup"><span data-stu-id="625fc-125">If it is set to True, all effective dated items are returned as a sequence (which could be embedded in any level).</span></span> <span data-ttu-id="625fc-126">其中包括所有过去的有效日期的项、 当前的有效日期的项，以及所有将来的有效日期的项。</span><span class="sxs-lookup"><span data-stu-id="625fc-126">These include all past effective dated items, the current effective dated item, as well as all future effective dated items.</span></span> <span data-ttu-id="625fc-127">如果`getHistoryItems`参数设置为 False，仅返回当前和所有将来的有效日期的项是。</span><span class="sxs-lookup"><span data-stu-id="625fc-127">If the `getHistoryItems` parameter is set to False, only the current and all future effective dated items are returned.</span></span> <span data-ttu-id="625fc-128">如果在同一实例上更新的后续调用都将然后`getHistoryItems`应设置为 False。</span><span class="sxs-lookup"><span data-stu-id="625fc-128">If subsequent calls to update on the same instance are to be made, then `getHistoryItems` should be set to False.</span></span> <span data-ttu-id="625fc-129">另请参阅[UpdateEx 方法](../core/updateex-method.md)。</span><span class="sxs-lookup"><span data-stu-id="625fc-129">See also [UpdateEx Method](../core/updateex-method.md).</span></span>  
  
 <span data-ttu-id="625fc-130">如果组件接口没有键，这其中只有一个实例可以存在，这种情况则`Get()`方法采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="625fc-130">If the component interface does not have a key, as in the case where only one instance can exist, then the `Get()` method has the form:</span></span>  
  
```  
Get(properties)  
```  
  
 <span data-ttu-id="625fc-131">有关有效日期项的详细信息，请参阅 PeopleSoft Enterprise 文档。</span><span class="sxs-lookup"><span data-stu-id="625fc-131">For more information on effective dated items, see the PeopleSoft Enterprise documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="625fc-132">用于 PeopleSoft Enterprise 的 BizTalk 适配器`Get()`方法提供如果 PeopleSoft`Get`启用组件接口中的函数。</span><span class="sxs-lookup"><span data-stu-id="625fc-132">The BizTalk Adapter for PeopleSoft Enterprise `Get()` method is provided if the PeopleSoft `Get` function in the component interface is enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="625fc-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="625fc-133">See Also</span></span>  
 [<span data-ttu-id="625fc-134">附录 a:组件接口方法</span><span class="sxs-lookup"><span data-stu-id="625fc-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)