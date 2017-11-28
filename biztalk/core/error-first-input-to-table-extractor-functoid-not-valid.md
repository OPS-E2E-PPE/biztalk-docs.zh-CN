---
title: "错误-第一个输入表提取程序 functoid 无效 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.firstInputToTableExtractorNotValid
ms.assetid: 5b197531-9bf4-49c6-ad3a-b3ba92d37701
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2449f6c5572a3a29b620becdc4310f4152f2eac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---first-input-to-table-extractor-functoid-not-valid"></a><span data-ttu-id="7ef44-102">错误-第一个输入表提取程序 functoid 无效</span><span class="sxs-lookup"><span data-stu-id="7ef44-102">Error - First Input to Table Extractor Functoid Not Valid</span></span>
<span data-ttu-id="7ef44-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="7ef44-103">**Error Code**</span></span>  
  
 <span data-ttu-id="7ef44-104">btm1019</span><span class="sxs-lookup"><span data-stu-id="7ef44-104">btm1019</span></span>  
  
 <span data-ttu-id="7ef44-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ef44-105">**Explanation**</span></span>  
  
 <span data-ttu-id="7ef44-106">第一个输入的参数指示**表提取程序**functoid 不是从一个链接**表循环**functoid，根据需要。</span><span class="sxs-lookup"><span data-stu-id="7ef44-106">The first input parameter to the indicated **Table Extractor** functoid is not a link from a **Table Looping** functoid, as required.</span></span>  
  
 <span data-ttu-id="7ef44-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="7ef44-107">**User Action**</span></span>  
  
 <span data-ttu-id="7ef44-108">指示之间创建链接**表提取程序**functoid 适当**表循环**通过将其拖放到另 functoid。</span><span class="sxs-lookup"><span data-stu-id="7ef44-108">Create a link between the indicated **Table Extractor** functoid and the appropriate **Table Looping** functoid by dragging one of them to the other.</span></span> <span data-ttu-id="7ef44-109">在映射网格页中，“表提取程序”functoid 必须位于“表循环”functoid 的右侧。</span><span class="sxs-lookup"><span data-stu-id="7ef44-109">The former functoid must be located to the right of the latter functoid in a map grid page.</span></span> <span data-ttu-id="7ef44-110">此外，使用**配置\<Functoid > Functoid**对话框框中，确保新创建的链接是为指示的第一个输入的参数**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="7ef44-110">Also, using the **Configure \<Functoid> Functoid** dialog box, ensure that the newly created link is the first input parameter to the indicated **Table Extractor** functoid.</span></span>