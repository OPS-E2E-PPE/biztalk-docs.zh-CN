---
title: 自定义 XSLT |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Scripting
- maps, customizing
- functoid types, Looping
- maps, extending
- XSLT, maps
- Scripting functoids
- maps, XSLT
- customizing, maps
- maps, replacing
ms.assetid: e254d16d-4d16-4c23-a3ed-cc98eea9939a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7ee93d5cd6deb2b7f5a9b291e6670741f301bd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390041"
---
# <a name="custom-xslt"></a><span data-ttu-id="ad240-102">自定义 XSLT</span><span class="sxs-lookup"><span data-stu-id="ad240-102">Custom XSLT</span></span>
<span data-ttu-id="ad240-103">如果您熟悉可扩展样式表语言转换 (XSLT) 代码，可以使用它进行自定义、 扩展，或替换 BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="ad240-103">If you are familiar with Extensible Stylesheet Language Transformations (XSLT) code, you can use it to customize, extend, or replace BizTalk maps.</span></span> <span data-ttu-id="ad240-104">若要使用 XSLT 的最简单方法是使用**脚本**functoid。</span><span class="sxs-lookup"><span data-stu-id="ad240-104">The simplest way to use XSLT is with the **Scripting** functoid.</span></span> <span data-ttu-id="ad240-105">**脚本**functoid 接受脚本在很多。已启用 NET 的语言，包括 XSLT。</span><span class="sxs-lookup"><span data-stu-id="ad240-105">The **Scripting** functoid accepts scripts in many .NET-enabled languages, including XSLT.</span></span> <span data-ttu-id="ad240-106">有关使用 XSLT 的详细信息**Scripting** functoid，请参阅[脚本使用内联 XSLT 和 XSLT 调用模板](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="ad240-106">For more information about using XSLT with the **Scripting** functoid, see [Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md).</span></span>  
  
 <span data-ttu-id="ad240-107">如果您一直使用要转换为另一个实例消息的 XSLT 代码，可以使用该代码代替 BizTalk 映射直接。</span><span class="sxs-lookup"><span data-stu-id="ad240-107">If you have XSLT code that you have been using to convert one instance message into another, you can use that code directly in place of a BizTalk map.</span></span> <span data-ttu-id="ad240-108">有关使用 XSLT 代码映射替换 BizTalk 有关的信息，请参阅[如何创建在无映射](../core/how-to-create-a-map-without-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="ad240-108">For information about replacing BizTalk maps with your XSLT code, see [How to Create a Map without Maps](../core/how-to-create-a-map-without-maps.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad240-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad240-109">See Also</span></span>  
 <span data-ttu-id="ad240-110">[映射](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="ad240-110">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="ad240-111">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="ad240-111">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)