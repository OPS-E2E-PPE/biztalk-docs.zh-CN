---
title: 错误-架构文件不在生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.schemaFileNotInBuild
ms.assetid: 9190868d-a1ae-48bf-ac85-510086805887
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48edbf86714ec100ba69833a57786205139247f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388425"
---
# <a name="error---schema-file-not-in-build"></a>错误-架构文件不在生成
**说明**  
  
 该命令 (**验证实例**，**生成实例**，或**验证架构**) 无法执行，因为**生成操作**架构文件的属性设置为**None**，防止此架构在这些命令。  
  
 **用户执行任何操作**  
  
 在 Microsoft 中选择相关的架构文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，然后在属性窗口中更改**生成操作**属性设置为**编译**。 然后尝试**验证实例**，**生成实例**，或**验证架构**试命令。