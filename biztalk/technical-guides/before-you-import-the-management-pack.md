---
title: 在导入管理包之前 |Microsoft 文档
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
ms.openlocfilehash: 1c11849c379a4654bed78a8e86ba263e6da428c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299445"
---
# <a name="before-you-import-the-management-pack"></a>导入管理包之前
作为最佳做法，应将用于正在使用的操作系统的 Windows Server 管理包导入。 在导入之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包中，执行以下操作：  
  
-   确保安装了 Operations Manager 2007 R2/2012年。  
  
-   你必须是 SCOM 管理员组或 SCOM 作者组的成员。 SCOM 管理服务器上的本地管理员具有所有权限和授予的 SCOM 管理员组的权限。  
  
-   通过将设置你的 BizTalk 服务器为 Operations Manager 中被管理的计算机部署上每个你想要管理的 BizTalk Server 的 SCOM 代理。 SCOM 代理部署涉及以下任务：  
  
    -   安装 SCOM 代理。  
  
    -   创建 BizTalk SCOM 代理帐户。  
  
    -   配置**运行方式**帐户。 将运行方式帐户添加到以下组：  
  
        -   BizTalk 组。  
  
        -   BizTalk 管理员。  
  
        -   SSO 管理员。  
  
        -   SSO Affiliate 管理员。  
  
    -   秨 ﹍ 菏跌。  
  
-   在 Operation Manager 控制台中，被管理的计算机处于正常状态。  
  
-   配置需要设置，如任何所需的运行方式帐户或配置文件的任何用户帐户。 此管理包包括运行方式配置文件命名为"BizTalk Server 监视帐户"和"BizTalk Server 发现帐户"上的每个代理基础定义具体的凭据。 你可能需要在导入管理包之后，为一些代理使用此运行方式配置文件。  
  
## <a name="in-this-section"></a>在本节中  
  
-   [此管理包中的文件](../technical-guides/files-in-this-management-pack.md)  
  
-   [推荐的其他管理包](../technical-guides/recommended-additional-management-packs.md)