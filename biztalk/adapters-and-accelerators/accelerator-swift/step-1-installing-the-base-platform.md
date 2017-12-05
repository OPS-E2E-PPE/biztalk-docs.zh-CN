---
title: "步骤 1： 安装基础平台 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- platforms
- installing, base platform
- base platform
ms.assetid: 27da386f-90c7-414f-a4e3-e909f0c18371
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e0884ff97e9981129f63c9bc425e86dfeaafc9a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="step-1-installing-the-base-platform"></a>步骤 1： 安装基础平台
对于基础平台，安装[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]和[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]使用默认安装选项的每个服务器上的 Service Pack 2。 请遵循这些建议：  
  
## <a name="pre-installation"></a>预安装  
  
-   在软件安装过程中禁用所有防病毒软件。 某些防病毒软件程序可能会阻止所需的软件组件正确安装。  
  
-   请确保你输入合适的许可信息 （最大你购买的每个服务器的连接数）。 可以通过的可用连接数影响系统性能。  
  
-   请确保你已安装 BizTalk Server 安装所需的所有软件必备项。 有关详细信息，请参阅在 BizTalk Server 安装说明[http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)。 [安装指南 》 BizTalk 2013 R2 Accelerator for SWIFT](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1)。  
  
-   在生产服务器上安装它们之前，请在脱机环境中测试所有重要更新。  
  
-   请确保你安装适用的作为你部署的一部分安装的所有产品的所有修补程序。 有关详细信息，请参阅以下源：  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server 联机帮助  
  
    -   在 BizTalk Server 安装说明[http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)。  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]网站，网址[http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685)。  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]下载中心网站，网址[http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686)。  
  
    -   [!INCLUDE[btsWinUpdate](../../includes/btswinupdate-md.md)]网站，网址[http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687)。  
  
-   若要避免病毒攻击，从 CD 安装平台，并通过一个电缆拔出并禁用任何网络适配器将每个服务器断开 Internet。  
  
-   干净分区使用格式的[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]NTFS 文件系统。  
  
## <a name="active-directory"></a>Active Directory  
  
-   创建一个名为的域用户**管理员**并将其添加到本地**管理员**组部署中的每台计算机上。 在安装时，登录到使用此域帐户的部署服务器。  
  
-   请不要配置任何网络适配器，或者在此时加入任何域。 本指南介绍如何更高版本配置这些设置，当你开始部署过程。  
  
## <a name="internal-web-servers-mrsr-site"></a>内部 Web 服务器 （MRSR 站点）  
  
-   请确保仅在 MRSR 站点服务器上安装 Internet 信息服务 (IIS)。  
  
-   请确保 Internet 信息服务 (IIS) 未安装在 Internet Security and Acceleration (ISA) Server。  
  
-   请确保仅在 MRSR 站点服务器上安装了消息队列 (MSMQ) 服务。 如果 BizTalk 消息传送服务器也将用作 MRSR 站点服务器，并在这些服务器上安装 MSMQ。