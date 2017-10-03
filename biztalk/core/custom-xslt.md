---
title: "自定义 XSLT |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4adf2abe438b3972419184b1297eaff5578c5bde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="custom-xslt"></a><span data-ttu-id="32f5d-102">自定义 XSLT</span><span class="sxs-lookup"><span data-stu-id="32f5d-102">Custom XSLT</span></span>
<span data-ttu-id="32f5d-103">如果您熟悉可扩展样式表语言转换 (XSLT) 代码，则可以使用此代码自定义、扩展或替换 BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="32f5d-103">If you are familiar with Extensible Stylesheet Language Transformations (XSLT) code, you can use it to customize, extend, or replace BizTalk maps.</span></span> <span data-ttu-id="32f5d-104">若要使用 XSLT 的最简单方法是使用**脚本**functoid。</span><span class="sxs-lookup"><span data-stu-id="32f5d-104">The simplest way to use XSLT is with the **Scripting** functoid.</span></span> <span data-ttu-id="32f5d-105">**脚本**functoid 接受在很多的脚本。NET 启用语言，包括 XSLT。</span><span class="sxs-lookup"><span data-stu-id="32f5d-105">The **Scripting** functoid accepts scripts in many .NET-enabled languages, including XSLT.</span></span> <span data-ttu-id="32f5d-106">有关使用与 XSLT**脚本**functoid，请参阅[脚本使用内联 XSLT 和 XSLT 调用模板](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="32f5d-106">For more information about using XSLT with the **Scripting** functoid, see [Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md).</span></span>  
  
 <span data-ttu-id="32f5d-107">如果您已具有用于将一个实例消息转换为另一个实例消息的 XSLT 代码，则可以直接使用该代码代替 BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="32f5d-107">If you have XSLT code that you have been using to convert one instance message into another, you can use that code directly in place of a BizTalk map.</span></span> <span data-ttu-id="32f5d-108">使用 XSLT 代码映射替换 BizTalk 有关的信息，请参阅[如何创建没有地图图](../core/how-to-create-a-map-without-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="32f5d-108">For information about replacing BizTalk maps with your XSLT code, see [How to Create a Map without Maps](../core/how-to-create-a-map-without-maps.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f5d-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32f5d-109">See Also</span></span>  
 <span data-ttu-id="32f5d-110">[地图](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="32f5d-110">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="32f5d-111">创建使用 BizTalk 映射程序图</span><span class="sxs-lookup"><span data-stu-id="32f5d-111">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)