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
# <a name="considerations-when-moving-the-tracking-database-if-the-messagebox-database-is-not-being-moved"></a><span data-ttu-id="490f3-102">如果未移动 MessageBox 数据库移动跟踪数据库时的注意事项</span><span class="sxs-lookup"><span data-stu-id="490f3-102">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>
<span data-ttu-id="490f3-103">如果要移动跟踪数据库而不是 MessageBox 数据库，当您编辑的 SampleUpdateInfo.xml 文件，请确保您包括 MessageBox 数据库，即使在未移动 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="490f3-103">If you are moving the Tracking database but not the MessageBox database, when you edit the SampleUpdateInfo.xml file, make sure that you include an entry for the MessageBox database as well, even though the MessageBox database is not being moved.</span></span> <span data-ttu-id="490f3-104">此操作必须执行，确保[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业 TrackedMessages_Copy_BizTalkMsgBoxDb 更新与新的跟踪数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="490f3-104">This must be done to ensure that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent job TrackedMessages_Copy_BizTalkMsgBoxDb is updated with the location of the new Tracking database.</span></span>  
  
 <span data-ttu-id="490f3-105">例如，在以下的 SampleUpdateInfo.xml 文件中，仅对跟踪数据库是从移 OldServer 至 NewServer。</span><span class="sxs-lookup"><span data-stu-id="490f3-105">For example, in the following SampleUpdateInfo.xml file, only the Tracking database is being moved from OldServer to NewServer.</span></span> <span data-ttu-id="490f3-106">MessageBox 数据库停留在 OldServer 上：</span><span class="sxs-lookup"><span data-stu-id="490f3-106">The MessageBox database is staying on OldServer:</span></span>  
  
```  
<UpdateConfiguration>  
     <MessageBoxDB oldDBName="BizTalkMgmtDb" oldDBServer="OldServer" newDBName="BizTalkMgmtDb" newDBServer="OldServer" IsMaster="1"/>  
     <TrackingDB oldDBName="BizTalkDTADB" oldDBServer="OldServer" newDBName="BizTalkDTADB" newDBServer="NewServer"/>  
     <OtherDatabases>  
     </OtherDatabases>  
</UpdateConfiguration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="490f3-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="490f3-107">See Also</span></span>  
 [<span data-ttu-id="490f3-108">移动数据库</span><span class="sxs-lookup"><span data-stu-id="490f3-108">Moving Databases</span></span>](../technical-guides/moving-databases.md)