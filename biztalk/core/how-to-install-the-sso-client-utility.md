---
title: 如何安装 SSO 客户端实用工具 |Microsoft 文档
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
ms.openlocfilehash: 4eba4e0747c9566c5303e04602d957173cc56052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254245"
---
# <a name="how-to-install-the-sso-client-utility"></a>如何安装 SSO 客户端实用工具
独立的 SSO 客户端实用工具 （命令行实用程序和用户的基于接口） 允许最终用户在 SSO 数据库中配置其客户端映射。 你可以从使用 SSO 管理功能安装的自解压文件 (SSOClientInstall.exe) 安装客户端实用工具。 管理员还可以安装程序包可向客户端用户通过将安装包的副本放在网络共享上。  
  
 若要安装 SSO 客户端实用工具，你必须运行以下操作系统之一的客户端计算机上：  
  
-   [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]  
  
-   [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] 或 [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]（仅当使用基于 UI 的 SSO 客户端实用工具或利用企业 SSO 的托管互操作组件时才需要）。  
  
 安装后 SSO 客户端实用工具，可以启动从**启动**菜单中单击**程序**， **Microsoft Enterprise 上单一登录**，，然后**SSO 客户端实用工具**。  
  
### <a name="to-install-the-sso-client-utility"></a>若要安装 SSO 客户端实用工具  
  
1.  双击安装程序包 SSOClientInstall。  
  
    > [!NOTE]
    >  向企业单一登录管理员索取企业中的此文件的位置。  
  
     **WinZip 自动解压缩程序**程序显示。  
  
2.  选择你想要解压缩文件，然后单击的文件夹**Unzip**。  
  
     建议解压缩临时文件夹中的文件。  
  
     **企业单一登录客户端安装程序**程序显示。  
  
3.  上**企业单一登录客户端欢迎**页上，单击**下一步**。  
  
4.  在许可协议页上，单击**我接受此许可协议的条款**，然后单击**下一步**。  
  
5.  上**用户信息**页上，键入你的用户姓名、 组织名称，然后单击**下一步**。  
  
6.  上**开始安装**页上，单击**安装**。  
  
7.  上**完成企业单一登录客户端向导**页上，单击**完成**。  
  
8.  指定的 SSO 服务器通过执行以下任一操作：  
  
    -   打开 ENTSSO 管理 MMC 管理单元中。 **选择 SSO 服务器**对话框将出现。 输入或浏览到你想要执行管理操作时，连接到 SSO 服务器。 若要指定计算机上的 SSO 服务器的所有用户，选择**设置 SSO 服务器的所有用户**。  
  
         或  
  
    -   在命令提示符处，键入`ssomanage –server`指定所需的 SSO 服务器。 您还可以键入`ssomanage -serverall`指定执行管理操作时，此计算机的所有用户将都连接到的 SSO 服务器。  
  
## <a name="see-also"></a>另请参阅  
 [如何安装 SSO 管理组件](../core/how-to-install-the-sso-administration-component.md)   
 [配置 SSO](../core/configuring-sso.md)   
 [安装 SSO](../core/installing-sso.md)