---
title: 数据转换 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, data translation
- data translation, about data translation
- data transformation, about data transformation
- maps, data transformation
- data transformation, maps
- data translation, maps
ms.assetid: a6aa5e9a-8d9c-478d-8f69-f9b16ed1a18c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ee1cd9b7e825f210032f7caaaa292496cfa44c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238645"
---
# <a name="data-transformation"></a>数据转换
映射数据依赖于数据转换。  
  
 数据转换是在源架构的记录和字段与目标架构的（通常是不同的）记录和字段之间创建对应关系的过程。 数据转换的一个示例是将采购订单的发运地址信息和帐单邮寄地址信息映射到发票。 这是最基本的映射类型。 数据转换还可以应用于其他操作，例如：  
  
-   对循环记录中的数据求平均值，并将输出发送到目标架构中的单个字段。  
  
-   将字符数据转换为 ASCII 格式。  
  
-   对一个或多个记录中的数据执行加或减操作，并将结果放入目标架构中的单个字段中。  
  
 如果希望将数据从一种格式转换成另一种格式，您会使用管道。 这种转换可以将给定的消息类型转换成现有系统要求的替代格式，在解决企业应用程序集成问题时非常有用，但无法使用映射完成。  
  
## <a name="see-also"></a>另请参阅  
 [地图](../core/maps.md)   
 [创建使用 BizTalk 映射程序图](../core/creating-maps-using-biztalk-mapper.md)