---
title: 如果未移动 MessageBox 数据库移动跟踪数据库时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee4066cb-da5b-4d04-a3b8-23fbf2d0c92a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7ff06df85f70168f3811910c0fab94c8bd772c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401288"
---
# <a name="considerations-when-moving-the-tracking-database-if-the-messagebox-database-is-not-being-moved"></a>如果未移动 MessageBox 数据库移动跟踪数据库时的注意事项
如果要移动跟踪数据库而不是 MessageBox 数据库，当您编辑的 SampleUpdateInfo.xml 文件，请确保您包括 MessageBox 数据库，即使在未移动 MessageBox 数据库。 此操作必须执行，确保[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业 TrackedMessages_Copy_BizTalkMsgBoxDb 更新与新的跟踪数据库的位置。  
  
 例如，在以下的 SampleUpdateInfo.xml 文件中，仅对跟踪数据库是从移 OldServer 至 NewServer。 MessageBox 数据库停留在 OldServer 上：  
  
```  
<UpdateConfiguration>  
     <MessageBoxDB oldDBName="BizTalkMgmtDb" oldDBServer="OldServer" newDBName="BizTalkMgmtDb" newDBServer="OldServer" IsMaster="1"/>  
     <TrackingDB oldDBName="BizTalkDTADB" oldDBServer="OldServer" newDBName="BizTalkDTADB" newDBServer="NewServer"/>  
     <OtherDatabases>  
     </OtherDatabases>  
</UpdateConfiguration>  
```  
  
## <a name="see-also"></a>请参阅  
 [移动数据库](../technical-guides/moving-databases.md)