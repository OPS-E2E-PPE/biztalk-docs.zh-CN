---
title: 备份运行 BizTalk Server 的计算机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70f53b41-8083-4b56-8698-e75a13b21a69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04f8a0073ffd4117da1d5cf5d92dd969b9a0abfc
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528576"
---
# <a name="backing-up-a-computer-running-biztalk-server"></a>备份运行 BizTalk Server 的计算机
如果运行 BizTalk Server 的计算机出现了不可恢复的硬件故障，必须将该计算机为使用完全相同。 应设置基本平台软件、 必备软件、 BizTalk Server 组件和设置相同的配置在替代计算机。 这些配置设置可能会包含相应的注册表项、 文件、 文件夹和 BizTalk 应用程序正确操作所需的相关的 Windows 服务。  
  
 除了备份 BizTalk Server 数据库，您应备份以下 BizTalk Server 组件，以确保可以在硬件故障后恢复 BizTalk Server:  
  
-   BizTalk Server 配置  
  
-   企业单一登录 (SSO) 主密钥  
  
-   业务活动监视 (BAM) 门户 （除非使用 BAM 时不需要）  
  
-   BizTalk 应用程序  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何备份 BizTalk Server 配置](../core/how-to-back-up-the-biztalk-server-configuration.md)  
  
-   [如何备份主密钥](../core/how-to-back-up-the-master-secret.md)  
  
-   [如何备份 BAM 门户](../core/how-to-back-up-the-bam-portal.md)  
  
-   [备份 BizTalk Server 应用程序](../core/backing-up-biztalk-server-applications.md)