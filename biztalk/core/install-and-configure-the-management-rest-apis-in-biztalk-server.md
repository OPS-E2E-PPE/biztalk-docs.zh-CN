---
title: "安装和配置管理 REST Api |Microsoft 文档"
description: "查询中使用 BizTalk Server 中的功能包 1 管理数据 REST Api 你 BizTalk 环境的项目的状态"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 009b3b0bb333b8f92f6235da57b0c3e9f5daca96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a>安装和配置 BizTalk Server 中的管理 REST Api
使用 Windows PowerShell 脚本来启用远程管理的 REST Api 你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。

## <a name="what-are-management-data-apis"></a>管理数据 Api 有哪些？
管理数据 Api 是终结点，可以远程更新、 添加和查询中的不同项目的状态你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。 终结点将添加使用 REST，并附带 Swagger 定义。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，没有安装这些 REST Api 和其 swagger 定义的 Windows PowerShell 脚本。 这些 Api 进行 REST 调用来远程管理端口、 业务流程、 合作伙伴、 协议、 管道，和的详细信息。 

本主题演示了如何安装 REST Api。

## <a name="prerequisites"></a>先决条件
* 安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

* 在上安装 IIS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 在大多数[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境中，IIS 已安装。 请参阅[的硬件和软件要求 BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。

## <a name="enable-the-rest-apis"></a>启用 REST Api

1. 以管理员身份运行 Windows PowerShell (**启动**菜单上，键入**PowerShell**，右键单击，然后选择**以管理员身份运行**)。 
2. 浏览到 BizTalk 文件夹下**Program Files (x86)/Microsoft BizTalk Server 2016**
3. 运行以下命令。 请务必更新你`website`， `domain/user`， `password`，和`domain\group`用你的值： 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```
4. 运行该脚本后，浏览新 IIS 应用程序：  
    1. 打开 web 浏览器
    2. 浏览到**http://localhost/OperationalDataService/swagger**

5. Swagger 定义加载。 你还可以更改谁有权通过更新**web.config**管理应用程序的根文件夹中的文件。

REST Api 公开，通过该计算机，和可以访问和执行其他应用程序。 


## <a name="see-also"></a>另请参阅
 [配置功能包](../core/configure-the-feature-pack.md)