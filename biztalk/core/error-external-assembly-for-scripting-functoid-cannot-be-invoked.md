---
title: 错误-脚本 Functoid 的外部程序集不能调用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.cannotInvokeExternalAssembly
ms.assetid: 30d97b05-2cbf-44a5-b219-3a5ae17fc597
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dcf4b387dd33900130e8aa5adff29b8de8d79ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348338"
---
# <a name="error---external-assembly-for-scripting-functoid-cannot-be-invoked"></a>不能调用错误-脚本 Functoid 的外部程序集
**错误代码**  
  
 btm1067  
  
 **说明**  
  
 与相关相关联的外部程序集方法**脚本**functoid 不能调用。 尽管不需要编译映射，测试映射操作需要此类外部程序集位于全局程序集缓存 (GAC)。 正常、 运行时操作还要求外部程序集必须位于 GAC 中。  
  
 **用户执行任何操作**  
  
 确保引用相关的外部程序集**脚本**functoid 位于 gac。