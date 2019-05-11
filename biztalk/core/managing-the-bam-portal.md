---
title: 管理 BizTalk Server 中的 BAM 门户 |Microsoft Docs
Description: 安装和配置 BizTalk Server 中的 BAM 门户概述
ms.custom: ''
ms.date: 08/15/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a08aa85-3a45-4a8c-bdb5-5615ca097ce1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0448e435e7adcc84d30f31ded54534c248e8e69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380158"
---
# <a name="manage-the-bam-portal"></a>管理 BAM 门户

## <a name="set-up-bam-portal"></a>设置 BAM 门户
管理员通过运行设置 BAM 门户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。 若要指定是否启用了 BAM，并指定 Web 服务帐户，可以查看门户中，Windows 组和将承载在门户的网站，请使用 BizTalk Server 配置工具。 如果有必要更新 BAM 门户配置设置 BAM 门户后，，使用配置工具来更新配置设置，例如，portal users 组、 应用程序池帐户和管理 Web services 用户。  
  
 有关安装 BAM 门户的详细信息，请参阅[安装并在多计算机环境中配置 BAM](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)。  
  
 有关配置 BAM 门户的详细信息，请参阅[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。
  
 BAM 门户提供了通过修改 webconfig.xml 文件访问的许多可自定义设置。 这些设置控制的性能和 BAM 门户的操作。 本部分的余下部分介绍如何自定义 BAM 门户配置。  
  
## <a name="next-steps"></a>后续步骤 
  
-   [自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)  
  
-   [如何在 NLB 群集上配置 BAM 门户，转到工作](../core/how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster.md)  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)