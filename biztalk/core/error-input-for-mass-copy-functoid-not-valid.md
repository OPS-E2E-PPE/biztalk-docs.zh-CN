---
title: 错误-输入不是有效的批量复制 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.massCopyInputNotValid
ms.assetid: 141c45cd-79da-4f99-abb0-60a88dfcab76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac2fab02dc9d28f7ba85a05261ec22754315872
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348098"
---
# <a name="error---input-for-mass-copy-functoid-not-valid"></a><span data-ttu-id="d9bee-102">错误-输入不是有效的批量复制 Functoid</span><span class="sxs-lookup"><span data-stu-id="d9bee-102">Error - Input for Mass Copy Functoid Not Valid</span></span>
<span data-ttu-id="d9bee-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="d9bee-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d9bee-104">btm1069</span><span class="sxs-lookup"><span data-stu-id="d9bee-104">btm1069</span></span>  
  
 <span data-ttu-id="d9bee-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="d9bee-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d9bee-106">为相关的输入的参数**批量复制**functoid 不是有效或为相关的输入的参数过多**批量复制**functoid 指定。</span><span class="sxs-lookup"><span data-stu-id="d9bee-106">The input parameter for the relevant **Mass Copy** functoid is not valid or too many input parameters for the relevant **Mass Copy** functoid have been specified.</span></span> <span data-ttu-id="d9bee-107">**批量复制**functoid 只能有一个输入： 从链接**记录**源架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="d9bee-107">**Mass Copy** functoids must have exactly one input: a link from a **Record** node in the source schema.</span></span>  
  
 <span data-ttu-id="d9bee-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="d9bee-108">**User Action**</span></span>  
  
 <span data-ttu-id="d9bee-109">重新配置的相关**批量复制**functoid，以便它具有一个输入的参数从**记录**源架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="d9bee-109">Reconfigure the relevant **Mass Copy** functoid such that it has a single input parameter from a **Record** node in the source schema.</span></span>