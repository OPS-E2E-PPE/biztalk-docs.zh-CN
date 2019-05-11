---
title: 在导入管理包之前 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e3c13dd-613a-4885-a5d2-ad3ee492ff25
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28bd8cdbb520c5f2ee7f22cb0e2b035b32c44aa8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401299"
---
# <a name="before-you-import-the-management-pack"></a>导入管理包之前
作为最佳做法，应导入 Windows Server 管理包使用的操作系统。 在导入之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包中，执行以下操作：  
  
-   请确保已安装 Operations Manager 2007 R2/2012年。  
  
-   必须是 SCOM Administrators 组或 SCOM 作者组的成员。 SCOM 管理服务器上的本地管理员具有所有权限和到 SCOM Administrators 组授予的权限。  
  
-   部署上你想要管理每个 BizTalk Server 的 SCOM 代理到的 BizTalk 服务器设置为在 Operations Manager 中的托管计算机。 SCOM 代理部署过程包括以下任务：  
  
    -   安装 SCOM 代理。  
  
    -   创建 BizTalk SCOM 代理帐户。  
  
    -   配置**运行方式**帐户。 将运行方式帐户添加到以下组：  
  
        -   BizTalk 组。  
  
        -   BizTalk 管理员。  
  
        -   SSO 管理员。  
  
        -   SSO 关联管理员。  
  
    -   秨 ﹍ 菏跌。  
  
-   在 Operation Manager 控制台中，被管理的计算机处于正常状态。  
  
-   配置任何必须进行设置，例如任何所需的运行方式帐户或配置文件的用户帐户。 此管理包包括运行方式配置文件命名为"BizTalk Server 监视帐户"和"BizTalk Server 发现帐户"以在每个代理的基础上定义具体的凭据。 您可能需要为一些代理使用此运行方式配置文件导入管理包后。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [此管理包中的文件](../technical-guides/files-in-this-management-pack.md)  
  
-   [推荐的其他管理包](../technical-guides/recommended-additional-management-packs.md)