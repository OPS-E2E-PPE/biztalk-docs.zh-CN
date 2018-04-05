---
title: 警告-自定义 XSLT 但没有自定义扩展 XML |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.customXsltButNoCustomExtensionXML
ms.assetid: af008ac2-e9ae-4753-a5ba-bf4dbb711a4e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b67591e0e0dbb6b3ecac9aee1566c3245c9969a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="warning---custom-xslt-but-no-custom-extension-xml"></a><span data-ttu-id="6dec5-102">警告-自定义 XSLT 但没有自定义扩展 XML</span><span class="sxs-lookup"><span data-stu-id="6dec5-102">Warning - Custom XSLT but No Custom Extension XML</span></span>
<span data-ttu-id="6dec5-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="6dec5-103">**Error Code**</span></span>  
  
 <span data-ttu-id="6dec5-104">btm1034</span><span class="sxs-lookup"><span data-stu-id="6dec5-104">btm1034</span></span>  
  
 <span data-ttu-id="6dec5-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="6dec5-105">**Explanation**</span></span>  
  
 <span data-ttu-id="6dec5-106">**自定义 XSLT 路径**而无需重写属性**自定义扩展 XML**重写的属性。</span><span class="sxs-lookup"><span data-stu-id="6dec5-106">The **Custom XSLT Path** property has been overridden without the **Custom Extension XML** property being overridden.</span></span> <span data-ttu-id="6dec5-107">如果是故意如此，则可忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="6dec5-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="6dec5-108">BizTalk 映射程序将使用指定的 XSLT**自定义 XSLT 路径**属性并生成 dummy 扩展 XML 映射文件。</span><span class="sxs-lookup"><span data-stu-id="6dec5-108">BizTalk Mapper will use the XSLT specified by the **Custom XSLT Path** property and generate a dummy Extension XML mapping file.</span></span> <span data-ttu-id="6dec5-109">如果您对进行调用中提供的自定义 XSLT 从的外部程序集，则必须指定文件使用**自定义扩展 XML**属性，它包含程序集名称映射到的前缀。</span><span class="sxs-lookup"><span data-stu-id="6dec5-109">If you make calls to external assemblies from within the provided custom XSLT, you must specify a file using the **Custom Extension XML** property that contains the prefix to assembly name mapping.</span></span>  
  
 <span data-ttu-id="6dec5-110">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="6dec5-110">**User Action**</span></span>  
  
 <span data-ttu-id="6dec5-111">如果指此警告的情况不是有意的或者提供一个兼容值**自定义扩展 XML**重写值的属性或删除**自定义 XSLT 路径**属性。</span><span class="sxs-lookup"><span data-stu-id="6dec5-111">If the condition indicated by this warning was not intentional, either provide a compatible value for the **Custom Extension XML** property or remove the override value for the **Custom XSLT Path** property.</span></span>