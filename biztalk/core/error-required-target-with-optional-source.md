---
title: 错误-必需的目标节点具有可选源 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.reqdTargetWithOptionalSource
ms.assetid: 3f342011-4577-4682-8324-8296615d5194
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76dd96f61766a475db6385e306bc64bc36db4fcf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---required-target-with-optional-source"></a>错误-需要目标节点具有可选的源
**错误代码**  
  
 btm1001  
  
 **说明**  
  
 目标架构中所指示的必需节点的数据来自源架构中的可选节点。 因此，某些有效实例消息的映射将会失败。  
  
 **用户执行任何操作**  
  
 分别确认所指定的源节点和目标节点的可选和必需设置，并考虑使这些设置匹配。