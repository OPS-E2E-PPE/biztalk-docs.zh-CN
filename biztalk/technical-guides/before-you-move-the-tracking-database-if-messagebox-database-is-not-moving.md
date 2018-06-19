---
title: 如果不移动 MessageBox 数据库移动跟踪数据库时的注意事项 |Microsoft 文档
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
ms.openlocfilehash: ecb2fcb6ad9ead42bd3e09c84a8895758d82293f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299917"
---
# <a name="considerations-when-moving-the-tracking-database-if-the-messagebox-database-is-not-being-moved"></a><span data-ttu-id="6603b-102">如果不移动 MessageBox 数据库移动跟踪数据库时的注意事项</span><span class="sxs-lookup"><span data-stu-id="6603b-102">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>
<span data-ttu-id="6603b-103">如果要移动跟踪数据库而不是 MessageBox 数据库，当你编辑 SampleUpdateInfo.xml 文件中，请确保你包括 MessageBox 数据库以及的项，即使未移动 MessageBox 数据库也是如此。</span><span class="sxs-lookup"><span data-stu-id="6603b-103">If you are moving the Tracking database but not the MessageBox database, when you edit the SampleUpdateInfo.xml file, make sure that you include an entry for the MessageBox database as well, even though the MessageBox database is not being moved.</span></span> <span data-ttu-id="6603b-104">此操作必须执行以确保[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]使用新的跟踪数据库的位置更新 TrackedMessages_Copy_BizTalkMsgBoxDb 代理作业。</span><span class="sxs-lookup"><span data-stu-id="6603b-104">This must be done to ensure that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent job TrackedMessages_Copy_BizTalkMsgBoxDb is updated with the location of the new Tracking database.</span></span>  
  
 <span data-ttu-id="6603b-105">例如，在以下 SampleUpdateInfo.xml 文件中，仅跟踪数据库正在移动 OldServer 到 NewServer。</span><span class="sxs-lookup"><span data-stu-id="6603b-105">For example, in the following SampleUpdateInfo.xml file, only the Tracking database is being moved from OldServer to NewServer.</span></span> <span data-ttu-id="6603b-106">MessageBox 数据库保持在 OldServer 上使用：</span><span class="sxs-lookup"><span data-stu-id="6603b-106">The MessageBox database is staying on OldServer:</span></span>  
  
```  
<UpdateConfiguration>  
     <MessageBoxDB oldDBName="BizTalkMgmtDb" oldDBServer="OldServer" newDBName="BizTalkMgmtDb" newDBServer="OldServer" IsMaster="1"/>  
     <TrackingDB oldDBName="BizTalkDTADB" oldDBServer="OldServer" newDBName="BizTalkDTADB" newDBServer="NewServer"/>  
     <OtherDatabases>  
     </OtherDatabases>  
</UpdateConfiguration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6603b-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6603b-107">See Also</span></span>  
 [<span data-ttu-id="6603b-108">移动数据库</span><span class="sxs-lookup"><span data-stu-id="6603b-108">Moving Databases</span></span>](../technical-guides/moving-databases.md)