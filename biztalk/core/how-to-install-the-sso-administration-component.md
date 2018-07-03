---
title: 安装 SSO 管理组件 |Microsoft Docs
description: 若要获取 SSO 管理自定义安装和使用 ssomanage 或 SSO 管理 BizTalk Server 中输入服务器名称
ms.custom: ''
ms.date: 09/27/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 096839e2-7129-498d-92ee-5afeea8dbe0d
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f510a876102ec867e2f2f16676cef63cedfaa92
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981326"
---
# <a name="how-to-install-the-sso-administration-component"></a>如何安装 SSO 管理组件

## <a name="overview"></a>概述
可以作为独立的功能来安装企业单一登录管理组件。 在需要远程管理 SSO 系统时这将非常有用。 其硬件和软件要求与典型的企业 SSO 运行时服务安装的硬件和软件要求相同。  
  
 在安装后管理组件，您输入要用于进行管理的 SSO 服务器。 可以使用命令行工具 (ssomanage.exe) 或 SSO 管理 Mmc 管理单元来执行此操作。 本主题列出了这两个过程。  
  
 安装 SSO 管理实用工具 (ssomanage.exe) 时，不会在“开始”菜单上创建用于访问该命令行实用工具的快捷方式。 若要在安装后运行 SSO 管理实用工具，必须打开命令提示符，并导航到的 SSO 目录`Program Files\Common Files\Enterprise Single Sign-On`。  
  
 企业 SSO 管理功能还包括一个 MMC 管理单元。 对于中的管理单元函数必须在计算机上安装 MMC 3.0。  
  
 若要打开企业 SSO MMC 管理单元中的**启动**菜单中，选择**所有程序**，选择**Microsoft 企业单一登录**，然后**SSO管理**。  
  
## <a name="install-the-enterprise-single-sign-on-administrative-component"></a>安装企业单一登录管理组件  
  
- 执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并选择仅企业单一登录管理功能。 有关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，这列入**其他软件**。  
  
## <a name="enter-the-server-using-the-mmc-snap-in"></a>输入使用 MMC 管理单元中的服务器  
  
1.  当在未安装管理组件的计算机上安装管理组件后，请打开 SSO 管理单元。  
  
     在中**启动**菜单中，选择**所有程序**，选择**Microsoft 企业单一登录**，然后选择**SSO 管理**。  
  
2.  在 Mmc 管理单元下**控制台根节点**，右键单击**企业单一登录**，然后单击**选择**。  
  
     **选择 SSO Server**对话框将出现。  
  
3.  输入或浏览到要指定的 SSO 服务器名。 若要指定 SSO 服务器的所有用户的计算机上，选择**为所有用户设置 SSO 服务器**。  
  
4.  单击“确定” 。  
  
## <a name="enter-the-server-using-the-command-line-tool"></a>输入使用命令行工具的服务器  
  
1.  依次单击 **“开始”** 和 **“运行”**，然后键入 **cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录是`\Program Files\Common Files\Enterprise Single Sign-On`。  
  
3.  通过选择下列选项之一来输入 SSO 服务器：  
  
    1.  类型**ssomanage – server**输入想要执行管理操作时连接到的 SSO 服务器。  
  
         \- 或 -  
  
    2.  类型**ssomanage-serverall，** 输入执行管理操作时，此计算机的所有用户将都连接到 SSO 服务器。  
  
## <a name="see-also"></a>请参阅  
 [如何安装 SSO 客户端实用工具](../core/how-to-install-the-sso-client-utility.md)   
 [配置 SSO](../core/configuring-sso.md)   
 [安装 SSO](../core/installing-sso.md)
