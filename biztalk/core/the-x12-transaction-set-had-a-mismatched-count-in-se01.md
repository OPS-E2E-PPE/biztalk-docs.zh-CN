---
title: "X12 事务集 SE01 中有不匹配的计数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a90079f5-5939-40b6-9756-d7943240c125
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41539f0492f90d3f7276b0d80af28c568593ef4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-x12-transaction-set-had-a-mismatched-count-in-se01"></a>X12 事务集在 SE01 中的计数不匹配
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12StSeCountMismatch|  
|消息正文|X12 事务集在 SE01 中的计数不匹配。 将已 SE01 {0}，而应已 {1}。 此错误已纠正。|  
  
## <a name="explanation"></a>解释  
 此警告表明事务集尾部中的数字（SE01 字段）与交换的事务集中的段数不匹配。 发送管道纠正了 SE01 字段中的计数并发布了此警告。  
  
## <a name="user-action"></a>用户操作  
 无需执行任何操作。