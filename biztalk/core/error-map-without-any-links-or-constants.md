---
title: 错误-不含任何链接或常量的映射 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.mapWithoutAnyLinksOrConstants
ms.assetid: 8d1cdbcd-4bd0-4ddc-9e94-746e82b6ec48
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d697d6d053f2c0a36d0f5cb45002dca28a92f005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240637"
---
# <a name="error---map-without-any-links-or-constants"></a>错误-映射不含任何链接或常量
**错误代码**  
  
 btm1000  
  
 **说明**  
  
 映射不包含架构之间的任何链接或不包含目标架构中的常数值。 因此，此映射无法创建输出。  
  
 **用户执行任何操作**  
  
 在映射网格中添加适当的链接，如果需要，还可添加 functoid，或者在目标架构中添加常数，以指定与源架构一致的实例消息应如何转换为与目标架构一致的实例消息。