---
title: 警告-使用自定义 XSLT 和扩展 XML |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.usingCustomXsltAndExtensionXML
ms.assetid: b86da5fb-6435-4e3b-89b6-d9d036b5152b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce44d40fd726731261536b622fdb9b24c65f4281
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393635"
---
# <a name="warning---using-custom-xslt-and-extension-xml"></a><span data-ttu-id="61171-102">警告-使用自定义 XSLT 和扩展 XML</span><span class="sxs-lookup"><span data-stu-id="61171-102">Warning - Using Custom XSLT and Extension XML</span></span>
<span data-ttu-id="61171-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="61171-103">**Error Code**</span></span>  
  
 <span data-ttu-id="61171-104">btm1035</span><span class="sxs-lookup"><span data-stu-id="61171-104">btm1035</span></span>  
  
 <span data-ttu-id="61171-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="61171-105">**Explanation**</span></span>  
  
 <span data-ttu-id="61171-106">替代值**自定义 XSLT 路径**并**自定义扩展 XML**属性控制此映射，完全忽略任何映射生成的输出实例消息指定源和目标架构之间。</span><span class="sxs-lookup"><span data-stu-id="61171-106">The presence of override values for the **Custom XSLT Path** and **Custom Extension XML** properties is controlling the output instance messages produced by this map, completely ignoring any mappings specified between the source and destination schemas.</span></span> <span data-ttu-id="61171-107">如果这是有意为之，你可以忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="61171-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="61171-108">这是有效的一种方案是使用 BizTalk 映射器来生成初级 XSLT 的映射，修改此 XSLT 手动以满足特定的其他要求，并作为的值指定修改后的文件**自定义 XSLT 路径**属性，从而在随后的映射操作过程中替代初级 XSLT。</span><span class="sxs-lookup"><span data-stu-id="61171-108">One scenario in which this is valid is to use BizTalk Mapper to generate preliminary XSLT for the mapping, modify this XSLT by hand to meet specific additional requirements, and then specify the modified file as the value of the **Custom XSLT Path** property, thereby overriding the preliminary XSLT during subsequent mapping operations.</span></span>  
  
 <span data-ttu-id="61171-109">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="61171-109">**User Action**</span></span>  
  
 <span data-ttu-id="61171-110">如果不打算重写此映射内指定的映射，删除的替代值**自定义 XSLT 路径**属性和**自定义扩展 XML**属性，根据需要。</span><span class="sxs-lookup"><span data-stu-id="61171-110">If you do not intend to override the mapping specified within this map, remove the override values for the **Custom XSLT Path** property and the **Custom Extension XML** property, as appropriate.</span></span>