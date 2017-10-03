---
title: "管理 BizTalk Server 中的 BAM 门户 |Microsoft 文档"
Description: "安装和配置 BizTalk Server 中的 BAM 门户概述"
ms.custom: 
ms.date: 08/15/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a08aa85-3a45-4a8c-bdb5-5615ca097ce1
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7908c9c7ce8e4b731e0b88569e3dc3fb228a1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-the-bam-portal"></a>管理 BAM 门户

## <a name="set-up-bam-portal"></a>设置 BAM 门户
管理员可以通过运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装过程来设置 BAM 门户。 使用 BizTalk Server 配置工具可以指定是否启用 BAM，还可以指定 Web Services 帐户、可查看门户的 Windows 组以及门户的宿主网站。 如果设置 BAM 门户后有必要更新 BAM 门户配置，可以使用配置工具更新配置设置，例如，Portal Users 组、应用程序池帐户和管理 Web Services 用户。  
  
 有关安装 BAM 门户的详细信息，请参阅[安装和配置多个计算机环境中的 BAM](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)。  
  
 有关配置 BAM 门户的详细信息，请参阅[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。
  
 BAM 门户有许多可自定义的设置，这些设置可通过修改 webconfig.xml 文件来访问。 这些设置控制 BAM 门户的性能和操作。 本部分中的剩余内容介绍如何自定义 BAM 门户配置。  
  
## <a name="next-steps"></a>后续步骤 
  
-   [自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)  
  
-   [如何在 NLB 群集上配置到工作 BAM 门户](../core/how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster.md)  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)