---
title: 错误-输出验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.outputValidation
ms.assetid: 18a251a9-6bd4-4fd1-a774-2ea1b7870891
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 392ec887e3352940257f268e589280eb361c0d68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347118"
---
# <a name="error---output-validation"></a>错误-输出验证
**错误代码**  
  
 btm1046  
  
 **说明**  
  
 测试映射操作创建输出实例消息文件不是根据目标架构验证所指示的原因。  
  
 **用户执行任何操作**  
  
 在映射中指定的转换或目标架构中，或者对二者同时，根据所指示的原因，进行合适的更正。 可能会有帮助，BizTalk 编辑器中打开目标架构，并使用**验证架构**，**验证实例**，并**生成实例**命令可用右键单击解决方案资源管理器中的架构。