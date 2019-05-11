---
title: 警告-自定义 XSLT 但未自定义扩展 XML |Microsoft Docs
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
ms.openlocfilehash: a4c44fbe8385717061be1e5d8e81587d6a287b7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393712"
---
# <a name="warning---custom-xslt-but-no-custom-extension-xml"></a><span data-ttu-id="64712-102">警告-自定义 XSLT 但未自定义扩展 XML</span><span class="sxs-lookup"><span data-stu-id="64712-102">Warning - Custom XSLT but No Custom Extension XML</span></span>
<span data-ttu-id="64712-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="64712-103">**Error Code**</span></span>  
  
 <span data-ttu-id="64712-104">btm1034</span><span class="sxs-lookup"><span data-stu-id="64712-104">btm1034</span></span>  
  
 <span data-ttu-id="64712-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="64712-105">**Explanation**</span></span>  
  
 <span data-ttu-id="64712-106">**自定义 XSLT 路径**而无需重写属性**自定义扩展 XML**被重写的属性。</span><span class="sxs-lookup"><span data-stu-id="64712-106">The **Custom XSLT Path** property has been overridden without the **Custom Extension XML** property being overridden.</span></span> <span data-ttu-id="64712-107">如果这是有意为之，你可以忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="64712-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="64712-108">BizTalk 映射器将使用指定的 XSLT**自定义 XSLT 路径**属性并生成虚拟的扩展 XML 映射文件。</span><span class="sxs-lookup"><span data-stu-id="64712-108">BizTalk Mapper will use the XSLT specified by the **Custom XSLT Path** property and generate a dummy Extension XML mapping file.</span></span> <span data-ttu-id="64712-109">如果您进行到外部程序集从提供的自定义 XSLT 内调用，则必须指定文件使用**自定义扩展 XML**包含程序集名称映射前缀的属性。</span><span class="sxs-lookup"><span data-stu-id="64712-109">If you make calls to external assemblies from within the provided custom XSLT, you must specify a file using the **Custom Extension XML** property that contains the prefix to assembly name mapping.</span></span>  
  
 <span data-ttu-id="64712-110">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="64712-110">**User Action**</span></span>  
  
 <span data-ttu-id="64712-111">如果此警告所指示的情况不是有意的请提供一个兼容值**自定义扩展 XML**的替代值的属性或移除**自定义 XSLT 路径**属性。</span><span class="sxs-lookup"><span data-stu-id="64712-111">If the condition indicated by this warning was not intentional, either provide a compatible value for the **Custom Extension XML** property or remove the override value for the **Custom XSLT Path** property.</span></span>