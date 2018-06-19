---
title: 错误-必填字段都不需要输入 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.reqdFieldHasNoInput
ms.assetid: 2454baf8-aa28-4b7b-93cd-aab9afc63823
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 343b565dec1ee3d0bc2487bd32ea3854cbacb3bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240173"
---
# <a name="error---required-field-has-no-input"></a><span data-ttu-id="07fe4-102">错误-必填的字段具有没有输入</span><span class="sxs-lookup"><span data-stu-id="07fe4-102">Error - Required Field Has No Input</span></span>
<span data-ttu-id="07fe4-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="07fe4-103">**Error Code**</span></span>  
  
 <span data-ttu-id="07fe4-104">btm1028</span><span class="sxs-lookup"><span data-stu-id="07fe4-104">btm1028</span></span>  
  
 <span data-ttu-id="07fe4-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="07fe4-105">**Explanation**</span></span>  
  
 <span data-ttu-id="07fe4-106">目标架构中所指示的节点被指定为必需节点，但当前未提供任何传入链接、常数值或默认值，因此此映射生成的输出实例消息中将不包含该节点。</span><span class="sxs-lookup"><span data-stu-id="07fe4-106">The indicated node in the destination schema is specified as required, yet has no incoming link, constant value, or default value, and thus will not be included in output instance messages provided by this map.</span></span>  
  
 <span data-ttu-id="07fe4-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="07fe4-107">**User Action**</span></span>  
  
 <span data-ttu-id="07fe4-108">根据需要，将目标架构中所指示的节点更改为可选节点，或为该节点提供传入链接、常数值或默认值。</span><span class="sxs-lookup"><span data-stu-id="07fe4-108">As appropriate, either change the indicated node in the destination schema to optional, or provide an incoming link, constant value, or default value for it.</span></span>