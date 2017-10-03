---
title: "如果不移动 MessageBox 数据库移动跟踪数据库时的注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee4066cb-da5b-4d04-a3b8-23fbf2d0c92a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecb2fcb6ad9ead42bd3e09c84a8895758d82293f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-moving-the-tracking-database-if-the-messagebox-database-is-not-being-moved"></a>如果不移动 MessageBox 数据库移动跟踪数据库时的注意事项
如果要移动跟踪数据库而不是 MessageBox 数据库，当你编辑 SampleUpdateInfo.xml 文件中，请确保你包括 MessageBox 数据库以及的项，即使未移动 MessageBox 数据库也是如此。 此操作必须执行以确保[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]使用新的跟踪数据库的位置更新 TrackedMessages_Copy_BizTalkMsgBoxDb 代理作业。  
  
 例如，在以下 SampleUpdateInfo.xml 文件中，仅跟踪数据库正在移动 OldServer 到 NewServer。 MessageBox 数据库保持在 OldServer 上使用：  
  
```  
<UpdateConfiguration>  
     <MessageBoxDB oldDBName="BizTalkMgmtDb" oldDBServer="OldServer" newDBName="BizTalkMgmtDb" newDBServer="OldServer" IsMaster="1"/>  
     <TrackingDB oldDBName="BizTalkDTADB" oldDBServer="OldServer" newDBName="BizTalkDTADB" newDBServer="NewServer"/>  
     <OtherDatabases>  
     </OtherDatabases>  
</UpdateConfiguration>  
```  
  
## <a name="see-also"></a>另请参阅  
 [移动数据库](../technical-guides/moving-databases.md)