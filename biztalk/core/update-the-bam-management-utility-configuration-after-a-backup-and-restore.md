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
ms.openlocfilehash: fa7d8e91ab82cc74f2af2ca0c12f79cdb0a8fcbe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970078"
---
# <a name="how-to-update-the-bam-management-utility-configuration-after-a-backup-and-restore"></a>如何在备份和还原后更新 BAM 管理实用程序配置
在“服务器\数据库”名称组合由于 BizTalk Server 环境中的变化（例如备份和还原序列）而发生更改时，您必须更新 BAM 管理实用程序配置文件 (bm.exe.config) 以反映这些名称更改。  
  
### <a name="to-update-the-bam-management-configuration-file-a-after-backup-and-restore"></a>在备份和还原后更新 BAM 管理实用程序配置文件  
  
1. 打开 bm.exe.config 文件使用记事本**启动**，再单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config，，然后单击**确定**。  
  
2. 找到该文件中的 appSettings 部分，然后将以下值：  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="oldServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
3. 实例部署到 Windows Azure 虚拟机 (VM) 中的  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="newServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
4. 保存该文件。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 数据库](../core/managing-bam-databases.md)