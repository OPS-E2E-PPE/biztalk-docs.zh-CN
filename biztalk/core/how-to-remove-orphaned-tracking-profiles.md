---
title: 如何删除孤立的跟踪配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, orphans
- tracking profiles, activities
- tracking profiles, deleting
- activities, tracking profiles
ms.assetid: e8923dab-5d02-41a3-840b-104b20624e6c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e61365e5677b81fd48a655ba553cd44108d5a0fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384310"
---
# <a name="how-to-remove-orphaned-tracking-profiles"></a>如何删除孤立的跟踪配置文件
跟踪配置文件是与活动关联。 如果某个活动是取消部署，关联的跟踪配置文件可能会变得孤立用户，这意味着它们不再与活动关联。 可以使用以下过程删除跟踪配置文件。  
  
### <a name="to-remove-an-orphaned-tracking-profile"></a>若要删除孤立的跟踪配置文件  
  
1.  重新部署 BAM 定义。 有关部署 BAM 定义的信息，请参阅[如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。  
  
2.  使用跟踪配置文件编辑器 (TPE) 来删除跟踪配置文件。 有关删除跟踪配置文件的信息，请参阅[如何应用和删除跟踪配置文件](../core/how-to-apply-and-remove-a-tracking-profile.md)。  
  
3.  取消部署 BAM 定义。 有关删除 BAM 定义的信息，请参阅[如何删除 BAM 定义](../core/how-to-remove-bam-definitions.md)。  
  
## <a name="see-also"></a>请参阅  
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)