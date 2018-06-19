---
title: 如何更新后的备份和还原的 BAM 管理实用程序配置 |Microsoft 文档
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
ms.openlocfilehash: cf316e7275b3db47b02a7f09ed5d2a66571c4de1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286669"
---
# <a name="how-to-update-the-bam-management-utility-configuration-after-a-backup-and-restore"></a>如何在备份和还原后更新 BAM 管理实用程序配置
在“服务器\数据库”名称组合由于 BizTalk Server 环境中的变化（例如备份和还原序列）而发生更改时，您必须更新 BAM 管理实用程序配置文件 (bm.exe.config) 以反映这些名称更改。  
  
### <a name="to-update-the-bam-management-configuration-file-a-after-backup-and-restore"></a>在备份和还原后更新 BAM 管理实用程序配置文件  
  
1.  Bm.exe.config 使用记事本打开文件通过单击**启动**、 单击**运行**，键入记事本[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config，，然后单击**确定**。  
  
2.  找到该文件中的 appSettings 部分，然后将以下值：  
  
    ```  
    <!-- Default server and database for bm.exe. -->  
    <add key="DefaultServer" value="oldServerName" />  
    <add key="DefaultDatabase" value="BAMPrimaryImport" />  
    ```  
  
3.  实例部署到 Windows Azure 虚拟机 (VM) 中的  
  
    ```  
    <!-- Default server and database for bm.exe. -->  
    <add key="DefaultServer" value="newServerName" />  
    <add key="DefaultDatabase" value="BAMPrimaryImport" />  
    ```  
  
4.  保存该文件。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 数据库](../core/managing-bam-databases.md)