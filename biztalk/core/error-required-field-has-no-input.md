---
title: 错误-必填字段都没有输入 |Microsoft Docs
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
ms.openlocfilehash: 9f7443efd49c5d5375b025fd4fcf93f60d253d4b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346980"
---
# <a name="error---required-field-has-no-input"></a><span data-ttu-id="cb67f-102">错误-必填的字段具有任何输入</span><span class="sxs-lookup"><span data-stu-id="cb67f-102">Error - Required Field Has No Input</span></span>
<span data-ttu-id="cb67f-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="cb67f-103">**Error Code**</span></span>  
  
 <span data-ttu-id="cb67f-104">btm1028</span><span class="sxs-lookup"><span data-stu-id="cb67f-104">btm1028</span></span>  
  
 <span data-ttu-id="cb67f-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="cb67f-105">**Explanation**</span></span>  
  
 <span data-ttu-id="cb67f-106">目标架构中所指示的节点被指定为必需节点，但当前未提供任何传入链接、常数值或默认值，因此此映射生成的输出实例消息中将不包含该节点。</span><span class="sxs-lookup"><span data-stu-id="cb67f-106">The indicated node in the destination schema is specified as required, yet has no incoming link, constant value, or default value, and thus will not be included in output instance messages provided by this map.</span></span>  
  
 <span data-ttu-id="cb67f-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="cb67f-107">**User Action**</span></span>  
  
 <span data-ttu-id="cb67f-108">根据需要，将目标架构中所指示的节点更改为可选节点，或为该节点提供传入链接、常数值或默认值。</span><span class="sxs-lookup"><span data-stu-id="cb67f-108">As appropriate, either change the indicated node in the destination schema to optional, or provide an incoming link, constant value, or default value for it.</span></span>