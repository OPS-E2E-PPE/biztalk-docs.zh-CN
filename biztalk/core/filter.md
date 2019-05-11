---
title: 筛选器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8dad59d-4a47-4794-bbf9-cba02fe7f0bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5366385056383fd260fb80e2e6fa8b3f842ac48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388002"
---
# <a name="filter"></a><span data-ttu-id="e2c7d-102">“筛选器”</span><span class="sxs-lookup"><span data-stu-id="e2c7d-102">Filter</span></span>
<span data-ttu-id="e2c7d-103">`Filter`元素包含`Expression`的计算结果为`true`或`false`并确定当处理或跳过事件。</span><span class="sxs-lookup"><span data-stu-id="e2c7d-103">The `Filter` element contains an `Expression` that evaluates to `true` or `false` and determines when an event should be processed or skipped.</span></span>  
  
## <a name="format"></a><span data-ttu-id="e2c7d-104">格式</span><span class="sxs-lookup"><span data-stu-id="e2c7d-104">Format</span></span>  
  
```  
<ic:Filter>  
</ic:Filter>  
```  
  
## <a name="remarks"></a><span data-ttu-id="e2c7d-105">备注</span><span class="sxs-lookup"><span data-stu-id="e2c7d-105">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2c7d-106">示例</span><span class="sxs-lookup"><span data-stu-id="e2c7d-106">Example</span></span>  
 <span data-ttu-id="e2c7d-107">下面的示例定义筛选器的计算结果为`true`当工作流与事件关联的用户密钥等于"DocumentUrl":</span><span class="sxs-lookup"><span data-stu-id="e2c7d-107">The following example defines a filter that evaluates to `true` when the user key for the workflow associated with the event equals "DocumentUrl":</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>DocumentUrl</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2c7d-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2c7d-108">See Also</span></span>  
 [<span data-ttu-id="e2c7d-109">侦听器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="e2c7d-109">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)