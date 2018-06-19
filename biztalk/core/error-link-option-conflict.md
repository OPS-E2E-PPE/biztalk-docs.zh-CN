---
title: 错误-链接选项冲突 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.linkOptionConflict
ms.assetid: dbad5c00-500b-4931-a54c-8b311fbfda53
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31f5829f971e524a5e4d2c0f443174c6511a6314
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240365"
---
# <a name="error---link-option-conflict"></a><span data-ttu-id="68adc-102">错误-链接选项冲突</span><span class="sxs-lookup"><span data-stu-id="68adc-102">Error - Link Option Conflict</span></span>
<span data-ttu-id="68adc-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="68adc-103">**Error Code**</span></span>  
  
 <span data-ttu-id="68adc-104">btm1022</span><span class="sxs-lookup"><span data-stu-id="68adc-104">btm1022</span></span>  
  
 <span data-ttu-id="68adc-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="68adc-105">**Explanation**</span></span>  
  
 <span data-ttu-id="68adc-106">目标架构中所指示的节点在它们的传入链接中存在编译器指令冲突。</span><span class="sxs-lookup"><span data-stu-id="68adc-106">The indicated nodes in the destination schema have conflicting compiler directives specified for their incoming links.</span></span>  
  
 <span data-ttu-id="68adc-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="68adc-107">**User Action**</span></span>  
  
 <span data-ttu-id="68adc-108">选择指向目标架构中所指示的节点的一个或两个链接，然后在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口中更改它们的编译器指令，使它们兼容。</span><span class="sxs-lookup"><span data-stu-id="68adc-108">Select one or both of the links leading to the indicated nodes in the destination schema and then in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change their compiler directives so that they are compatible.</span></span>