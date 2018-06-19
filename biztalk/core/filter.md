---
title: 筛选器 |Microsoft 文档
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
ms.openlocfilehash: efa69998b1782f42d7730744fd88534d26a87835
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245797"
---
# <a name="filter"></a><span data-ttu-id="0e692-102">“筛选器”</span><span class="sxs-lookup"><span data-stu-id="0e692-102">Filter</span></span>
<span data-ttu-id="0e692-103">`Filter`元素包含`Expression`计算结果为`true`或`false`并确定当处理或跳过事件。</span><span class="sxs-lookup"><span data-stu-id="0e692-103">The `Filter` element contains an `Expression` that evaluates to `true` or `false` and determines when an event should be processed or skipped.</span></span>  
  
## <a name="format"></a><span data-ttu-id="0e692-104">格式</span><span class="sxs-lookup"><span data-stu-id="0e692-104">Format</span></span>  
  
```  
<ic:Filter>  
</ic:Filter>  
```  
  
## <a name="remarks"></a><span data-ttu-id="0e692-105">注释</span><span class="sxs-lookup"><span data-stu-id="0e692-105">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e692-106">示例</span><span class="sxs-lookup"><span data-stu-id="0e692-106">Example</span></span>  
 <span data-ttu-id="0e692-107">下面的示例定义了一个筛选器，当与相应事件相关的工作流的用户密钥等于“DocumentUrl”时，此筛选器的计算结果为 `true`：</span><span class="sxs-lookup"><span data-stu-id="0e692-107">The following example defines a filter that evaluates to `true` when the user key for the workflow associated with the event equals "DocumentUrl":</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0e692-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e692-108">See Also</span></span>  
 [<span data-ttu-id="0e692-109">拦截器 OnEvent 元素</span><span class="sxs-lookup"><span data-stu-id="0e692-109">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)