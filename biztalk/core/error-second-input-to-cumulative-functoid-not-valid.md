---
title: 错误-第二个输入无效的累计 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputToCumulativeNotValid
ms.assetid: e41a58a7-e0a2-4284-bd19-279578a8915d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ae68d06fbdadae35cef199215c1e9861b37dd19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388458"
---
# <a name="error---second-input-to-cumulative-functoid-not-valid"></a><span data-ttu-id="df814-102">错误-第二个输入无效的累计 Functoid</span><span class="sxs-lookup"><span data-stu-id="df814-102">Error - Second Input to Cumulative Functoid Not Valid</span></span>
<span data-ttu-id="df814-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="df814-103">**Error Code**</span></span>  
  
 <span data-ttu-id="df814-104">btm1031</span><span class="sxs-lookup"><span data-stu-id="df814-104">btm1031</span></span>  
  
 <span data-ttu-id="df814-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="df814-105">**Explanation**</span></span>  
  
 <span data-ttu-id="df814-106">所指示**累计**functoid 具有无效的第二个输入的参数。</span><span class="sxs-lookup"><span data-stu-id="df814-106">The indicated **Cumulative** functoid has a second input parameter that is not valid.</span></span> <span data-ttu-id="df814-107">累计 functoid 的第二个输入的参数必须是一个正整数，用于指示对其执行累计的源架构中的范围。</span><span class="sxs-lookup"><span data-stu-id="df814-107">The second input parameter to cumulative functoids must be a positive integer that indicates the range within the source schema over which the accumulation will be performed.</span></span>  
  
 <span data-ttu-id="df814-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="df814-108">**User Action**</span></span>  
  
 <span data-ttu-id="df814-109">选择所指示**累计**functoid，单击省略号 (**...**) 按钮与相关联**顺序 Functoid 输入**属性在 microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，然后在**配置\<Functoid\>Functoid**对话框框中，确保第二个输入的参数，如果有的话，是一个正整数。</span><span class="sxs-lookup"><span data-stu-id="df814-109">Select the indicated **Cumulative** functoid, click the ellipsis (**...**) button associated with the **Order Functoid Inputs** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, ensure that the second input parameter, if any, is a positive integer.</span></span>