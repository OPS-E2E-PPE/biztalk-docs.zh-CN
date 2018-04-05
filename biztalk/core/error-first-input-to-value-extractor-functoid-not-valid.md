---
title: 错误-第一个输入值不是有效的提取程序 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputValueExtractorNotValid
ms.assetid: 7703ca5f-21aa-441f-8c28-b02da72c25c1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68b143cea7e1d7e99c1d5b378bd9d6619270fb70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---first-input-to-value-extractor-functoid-not-valid"></a><span data-ttu-id="00fe0-102">错误-第一个输入值不是有效的提取程序 Functoid</span><span class="sxs-lookup"><span data-stu-id="00fe0-102">Error - First Input to Value Extractor Functoid Not Valid</span></span>
<span data-ttu-id="00fe0-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="00fe0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="00fe0-104">btm1002</span><span class="sxs-lookup"><span data-stu-id="00fe0-104">btm1002</span></span>  
  
 <span data-ttu-id="00fe0-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="00fe0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="00fe0-106">第一个输入的参数指示**值提取程序**functoid 必须输出 （ADO 记录集），从**数据库查找**functoid。</span><span class="sxs-lookup"><span data-stu-id="00fe0-106">The first input parameter to the indicated **Value Extractor** functoid must be the output (an ADO recordset) from the **Database Lookup** functoid.</span></span>  
  
 <span data-ttu-id="00fe0-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="00fe0-107">**User Action**</span></span>  
  
 <span data-ttu-id="00fe0-108">确保所有的第一个输入**值提取程序**functoid 是从一个链接**数据库查找**functoid 映射网格页在其左侧。</span><span class="sxs-lookup"><span data-stu-id="00fe0-108">Ensure that the first input to all **Value Extractor** functoids is a link from a **Database Lookup** functoid to their left in a map grid page.</span></span>