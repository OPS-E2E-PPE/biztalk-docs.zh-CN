---
title: 警告-使用自定义 XSLT 和扩展的 XML |Microsoft 文档
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
ms.openlocfilehash: 90644aec738345e3a36286cc62aaa7a355e04348
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288581"
---
# <a name="warning---using-custom-xslt-and-extension-xml"></a><span data-ttu-id="ea208-102">警告-使用自定义 XSLT 和扩展 XML</span><span class="sxs-lookup"><span data-stu-id="ea208-102">Warning - Using Custom XSLT and Extension XML</span></span>
<span data-ttu-id="ea208-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="ea208-103">**Error Code**</span></span>  
  
 <span data-ttu-id="ea208-104">btm1035</span><span class="sxs-lookup"><span data-stu-id="ea208-104">btm1035</span></span>  
  
 <span data-ttu-id="ea208-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="ea208-105">**Explanation**</span></span>  
  
 <span data-ttu-id="ea208-106">值替代存在**自定义 XSLT 路径**和**自定义扩展 XML**属性控制此映射，完全忽略任何映射生成的输出实例消息指定源和目标架构之间。</span><span class="sxs-lookup"><span data-stu-id="ea208-106">The presence of override values for the **Custom XSLT Path** and **Custom Extension XML** properties is controlling the output instance messages produced by this map, completely ignoring any mappings specified between the source and destination schemas.</span></span> <span data-ttu-id="ea208-107">如果是故意如此，则可忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="ea208-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="ea208-108">这是有效的一种情况是使用 BizTalk 映射程序来生成的映射的初步 XSLT，修改此 XSLT 手动来满足特定的其他要求，然后指定作为的值的修改后的文件**自定义 XSLT 路径**属性，从而在后续的映射操作期间替代初级 XSLT。</span><span class="sxs-lookup"><span data-stu-id="ea208-108">One scenario in which this is valid is to use BizTalk Mapper to generate preliminary XSLT for the mapping, modify this XSLT by hand to meet specific additional requirements, and then specify the modified file as the value of the **Custom XSLT Path** property, thereby overriding the preliminary XSLT during subsequent mapping operations.</span></span>  
  
 <span data-ttu-id="ea208-109">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="ea208-109">**User Action**</span></span>  
  
 <span data-ttu-id="ea208-110">如果不打算重写此映射内指定的映射，删除的替代值**自定义 XSLT 路径**属性和**自定义扩展 XML**属性，根据需要。</span><span class="sxs-lookup"><span data-stu-id="ea208-110">If you do not intend to override the mapping specified within this map, remove the override values for the **Custom XSLT Path** property and the **Custom Extension XML** property, as appropriate.</span></span>