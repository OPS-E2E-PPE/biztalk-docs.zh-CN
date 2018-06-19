---
title: 错误-需要迁移映射 |Microsoft 文档
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
ms.openlocfilehash: 9f49ef4aae0db47216f6117f1053185df6fae0a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240549"
---
# <a name="error---map-needs-to-be-migrated"></a>错误-需要迁移映射
**错误代码**  
  
 btm1064  
  
 **说明**  
  
 由于映射是使用以前版本的 BizTalk 映射器创建的，因此无法编译。 在编译这些映射之前，必须先将它们迁移到此版本的 BizTalk 映射器。  
  
 **用户执行任何操作**  
  
 通过将映射的文件扩展名从“xml”更改为“btm”，并将其添加到相关的 Microsoft BizTalk Server 项目中，可将映射迁移到当前版本的 BizTalk 映射器。 使用**添加现有项**上可用的命令**文件**菜单和快捷菜单上的 BizTalk 项目在解决方案资源管理器，然后打开该映射，通过在解决方案资源管理器中双击它。 由于已学至此主题，想必已执行了前两个步骤。 此时只需在当前版本的 BizTalk 映射器中打开该映射，就可以自动迁移映射。