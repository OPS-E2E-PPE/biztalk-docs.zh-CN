---
title: "安装和配置管理 REST Api |Microsoft 文档"
description: "查询中使用 BizTalk Server 中的功能包的管理数据 REST Api 你 BizTalk 环境的项目"
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e05b122047d7e303ed4e187fec19725cce9ae398
ms.sourcegitcommit: 30189176c44873e3de42cc5f2b8951da51ffd251
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a>安装和配置 BizTalk Server 中的管理 REST Api

## <a name="what-are-management-data-apis"></a>管理数据 Api 有哪些？
管理数据 Api 是终结点，可以远程更新、 添加和查询中的不同项目的状态你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。 终结点将添加使用 REST，并附带 swagger 定义。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，没有安装这些 REST Api 和其 swagger 定义的 Windows PowerShell 脚本。 这些 Api 进行 REST 调用来远程管理端口、 业务流程、 合作伙伴、 协议、 管道，和的详细信息。 

## <a name="prerequisites"></a>先决条件
* 安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

* 在上安装 IIS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 在大多数[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境中，IIS 已安装。 请参阅[的硬件和软件要求 BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。 确认打开 BizTalk 服务器上安装 IIS **Internet Information Services Manager**。 

## <a name="step-1-install-the-rest-apis"></a>步骤 1： 安装 REST Api

1. 以管理员身份运行 Windows PowerShell (**启动**菜单上，键入**PowerShell**，右键单击，然后选择**以管理员身份运行**)。 
2. 转到 BizTalk 安装文件夹 (例如，键入： `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。
3. 在以下文本，将`Default Web Site`， `mgmtServiceAppPool`， `domain/user`， `password`，和`domain\group`用你的值：

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    在以下示例中，我们使用`Default Web Site`，创建名为应用程序池`RESTAppPool`，运行作为应用程序池`bootcampbts2016\btsservice`帐户，请使用`BIZTALK-serviceacct`作为用户帐户密码，然后让 BizTalk Server Administrators 组权限。 请务必输入以下、 包括单报价周围用带空格的值： 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    完成后， **BizTalkManagementService**在 IIS 内创建应用程序：  
    ![BizTalkManagementService 应用程序](../core/media/biztalkmanagementservice-apppool.png)

4. 若要确认它是否工作，请浏览到`http://localhost/BizTalkManagementService/swagger`。 如果你提示登录，请使用是你在上一步中输入域 \ 组的成员的帐户登录 (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。 

> [!WARNING]
> 在 IIS 中的 BizTalkManagementService 应用程序使用 web.config 文件。 Web.config 中的元素**区分大小写**。 因此当你执行 Windows PowerShell 脚本，请确保输入正确的大小写的`-AuthorizationRoles`值。 如果你不确定的这种情况，下面是找出的简单办法： 
> 
> 1. 打开**计算机管理**，然后展开**本地用户和组**。
> 2. 选择**组**，向下滚动到**SQLServer...** 组。 
> 3. 在下面的示例，请注意**BOOTCAMPBTS2016**处于全部大写。 如果看到全部大写，然后在全部大写中输入计算机名称。 
> 
> ![计算机名显示在全部大写](../core/media/groups-case.png)

现在，通过 IIS 公开 REST Api，它们可以访问和执行其他应用程序。 

你可以更改谁有权通过手动更新**web.config**文件，它是管理应用程序的根文件夹中。 例如，使用以下命令以允许任何人访问 swagger 输出： 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a>步骤 2： 测试 Api

1. 在 BizTalk Server 中，浏览到`http://localhost/BizTalkManagementService/swagger`。

2. 滚动到**主机**，然后选择**显示/隐藏**。 没有 GET 命令;单击此行：  
![获取所有主机](../core/media/managment-rest-apis-hosts-get.png)

3. 它显示的详细信息。 选择**试试看**:  
![进行试用](../core/media/managment-rest-apis-hosts-tryitout.png)

4. 响应正文将返回所有主机：  
![响应](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> 如果浏览到`http://localhost/BizTalkManagementService`，你应收到一个 500 错误。 这是一件好事。 只需添加`/swagger`到末尾的 URL，并且你将看到可用的 REST Api。 


## <a name="see-also"></a>另请参阅
 [配置功能包](../core/configure-the-feature-pack.md)