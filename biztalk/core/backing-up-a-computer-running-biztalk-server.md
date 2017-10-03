---
title: "备份运行 BizTalk Server 的计算机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70f53b41-8083-4b56-8698-e75a13b21a69
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 537ea40b39ecd35127b62f8d96f0175e98a1f3b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-a-computer-running-biztalk-server"></a>对运行 BizTalk Server 的计算机进行备份
如果运行 BizTalk Server 的计算机出现了不可恢复的硬件故障，则必须用相同的计算机来替代它。 您应该在替代计算机上安装基本平台软件、必备软件和 BizTalk Server 组件，并设置相同的配置。 这些配置设置包括相应的注册表项、文件、文件夹以及正确操作 BizTalk 应用程序所需的相关 Windows 服务。  
  
 为了确保在发生硬件故障后能够恢复 BizTalk Server，除了备份 BizTalk Server 数据库外，还应备份以下 BizTalk Server 组件：  
  
-   BizTalk Server 配置  
  
-   企业单一登录 (SSO) 主密钥  
  
-   业务活动监视 (BAM) 门户（不使用 BAM 时不需要）  
  
-   BizTalk 应用程序  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何备份的 BizTalk Server 配置](../core/how-to-back-up-the-biztalk-server-configuration.md)  
  
-   [如何备份主密钥](../core/how-to-back-up-the-master-secret.md)  
  
-   [如何备份 BAM 门户](../core/how-to-back-up-the-bam-portal.md)  
  
-   [备份 BizTalk 服务器应用程序](../core/backing-up-biztalk-server-applications.md)