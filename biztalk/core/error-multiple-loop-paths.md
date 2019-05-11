---
title: 错误-多个循环路径 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleLoopPaths
ms.assetid: 3f7c0c1c-5aaa-4da9-99ab-78bac536b8dd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02461c4e9fb86bb0c2c902be394b08840172c4d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388612"
---
# <a name="error---multiple-loop-paths"></a><span data-ttu-id="deb61-102">错误-多个循环路径</span><span class="sxs-lookup"><span data-stu-id="deb61-102">Error - Multiple Loop Paths</span></span>
<span data-ttu-id="deb61-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="deb61-103">**Error Code**</span></span>  
  
 <span data-ttu-id="deb61-104">btm1030</span><span class="sxs-lookup"><span data-stu-id="deb61-104">btm1030</span></span>  
  
 <span data-ttu-id="deb61-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="deb61-105">**Explanation**</span></span>  
  
 <span data-ttu-id="deb61-106">目标架构中所指示的节点具有多个源循环路径。</span><span class="sxs-lookup"><span data-stu-id="deb61-106">The indicated node in the destination schema has multiple source loop paths.</span></span>  
  
 <span data-ttu-id="deb61-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="deb61-107">**User Action**</span></span>  
  
 <span data-ttu-id="deb61-108">使用**循环**functoid 用于显式对其将执行循环将源架构中指定的节点。</span><span class="sxs-lookup"><span data-stu-id="deb61-108">Use a **Looping** functoid to explicitly specify the node in the source schema over which the looping will be performed.</span></span>