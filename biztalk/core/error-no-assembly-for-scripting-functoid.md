---
title: 错误-脚本 Functoid 未设置程序集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.noAssemblyForScriptingFunctoid
ms.assetid: db8fa41c-904c-4789-9522-f3107dbeb087
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b62a1a82c69339c445acdb8172dca5127fa39376
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388544"
---
# <a name="error---no-assembly-for-scripting-functoid"></a><span data-ttu-id="62e68-102">错误-脚本 Functoid 未设置程序集</span><span class="sxs-lookup"><span data-stu-id="62e68-102">Error - No Assembly for Scripting Functoid</span></span>
<span data-ttu-id="62e68-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="62e68-103">**Error Code**</span></span>  
  
 <span data-ttu-id="62e68-104">btm1007</span><span class="sxs-lookup"><span data-stu-id="62e68-104">btm1007</span></span>  
  
 <span data-ttu-id="62e68-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="62e68-105">**Explanation**</span></span>  
  
 <span data-ttu-id="62e68-106">**脚本程序集**属性所指示**脚本**functoid 即使设置**脚本类型**属性指示外部程序集包含此脚本**脚本**functoid。</span><span class="sxs-lookup"><span data-stu-id="62e68-106">The **Script Assembly** property of the indicated **Scripting** functoid has not been set even though the **Script Type** property indicates that an external assembly contains the script for this **Scripting** functoid.</span></span>  
  
 <span data-ttu-id="62e68-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="62e68-107">**User Action**</span></span>  
  
 <span data-ttu-id="62e68-108">选择所指示**Scripting** functoid，单击省略号 (**...**) 按钮与相关联**脚本**属性在 microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后将相应的值设置**配置 Functoid 脚本**对话框中，包括**脚本程序集**属性。</span><span class="sxs-lookup"><span data-stu-id="62e68-108">Select the indicated **Scripting** functoid, click the ellipsis (**...**) button associated with the **Script** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then set the appropriate values in the **Configure Functoid Script** dialog box, including the **Script Assembly** property.</span></span>