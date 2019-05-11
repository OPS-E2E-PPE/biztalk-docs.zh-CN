---
title: 警告-自定义扩展 XML 但未自定义 XSLT |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.customExtensionXmlButNoCustomXSLT
ms.assetid: 3219c73c-2e58-4fe2-bc6e-2d60348d2415
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d94bea29ee6943ee6b084518e4b4ff404377503
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393729"
---
# <a name="warning---custom-extension-xml-but-no-custom-xslt"></a><span data-ttu-id="5d457-102">警告-自定义扩展 XML 但未自定义 XSLT</span><span class="sxs-lookup"><span data-stu-id="5d457-102">Warning - Custom Extension XML But No Custom XSLT</span></span>
<span data-ttu-id="5d457-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="5d457-103">**Error Code**</span></span>  
  
 <span data-ttu-id="5d457-104">btm1033</span><span class="sxs-lookup"><span data-stu-id="5d457-104">btm1033</span></span>  
  
 <span data-ttu-id="5d457-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="5d457-105">**Explanation**</span></span>  
  
 <span data-ttu-id="5d457-106">**自定义扩展 XML**而无需重写属性**自定义 XSLT 路径**被重写的属性。</span><span class="sxs-lookup"><span data-stu-id="5d457-106">The **Custom Extension XML** property has been overridden without the **Custom XSLT Path** property being overridden.</span></span> <span data-ttu-id="5d457-107">如果这是有意为之，你可以忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="5d457-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="5d457-108">BizTalk 映射器将使用通过编译映射生成的 XSLT 和将还生成扩展 XML 并将其追加到指定的重写的属性的自定义扩展 XML。</span><span class="sxs-lookup"><span data-stu-id="5d457-108">BizTalk Mapper will use the XSLT produced by compiling the map and will also generate the Extension XML and append it to the custom Extension XML specified by the overridden property.</span></span> <span data-ttu-id="5d457-109">当映射包含这很有用**脚本**functoid 使用内联 XSLT 或内联 XSLT 调用模板，可以对一个或多个方法的调用外部程序集中。</span><span class="sxs-lookup"><span data-stu-id="5d457-109">This can be useful when the map contains **Scripting** functoids that use inline XSLT or inline XSLT call templates that make calls to one or more methods in external assemblies.</span></span> <span data-ttu-id="5d457-110">在这种情况下，用户可以然后指定在程序集名称映射前缀**自定义扩展 XML**属性。</span><span class="sxs-lookup"><span data-stu-id="5d457-110">In such cases, the user can then specify the prefix to assembly name mapping in the **Custom Extension XML** property.</span></span>  
  
 <span data-ttu-id="5d457-111">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="5d457-111">**User Action**</span></span>  
  
 <span data-ttu-id="5d457-112">如果此警告所指示的情况不是有意的请提供一个兼容值**自定义 XSLT 路径**的替代值的属性或移除**自定义扩展 XML**属性。</span><span class="sxs-lookup"><span data-stu-id="5d457-112">If the condition indicated by this warning was not intentional, either provide a compatible value for the **Custom XSLT Path** property or remove the override value for the **Custom Extension XML** property.</span></span>