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
# <a name="order-of-records-and-fields"></a>记录和字段的顺序
BizTalk 映射器使用的可扩展样式表语言转换 (XSLT) 不能确保输出元素和属性的输出顺序。 这是因为 BizTalk 映射器是通过以下方式生成 XSLT 的：检查目标架构结构，然后将元素通过网格页传播回来，以便从源架构结构中提取值。 例如，如果希望创建的输出文件中包含的 BillTo Address 记录列于 ShipTo Address 记录之前，则必须确保在目标架构中 BillTo Address 记录位于 ShipTo Address 记录之前。  
  
> [!IMPORTANT]
>  元素和属性在输出实例消息中的显示顺序取决于相应目标架构中记录和字段的顺序。  
  
## <a name="see-also"></a>另请参阅  
 [地图](../core/maps.md)   
 [创建使用 BizTalk 映射程序图](../core/creating-maps-using-biztalk-mapper.md)