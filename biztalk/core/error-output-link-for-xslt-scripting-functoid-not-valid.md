---
title: 错误-XSLT 脚本 Functoid 不是有效的输出链接 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.outputLinkForXsltNotValid
ms.assetid: cdf8e779-6cf6-4d9c-8655-f8b406498fb7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd597a3953db76087086c7ea9038e9fa1fd87eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---output-link-for-xslt-scripting-functoid-not-valid"></a><span data-ttu-id="c54da-102">错误-XSLT 脚本 Functoid 不是有效的输出链接</span><span class="sxs-lookup"><span data-stu-id="c54da-102">Error - Output Link For XSLT Scripting Functoid Not Valid</span></span>
<span data-ttu-id="c54da-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="c54da-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c54da-104">btm1075</span><span class="sxs-lookup"><span data-stu-id="c54da-104">btm1075</span></span>  
  
 <span data-ttu-id="c54da-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="c54da-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c54da-106">相关的输出链接**脚本**functoid 配置为使用内联 XSLT 或 XSLT 调用模板无效。</span><span class="sxs-lookup"><span data-stu-id="c54da-106">The output link of the relevant **Scripting** functoid configured to use inline XSLT or an XSLT Call Template is not valid.</span></span> <span data-ttu-id="c54da-107">此类的输出**脚本**functoid 必须连接直接到目标架构中的节点 （而非另一个 functoid，例如）。</span><span class="sxs-lookup"><span data-stu-id="c54da-107">The output of such **Scripting** functoids must be connected directly to a node in the destination schema (and not to another functoid, for example).</span></span>  
  
 <span data-ttu-id="c54da-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="c54da-108">**User Action**</span></span>  
  
 <span data-ttu-id="c54da-109">确保从相关连接输出链接**脚本**functoid 直接到目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="c54da-109">Ensure that you connect the output link from the relevant **Scripting** functoid directly to a node in the destination schema.</span></span>