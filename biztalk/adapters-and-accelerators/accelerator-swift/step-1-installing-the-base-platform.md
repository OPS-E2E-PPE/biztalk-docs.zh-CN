---
title: 第 1 步：安装基础平台 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- platforms
- installing, base platform
- base platform
ms.assetid: 27da386f-90c7-414f-a4e3-e909f0c18371
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd3f901e31f0def313f3f8cf5cb3a9b8ea0dd16c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529967"
---
# <a name="step-1-installing-the-base-platform"></a>第 1 步：安装基础平台
基础平台，用于安装 Microsoft[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]和[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]使用默认安装选项的每个服务器上的 Service Pack 2。 请遵循以下建议：  
  
## <a name="pre-installation"></a>预安装  
  
- 在软件安装过程中禁用所有防病毒软件。 某些防病毒软件程序可能会阻止所需的软件组件正确安装。  
  
- 请确保输入适当的授权信息 （最大已购买每个服务器的连接数）。 系统性能可能受到可用连接数。  
  
- 请确保已安装 BizTalk Server 安装所需的所有软件必备项。 有关详细信息，请参阅 BizTalk Server 安装说明[ http://go.microsoft.com/fwlink/?LinkId=81041 ](http://go.microsoft.com/fwlink/?LinkId=81041)。 [BizTalk 2013 R2 accelerator for SWIFT 安装指南](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1)。  
  
- 在脱机环境中测试所有关键更新，然后再在生产服务器上安装它们。  
  
- 请确保安装所有适用的修补程序作为你的部署的一部分安装的所有产品。 有关详细信息，请参阅以下源：  
  
  - Microsoft BizTalk Server 联机帮助  
  
  - 在 BizTalk Server 安装说明[ http://go.microsoft.com/fwlink/?LinkId=81041 ](http://go.microsoft.com/fwlink/?LinkId=81041)。  
  
  - Microsoft[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]网站，网址[ http://go.microsoft.com/fwlink/?linkid=48685 ](http://go.microsoft.com/fwlink/?linkid=48685)。  
  
  - Microsoft 下载网站，网址[ http://go.microsoft.com/fwlink/?linkid=48686 ](http://go.microsoft.com/fwlink/?linkid=48686)。  
  
  - [!INCLUDE[btsWinUpdate](../../includes/btswinupdate-md.md)] 网站，网址[ http://go.microsoft.com/fwlink/?linkid=48687 ](http://go.microsoft.com/fwlink/?linkid=48687)。  
  
- 若要避免病毒攻击，从 CD 安装平台和每个服务器断开与 Internet 的连接电缆拔出和禁用任何网络适配器。  
  
- 空白分区使用格式[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]NTFS 文件系统。  
  
## <a name="active-directory"></a>Active Directory  
  
-   创建名为域用户**管理员**并将其添加到本地**管理员**组在部署中每台计算机上。 在安装时，登录到部署服务器使用此域帐户。  
  
-   没有配置任何网络适配器或在此时加入任何域。 本指南介绍如何配置这些设置更高版本时开始部署过程。  
  
## <a name="internal-web-servers-mrsr-site"></a>内部 Web 服务器 （MRSR 站点）  
  
-   请确保仅在 MRSR 站点服务器上安装 Internet 信息服务 (IIS)。  
  
-   请确保 Internet 信息服务 (IIS) 未安装 Internet Security and Acceleration (ISA) 服务器上。  
  
-   请确保仅在 MRSR 站点服务器上安装了消息队列 (MSMQ) 服务。 如果 BizTalk 消息传送服务器也将用作 MRSR 站点服务器，并在这些服务器上安装 MSMQ。