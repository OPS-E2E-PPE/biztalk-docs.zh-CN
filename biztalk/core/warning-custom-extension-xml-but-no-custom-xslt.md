---
title: "警告-自定义扩展 XML 但没有自定义 XSLT |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.warning.customExtensionXmlButNoCustomXSLT
ms.assetid: 3219c73c-2e58-4fe2-bc6e-2d60348d2415
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b626f8ede3231c04ae74dc0097cbdf524c90522
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="warning---custom-extension-xml-but-no-custom-xslt"></a><span data-ttu-id="59dbe-102">警告-自定义扩展 XML 但没有自定义 XSLT</span><span class="sxs-lookup"><span data-stu-id="59dbe-102">Warning - Custom Extension XML But No Custom XSLT</span></span>
<span data-ttu-id="59dbe-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="59dbe-103">**Error Code**</span></span>  
  
 <span data-ttu-id="59dbe-104">btm1033</span><span class="sxs-lookup"><span data-stu-id="59dbe-104">btm1033</span></span>  
  
 <span data-ttu-id="59dbe-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="59dbe-105">**Explanation**</span></span>  
  
 <span data-ttu-id="59dbe-106">**自定义扩展 XML**而无需重写属性**自定义 XSLT 路径**重写的属性。</span><span class="sxs-lookup"><span data-stu-id="59dbe-106">The **Custom Extension XML** property has been overridden without the **Custom XSLT Path** property being overridden.</span></span> <span data-ttu-id="59dbe-107">如果是故意如此，则可忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="59dbe-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="59dbe-108">BizTalk 映射器将使用通过编译映射而生成的 XSLT，还将生成扩展 XML 并将其附加到由替代属性指定的自定义扩展 XML 之后。</span><span class="sxs-lookup"><span data-stu-id="59dbe-108">BizTalk Mapper will use the XSLT produced by compiling the map and will also generate the Extension XML and append it to the custom Extension XML specified by the overridden property.</span></span> <span data-ttu-id="59dbe-109">这一点可能很有用，当映射包含**脚本**使用内联 XSLT 或内联 XSLT 的 functoid 调用外部程序集中进行到一个或多个方法调用的模板。</span><span class="sxs-lookup"><span data-stu-id="59dbe-109">This can be useful when the map contains **Scripting** functoids that use inline XSLT or inline XSLT call templates that make calls to one or more methods in external assemblies.</span></span> <span data-ttu-id="59dbe-110">在这种情况下，用户可以然后指定中的程序集名称映射到前缀**自定义扩展 XML**属性。</span><span class="sxs-lookup"><span data-stu-id="59dbe-110">In such cases, the user can then specify the prefix to assembly name mapping in the **Custom Extension XML** property.</span></span>  
  
 <span data-ttu-id="59dbe-111">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="59dbe-111">**User Action**</span></span>  
  
 <span data-ttu-id="59dbe-112">如果指此警告的情况不是有意的或者提供一个兼容值**自定义 XSLT 路径**重写值的属性或删除**自定义扩展 XML**属性。</span><span class="sxs-lookup"><span data-stu-id="59dbe-112">If the condition indicated by this warning was not intentional, either provide a compatible value for the **Custom XSLT Path** property or remove the override value for the **Custom Extension XML** property.</span></span>