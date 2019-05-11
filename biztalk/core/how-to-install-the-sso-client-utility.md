---
title: 如何安装 SSO 客户端实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, client utility
- client utility [SSO]
- SSO, installing
ms.assetid: e14d257e-2fde-46af-b90c-5dbc0884536b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc7970f397c8b5c076edd7bf0f29e3d7cf8becd3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384918"
---
# <a name="how-to-install-the-sso-client-utility"></a>如何安装 SSO 客户端实用工具
独立的 SSO 客户端实用工具 （命令行实用程序和用户界面基于） 允许最终用户在 SSO 数据库中配置其客户端映射。 可以从与 SSO 管理功能一起安装的自解压缩文件 (SSOClientInstall.exe) 安装客户端实用工具。 管理员还可以安装程序包提供给客户端用户通过将安装程序包的副本放在网络共享上。  
  
 若要安装 SSO 客户端实用工具，您必须运行以下操作系统之一的客户端计算机上：  
  
- [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]  
  
- [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] 或[!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)](只需使用基于 UI 的 SSO 客户端实用工具或利用企业 SSO 的托管互操作性组件)。  
  
  安装 SSO 客户端实用工具后, 可以启动从**启动**菜单中单击**程序**， **Microsoft 企业单一登录**，，然后**SSO 客户端实用工具**。  
  
### <a name="to-install-the-sso-client-utility"></a>若要安装 SSO 客户端实用工具  
  
1.  双击安装程序包 SSOClientInstall。  
  
    > [!NOTE]
    >  让企业单一登录管理员提供在企业中此文件的位置。  
  
     **WinZip 自解压缩程序**程序看起来。  
  
2.  选择你想要解压缩文件，然后单击的文件夹**解压缩**。  
  
     建议将临时文件夹中的文件解压缩。  
  
     **企业单一登录客户端安装程序**程序看起来。  
  
3.  上**欢迎使用企业单一登录客户端**页上，单击**下一步**。  
  
4.  在许可协议页上，单击**我接受此许可协议条款**，然后单击**下一步**。  
  
5.  上**用户信息**页上，键入用户名、 组织名称，然后单击**下一步**。  
  
6.  上**开始安装**页上，单击**安装**。  
  
7.  上**完成企业单一登录客户端向导**页上，单击**完成**。  
  
8.  通过执行以下任一操作指定的 SSO 服务器：  
  
    -   ENTSSO 管理 Mmc 管理单元打开。 **选择 SSO Server**对话框将出现。 输入或浏览到你想要执行管理操作时连接到 SSO 服务器。 若要指定 SSO 服务器的所有用户在计算机上，选择**为所有用户设置 SSO 服务器**。  
  
         或  
  
    -   在命令提示符处，键入`ssomanage –server`来指定所需的 SSO 服务器。 此外可以键入`ssomanage -serverall`以指定执行管理操作时，此计算机的所有用户将都连接到 SSO 服务器。  
  
## <a name="see-also"></a>请参阅  
 [如何安装 SSO 管理组件](../core/how-to-install-the-sso-administration-component.md)   
 [配置 SSO](../core/configuring-sso.md)   
 [安装 SSO](../core/installing-sso.md)