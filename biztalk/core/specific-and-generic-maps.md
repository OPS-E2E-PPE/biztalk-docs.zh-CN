---
title: 特殊映射与通用映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, specific
- maps, generic
ms.assetid: ee26dd13-affb-47c5-961a-f2377129de22
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69b85658030540ae9b823a5eab32501a200f974c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243207"
---
# <a name="specific-and-generic-maps"></a>特殊映射与通用映射
创建一个映射，以将数据转换时，可以创建*特定*或*泛型*映射。  
  
 使用特殊映射来满足特定贸易合作伙伴的需求。 当与贸易合作伙伴具有非常特定的业务需求或业务协议时，请使用特殊映射。 特殊映射的优点是，它自定义以满足您与特定贸易合作伙伴的业务功能的需求。 特殊映射的缺点是它不能与多个贸易合作伙伴使用。 如果乘贸易合作伙伴的与这些贸易合作伙伴交换的不同的消息类型的数目数必须分配足够的时间和资源来管理所有关联的映射。  
  
 通用映射，但是，旨在与多个贸易合作伙伴一起使用。 因此，而不是开发和维护多个特定的业务文档架构，创建一个用于每种类型的业务文档架构，然后将其用于所有贸易合作伙伴。 虽然多个贸易合作伙伴使用一个映射可以节省时间和资源，这些映射未自定义，可能无法满足所有情况下的需要。  
  
 很可能您将创建特定和泛型的映射，具体取决于你的业务性质。  
  
## <a name="see-also"></a>请参阅  
 [映射](../core/maps.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)