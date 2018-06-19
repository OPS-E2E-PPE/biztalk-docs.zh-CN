---
title: 记录和字段的顺序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Mapper, sorting
- XSLT, sorting
ms.assetid: 7fa9b5cd-73bc-496f-a081-4a45da3afe42
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5826d46fef73400a5d54e2d1154a1647af85294e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263853"
---
# <a name="order-of-records-and-fields"></a><span data-ttu-id="fe21e-102">记录和字段的顺序</span><span class="sxs-lookup"><span data-stu-id="fe21e-102">Order of Records and Fields</span></span>
<span data-ttu-id="fe21e-103">BizTalk 映射器使用的可扩展样式表语言转换 (XSLT) 不能确保输出元素和属性的输出顺序。</span><span class="sxs-lookup"><span data-stu-id="fe21e-103">Extensible Stylesheet Language Transformations (XSLT), as used by BizTalk Mapper, do not guarantee the output order of output elements and attributes.</span></span> <span data-ttu-id="fe21e-104">这是因为 BizTalk 映射器是通过以下方式生成 XSLT 的：检查目标架构结构，然后将元素通过网格页传播回来，以便从源架构结构中提取值。</span><span class="sxs-lookup"><span data-stu-id="fe21e-104">This is because BizTalk Mapper generates XSLT by examining the destination schema structure, and then propagating elements back through the grid pages to extract values from the source schema structure.</span></span> <span data-ttu-id="fe21e-105">例如，如果希望创建的输出文件中包含的 BillTo Address 记录列于 ShipTo Address 记录之前，则必须确保在目标架构中 BillTo Address 记录位于 ShipTo Address 记录之前。</span><span class="sxs-lookup"><span data-stu-id="fe21e-105">For example, if you want to create an output file that has the BillTo Address record listed before the ShipTo Address record, you must ensure that the BillTo Address precedes the ShipTo Address record in the destination schema.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe21e-106">元素和属性在输出实例消息中的显示顺序取决于相应目标架构中记录和字段的顺序。</span><span class="sxs-lookup"><span data-stu-id="fe21e-106">The order in which elements and attributes appear in an output instance message depends on the order of the records and fields of the corresponding destination schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe21e-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe21e-107">See Also</span></span>  
 <span data-ttu-id="fe21e-108">[地图](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="fe21e-108">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="fe21e-109">创建使用 BizTalk 映射程序图</span><span class="sxs-lookup"><span data-stu-id="fe21e-109">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)