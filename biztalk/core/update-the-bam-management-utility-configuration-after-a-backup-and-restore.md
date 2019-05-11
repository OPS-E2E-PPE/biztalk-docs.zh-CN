---
title: 如何更新 BAM 管理实用程序配置后的备份和还原 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b27062b-546f-4030-983b-15d793912690
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b33d86a80f87991bf0d22f0daac3c15ccc83f841
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398650"
---
# <a name="how-to-update-the-bam-management-utility-configuration-after-a-backup-and-restore"></a><span data-ttu-id="310bf-102">如何更新后的备份和还原的 BAM 管理实用程序配置</span><span class="sxs-lookup"><span data-stu-id="310bf-102">How to Update the BAM Management Utility Configuration After a Backup and Restore</span></span>
<span data-ttu-id="310bf-103">当 server\database 名称组合作为你的 BizTalk Server 环境，如备份和还原序列中的更改的结果更改时，必须更新 BAM 管理实用程序配置文件 (bm.exe.config) 以反映这些名称更改。</span><span class="sxs-lookup"><span data-stu-id="310bf-103">When the server\database name combination changes as the result of a change in your BizTalk Server environment such as a backup and restore sequence, you must update the BAM management utility configuration file (bm.exe.config) to reflect these name changes.</span></span>  
  
### <a name="to-update-the-bam-management-configuration-file-a-after-backup-and-restore"></a><span data-ttu-id="310bf-104">若要更新 BAM 管理配置文件后的备份和还原</span><span class="sxs-lookup"><span data-stu-id="310bf-104">To update the BAM management configuration file a after backup and restore</span></span>  
  
1. <span data-ttu-id="310bf-105">打开 bm.exe.config 文件使用记事本**启动**，再单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="310bf-105">Open the bm.exe.config file using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="310bf-106">在文件中找到 appSettings 部分并更改以下值：</span><span class="sxs-lookup"><span data-stu-id="310bf-106">Locate the appSettings section in the file and change the following values:</span></span>  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="oldServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
3. <span data-ttu-id="310bf-107">实例部署到 Windows Azure 虚拟机 (VM) 中的</span><span class="sxs-lookup"><span data-stu-id="310bf-107">to</span></span>  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="newServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
4. <span data-ttu-id="310bf-108">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="310bf-108">Save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="310bf-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="310bf-109">See Also</span></span>  
 [<span data-ttu-id="310bf-110">管理 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="310bf-110">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)