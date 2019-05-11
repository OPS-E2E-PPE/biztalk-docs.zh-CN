---
title: 记录和字段的顺序 |Microsoft Docs
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
ms.openlocfilehash: 8bd47208d772489b322d1f23c6b44d7ed552dee2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262609"
---
# <a name="order-of-records-and-fields"></a>记录和字段的顺序
BizTalk 映射器使用的可扩展样式表语言转换 (XSLT) 不能确保输出元素和属性的输出顺序。 这是因为 BizTalk 映射器是通过以下方式生成 XSLT 的：检查目标架构结构，然后将元素通过网格页传播回来，以便从源架构结构中提取值。 例如，如果希望创建的输出文件中包含的 BillTo Address 记录列于 ShipTo Address 记录之前，则必须确保在目标架构中 BillTo Address 记录位于 ShipTo Address 记录之前。  
  
> [!IMPORTANT]
>  元素和属性在输出实例消息中的显示顺序取决于相应目标架构中记录和字段的顺序。  
  
## <a name="see-also"></a>请参阅  
 [映射](../core/maps.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)