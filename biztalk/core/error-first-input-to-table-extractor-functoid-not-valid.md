---
title: 错误-表提取程序 Functoid 不是有效第一个输入 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.firstInputToTableExtractorNotValid
ms.assetid: 5b197531-9bf4-49c6-ad3a-b3ba92d37701
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b96e673f33bfa7478b633c8254a62d81335cd61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348312"
---
# <a name="error---first-input-to-table-extractor-functoid-not-valid"></a><span data-ttu-id="85183-102">错误-第一个输入无效的表提取程序 Functoid</span><span class="sxs-lookup"><span data-stu-id="85183-102">Error - First Input to Table Extractor Functoid Not Valid</span></span>
<span data-ttu-id="85183-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="85183-103">**Error Code**</span></span>  
  
 <span data-ttu-id="85183-104">btm1019</span><span class="sxs-lookup"><span data-stu-id="85183-104">btm1019</span></span>  
  
 <span data-ttu-id="85183-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="85183-105">**Explanation**</span></span>  
  
 <span data-ttu-id="85183-106">所指示的第一个输入的参数**表提取程序**functoid 不是从链接**表循环**functoid，根据需要。</span><span class="sxs-lookup"><span data-stu-id="85183-106">The first input parameter to the indicated **Table Extractor** functoid is not a link from a **Table Looping** functoid, as required.</span></span>  
  
 <span data-ttu-id="85183-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="85183-107">**User Action**</span></span>  
  
 <span data-ttu-id="85183-108">创建之间所指示的链接**表提取程序**functoid 和相应**表循环**通过将其拖放到其他 functoid。</span><span class="sxs-lookup"><span data-stu-id="85183-108">Create a link between the indicated **Table Extractor** functoid and the appropriate **Table Looping** functoid by dragging one of them to the other.</span></span> <span data-ttu-id="85183-109">以前的 functoid 必须位于右侧的后一种 functoid 在映射网格页。</span><span class="sxs-lookup"><span data-stu-id="85183-109">The former functoid must be located to the right of the latter functoid in a map grid page.</span></span> <span data-ttu-id="85183-110">此外，使用**配置\<Functoid\> Functoid**对话框框中，确保新创建的链接是所指示的第一个输入的参数**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="85183-110">Also, using the **Configure \<Functoid\> Functoid** dialog box, ensure that the newly created link is the first input parameter to the indicated **Table Extractor** functoid.</span></span>