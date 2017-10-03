---
title: "特定和泛型映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, specific
- maps, generic
ms.assetid: ee26dd13-affb-47c5-961a-f2377129de22
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6ad84e23c3981730ee4cf7655a42d87c46158e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="specific-and-generic-maps"></a>特殊映射与通用映射
在创建转换数据的映射时，你可以创建*特定*或*泛型*映射。  
  
 可以使用特殊映射来满足特定贸易合作伙伴的需求。 当与贸易合作伙伴之间有特殊业务需求或业务协议时，可以使用特殊映射。 特殊映射的优点是：可以对其进行自定义以满足与特定贸易合作伙伴之间的业务功能需求。 特殊映射的缺点是：无法用于多个贸易合作伙伴。 如果将贸易合作伙伴的数量乘以与这些贸易伙伴交换的不同消息类型的数量，您必须分配足够的时间和资源来管理所有关联的映射。  
  
 另一方面，通用映射设计用于多个贸易合作伙伴。 因此，您只需为每种类型的业务文档创建一个架构，然后对所有贸易合作伙伴使用这些架构即可，而无需为特定业务文档开发和维护多个架构。 虽然对多个贸易合作伙伴使用一个映射可以节省时间和资源，但无法对这些映射进行自定义，而且可能无法满足所有情况下的需求。  
  
 根据业务的性质，您所创建的映射可能既有特殊映射也有通用映射。  
  
## <a name="see-also"></a>另请参阅  
 [地图](../core/maps.md)   
 [创建使用 BizTalk 映射程序图](../core/creating-maps-using-biztalk-mapper.md)