---
title: 错误-映射需要迁移 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.mapNeedsMigrating
ms.assetid: f10af4a4-6e40-4eec-a2fd-e526821aebe6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b1b1bee4bcdedecb31dc4b648b505d8ae53b4eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389028"
---
# <a name="error---map-needs-to-be-migrated"></a>错误-需要迁移映射
**错误代码**  
  
 btm1064  
  
 **说明**  
  
 无法编译该映射，因为它创建使用以前版本的 BizTalk 映射器。 它们可以编译之前，必须将此类映射迁移到此版本的 BizTalk 映射器。  
  
 **用户执行任何操作**  
  
 通过更改文件扩展名从"xml"为"btm"，并将其添加到相关的 Microsoft BizTalk Server 项目，将映射迁移到当前版本的 BizTalk 映射器。 使用**添加现有项**上可用的命令**文件**菜单和快捷菜单上的 BizTalk 项目在解决方案资源管理器，然后通过双击解决方案资源管理器中打开该映射。 因为你已达到本主题，你可能已经执行的前两个步骤。 只需在当前版本的 BizTalk 映射器中打开该映射将执行在实时迁移映射。