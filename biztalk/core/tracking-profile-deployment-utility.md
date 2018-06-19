---
title: 跟踪配置文件部署实用工具 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d631b7c-a40f-4cee-88a4-3d932ab7fde0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 672879df2c1c5217d8a9710dad000609dd95d0c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974107"
---
# <a name="tracking-profile-deployment-utility"></a>跟踪配置文件部署实用工具
开发人员使用 bttdeploy 实用程序可以将跟踪配置文件应用于 BAM 基础结构，也可以用它从 BAM 基础结构中删除跟踪配置文件。 使用 bttdeploy 实用程序在功能上与单击跟踪配置文件编辑器 (TPE) 中的“应用跟踪配置文件”菜单选项一样。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
 **用法**  
  
 **bttdeploy.exe [选项] 文件名称**  
  
|选项|Description|  
|------------|-----------------|  
|/h 或 /?|可选：显示 bttdeploy 的语法摘要。|  
|/mgdb\<服务器名称 [，端口]\>\\< 数据库名称\>|可选：指定要将配置文件应用到的管理服务器、端口和数据库名称。 **注意：** 端口使用此参数时，是可选的。|  
|/remove|可选：指定将从 BAM 数据库中删除跟踪配置文件。|  
|filename|要应用或删除的跟踪配置文件的名称。|  
  
## <a name="see-also"></a>另请参阅  
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)   
 [如何删除孤立的跟踪配置文件](../core/how-to-remove-orphaned-tracking-profiles.md)