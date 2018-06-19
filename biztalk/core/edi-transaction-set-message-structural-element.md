---
title: EDI 事务集消息结构化元素 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caea8408-c09c-4525-a9c9-18abe4432594
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d49288e9a311c9766e61fe985b9e279a8660f4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239181"
---
# <a name="edi-transaction-set-message-structural-element"></a>EDI 事务集消息结构化元素
事务集（在 X12 编码中）或消息（在 EDIFACT 编码中）包含构成消息数据的段。 事务集由标头、数据段集合和尾部组成。 事务集中提供了处理事务所需的所有详细信息。  
  
 事务集必须以 ST 事务集标头（在 X12 中）或 UNH 消息标头（在 EDIFACT 中）开始， 且必须以 SE 事务集尾部（在 X12 中）或 UNT 消息尾部（在 EDIFACT 中）结束。 尾部提供包括标头和尾部段在内的数据段的计数。  
  
 事务集可以包含一个或多个循环，这些循环是重复相关段的集合所必需的。