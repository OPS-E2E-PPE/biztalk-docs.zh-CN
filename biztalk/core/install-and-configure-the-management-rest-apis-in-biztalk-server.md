---
title: 安装和配置管理 REST Api |Microsoft Docs
description: 查询在 BizTalk Server 功能包中使用管理数据 REST Api 在 BizTalk 环境中的项目
ms.custom: fp1
ms.date: 02/25/2019
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 680b7390462a7a64d3064f621b2011952ba2551c
ms.sourcegitcommit: 0e14c3e018b091d81d0e4a68fafc10f6e31697e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56828562"
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a>安装和配置 BizTalk Server 中的管理 REST Api

## <a name="what-are-management-data-apis"></a>管理数据的 Api 有哪些？
管理数据的 Api 是允许您远程更新、 添加和查询中的不同产物的状态的终结点在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。 终结点将添加使用 REST，并附带 swagger 定义。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，没有安装这些 REST Api 和它们的 swagger 定义的 Windows PowerShell 脚本。 这些 Api 进行 REST 调用来远程管理端口、 业务流程、 合作伙伴、 协议、 管道和的详细信息。 

若要查看可用的 Api，以及你可以操作，请参阅[功能包 REST API 参考](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016)。

## <a name="prerequisites"></a>先决条件
* 安装[功能包 2](https://aka.ms/bts2016fp2)上你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

* 上安装 IIS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 确认 IIS 已安装 BizTalk Server 上，通过打开**Internet Information Services Manager**。 

  在大多数[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境中，IIS 已安装。 请参阅[硬件和软件要求 BizTalk Server 2016 的](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。 

## <a name="step-1-install-the-rest-apis"></a>步骤 1：安装 REST Api

1. 以管理员身份运行 Windows PowerShell (**启动**菜单 > 类型**PowerShell** > 右键单击 >**以管理员身份运行**)。 
2. 转到 BizTalk 安装文件夹 (例如，键入： `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。
3. 在以下文本替换`Default Web Site`， `mgmtServiceAppPool`， `domain/user`， `password`，和`domain\group`与你的值：

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    在以下示例中，我们将使用`Default Web Site`，创建名为应用程序池`RESTAppPool`，运行作为应用程序池`bootcampbts2016\btsservice`帐户，请使用`BIZTALK-serviceacct`作为用户帐户密码，并授予 BizTalk Server Administrators 组的权限。 确保输入以下信息，包括单个空格周围值加引号： 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    完成后， **BizTalkManagementService**在 IIS 中创建应用程序：  
    ![BizTalkManagementService 应用程序](../core/media/biztalkmanagementservice-apppool.png)

4. 若要确认其是否工作，请浏览到`http://localhost/BizTalkManagementService/swagger`。 如果系统会提示登录，是你在上一步中输入域 \ 组的成员的帐户登录 (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。 

> [!WARNING]
> BizTalkManagementService 应用程序在 IIS 中的使用的 web.config 文件。 Web.config 中的元素**区分大小写**。 因此在执行 Windows PowerShell 脚本，请确保输入正确的大小写的`-AuthorizationRoles`值。 如果您不确定的这种情况，下面是找出的简单办法： 
> 
> 1. 打开**计算机管理**，然后展开**本地用户和组**。
> 2. 选择**组**，向下滚动到**SQLServer...** 组。 
> 3. 在下面的示例，请注意**BOOTCAMPBTS2016**是在全大写形式。 如果您看到全部大写的则所有 caps 中输入计算机名称。 
> 
> ![计算机名称是在全大写形式](../core/media/groups-case.png)

现在，通过 IIS 公开 REST Api，它们可以访问和执行由其他应用程序。 [功能包 REST API 参考](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016)列出了 Api。

您可以更改谁有权访问通过手动更新**web.config**文件，它是管理应用程序的根文件夹中。 例如，使用以下命令以允许任何人访问 swagger 输出： 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a>步骤 2：测试 Api

1. 在 BizTalk 服务器上，浏览到`http://localhost/BizTalkManagementService/swagger`。

2. 滚动到**主机**，然后选择**显示/隐藏**。 GET 命令;单击此行：  
![获取所有主机](../core/media/managment-rest-apis-hosts-get.png)

3. 它显示的详细信息。 选择**试试看**:  
![进行试用](../core/media/managment-rest-apis-hosts-tryitout.png)

4. 响应正文将返回所有主机：  
![响应](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> 如果浏览到`http://localhost/BizTalkManagementService`，应收到一个 500 错误。 这是一件好事。 只需添加`/swagger`到末尾的 URL，并且您将看到可用的 REST Api。 


## <a name="see-also"></a>另请参阅
 [配置功能包](../core/configure-the-feature-pack.md)