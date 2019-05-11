---
title: 跟踪配置文件部署实用程序 |Microsoft Docs
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
ms.openlocfilehash: cf72709c0527b9bc39b238be6d2ca98b698530fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313801"
---
# <a name="tracking-profile-deployment-utility"></a>跟踪配置文件部署实用程序
开发人员使用 bttdeploy 实用程序应用到的跟踪配置文件，并从 BAM 基础结构中删除它们。 使用 bttdeploy 实用程序在功能上等效于单击应用跟踪配置文件菜单选项在跟踪配置文件编辑器 (TPE)。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
 **Usage**  
  
 **bttdeploy.exe [options] file name**  
  
|Option|Description|  
|------------|-----------------|  
|/h 或 /？|可选：显示摘要 bttdeploy 的语法。|  
|/mgdb \<server name[,port]\>\\<database name\>|可选：指定管理服务器、 端口和要对其应用该配置文件的数据库名称。 **注意：** 使用此参数时，该端口是可选的。|  
|/remove|可选：指定跟踪配置文件将从 BAM 数据库中删除。|  
|filename|跟踪的名称配置可应用或删除的文件。|  
  
## <a name="see-also"></a>请参阅  
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)   
 [如何删除孤立的跟踪配置文件](../core/how-to-remove-orphaned-tracking-profiles.md)