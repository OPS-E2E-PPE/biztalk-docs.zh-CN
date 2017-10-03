---
title: "错误-不在生成的架构文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.schemaFileNotInBuild
ms.assetid: 9190868d-a1ae-48bf-ac85-510086805887
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3b5d6d11bec6b9f263e2f204f004a9a162de471
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---schema-file-not-in-build"></a>错误-不在生成的架构文件
**说明**  
  
 该命令 (**验证实例**，**生成实例**，或**验证架构**) 无法执行，因为**生成操作**架构文件的属性设置为**无**，阻止此架构参与这些命令。  
  
 **用户执行任何操作**  
  
 在 Microsoft 中选择相关的架构文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，然后在属性窗口中，更改**生成操作**属性**编译**。 然后尝试**验证实例**，**生成实例**，或**验证架构**试命令。