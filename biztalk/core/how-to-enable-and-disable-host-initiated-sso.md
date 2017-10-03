---
title: "如何启用和禁用主机启动的 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host initiated SSO, disabling
- disabling, host initiated SSO
- enabling, host initiated SSO
- host initiated SSO, enabling
ms.assetid: a11d314a-6ff9-4d0a-89c3-c412541c2cec
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6e7440742c5bb8efb8d867ecc96447390336b84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-and-disable-host-initiated-sso"></a>如何启用和禁用主机启动的 SSO
默认情况下，单一登录系统中不启用主机启动的单一登录，而必须由 SSO 管理员启用。  
  
### <a name="to-enable-host-initiated-sso-using-the-mmc-snap-in"></a>使用 MMC 管理单元启用主机启动的 SSO  
  
1.  上**启动**菜单上，单击**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击“系统” ，然后单击“属性” 。  
  
4.  单击**选项**选项卡。  
  
5.  选择**启用主机启动的 SSO**框中，然后单击**确定**。  
  
### <a name="to-enable-host-initiated-sso-using-the-command-line"></a>使用命令行启用主机启动的 SSO  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器 >: \program Files\Enterprise 单一登录。  
  
4.  类型**ssomanage-启用 hisso**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
 禁用 SSO 将应用于整个 SSO 系统，与主机启动的 SSO 相关的所有操作都将关闭。  
  
#### <a name="to-disable-host-initiated-sso-using-the-mmc-snap-in"></a>使用 MMC 管理单元禁用主机启动的 SSO  
  
1.  上**启动**菜单上，单击**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击“系统” ，然后单击“属性” 。  
  
4.  单击**选项**选项卡。  
  
5.  清除**启用主机启动的 SSO**框中，然后单击**确定**。  
  
#### <a name="to-disable-host-initiated-sso-using-the-command-line"></a>使用命令行禁用主机启动的 SSO  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器 >: \program Files\Enterprise 单一登录。  
  
4.  类型**ssomanage-禁用 hisso**根据。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [主机启动的 SSO](../core/host-initiated-sso.md)