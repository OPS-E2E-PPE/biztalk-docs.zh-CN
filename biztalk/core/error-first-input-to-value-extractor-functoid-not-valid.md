---
title: 错误-值提取程序 Functoid 不是有效的第一个输入 |Microsoft Docs
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
ms.openlocfilehash: 8a419cb522a385d83c5e877b14625f8e93c30775
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348350"
---
# <a name="error---first-input-to-value-extractor-functoid-not-valid"></a><span data-ttu-id="941ec-102">错误-值提取程序 Functoid 不是有效的第一个输入</span><span class="sxs-lookup"><span data-stu-id="941ec-102">Error - First Input to Value Extractor Functoid Not Valid</span></span>
<span data-ttu-id="941ec-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="941ec-103">**Error Code**</span></span>  
  
 <span data-ttu-id="941ec-104">btm1002</span><span class="sxs-lookup"><span data-stu-id="941ec-104">btm1002</span></span>  
  
 <span data-ttu-id="941ec-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="941ec-105">**Explanation**</span></span>  
  
 <span data-ttu-id="941ec-106">所指示的第一个输入的参数**值提取程序**functoid 必须是输出 （ADO 记录集），从**数据库查找**functoid。</span><span class="sxs-lookup"><span data-stu-id="941ec-106">The first input parameter to the indicated **Value Extractor** functoid must be the output (an ADO recordset) from the **Database Lookup** functoid.</span></span>  
  
 <span data-ttu-id="941ec-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="941ec-107">**User Action**</span></span>  
  
 <span data-ttu-id="941ec-108">确保所有的第一个输入**值提取程序**functoid 是从一个链接**数据库查找**在映射网格页左侧的 functoid。</span><span class="sxs-lookup"><span data-stu-id="941ec-108">Ensure that the first input to all **Value Extractor** functoids is a link from a **Database Lookup** functoid to their left in a map grid page.</span></span>