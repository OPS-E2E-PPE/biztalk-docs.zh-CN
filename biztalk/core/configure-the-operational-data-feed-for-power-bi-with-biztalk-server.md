---
title: 启用 Power BI |Microsoft Docs
description: 为 BizTalk Server 功能包中安装 Power BI 模板
ms.custom: fp1
ms.date: 6/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba5e0944c8b816a4800618940048b3e427143ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391441"
---
# <a name="configure-the-power-bi-operational-data-feed-in-biztalk-server"></a>配置 BizTalk Server 中的源的 Power BI 操作数据

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、 将跟踪发送到 Power BI 中使用 Power BI 模板提供，或创建您自己。 

## <a name="what-is-operational-data"></a>什么是操作数据
操作数据是信息的实例和消息流经您[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。 操作数据源是相同的数据获取查看组中心[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]。 访问和查询使用可视化工具，包括 Power BI 的数据。 

源包含以下数据表：
* 应用程序数据
* AS2 状态记录
* 批处理的信息
* 实例信息
* 交换聚合记录
* 交换状态记录
* 消息
* 订阅
* 跟踪的事件
* 事务报告
* 事务集

> [!TIP]
> [PowerBI.com](http://powerbi.microsoft.com)是一个不错的资源以了解并了解有关 Power BI 的详细信息。

## <a name="prerequisites"></a>先决条件
* 下载并安装[Power BI Desktop](https://powerbi.microsoft.com/desktop/)具有网络访问权限的任何计算机上你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 安装[功能包 2](https://aka.ms/bts2016fp2)，或更高版本上功能包，你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 上安装 IIS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 在大多数[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境中，IIS 已安装。 请参阅[硬件和软件要求 BizTalk Server 2016 的](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。 确认 IIS 安装通过打开**Internet Information Services Manager**。 
* 可选。 安装和配置[Power BI Gateway](https://powerbi.microsoft.com/gateway/)连接[PowerBI.com](http://powerbi.microsoft.com)与你的本地 BizTalk Server。 如果您不使用的本地 BizTalk Server，则不需要网关。

## <a name="step-1-enable-operational-data"></a>第 1 步：启用操作数据

1. 以管理员身份运行 Windows PowerShell (**启动**菜单中，键入**PowerShell**，右键单击，然后选择**以管理员身份运行**)。 
2. 转到 BizTalk 安装文件夹 (例如，键入： `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。
3. 在以下文本替换`Default Web Site`， `operationalDataServiceAppPool`， `domain\user`， `password`，和`domain\group`与你的值：

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user\> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1\>, <domain>\<group2\>, <domain>\<user\>, <domain>\<user2\>'
    ```

   * **服务**:若要配置的服务 (**OperationalData**适用于 Power BI)
   * **WebSiteName**:现有 IIS web 站点承载的服务。 默认值是**默认网站**。
   * **ApplicationPool**:使用该服务的应用程序池。 如果存在，则不会创建一个新。 默认值是**DefaultAppPool**。
   * **ApplicationPoolUser**:配置要作为此用户身份运行的应用程序池。 必须具有 BizTalk Server 操作员或更高的权限。
   * **ApplicationPoolUserPassword**:ApplicationPoolUser 密码
   * **AuthorizationAccount**:授权组或用户可以使用此服务的列表

     在以下示例中，我们将使用`Default Web Site`，创建名为应用程序池`PowerBIAppPool`，运行作为应用程序池`bootcampbts2016\btsservice`帐户，请使用`BIZTALK-serviceacct`作为用户帐户密码，并授予`BizTalk Server Administrators`组权限。 确保输入以下信息，包括单个空格周围值加引号： 

     ```Powershell
     FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName 'Default Web Site' -ApplicationPool PowerBIAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
     ```

     完成后，BizTalkOperationalDataService 应用程序是在 IIS 中创建：  
     ![BizTalkMOperationalDataServer 应用程序](../core/media/biztalkmanagementservice-apppool.png)


4. 若要确认其是否工作，请浏览到`http://localhost/BizTalkOperationalDataService`。 

    如果系统会提示登录，是你在上一步中输入域 \ 组的成员的帐户登录 (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。 

    如果系统提示打开或保存 BizTalkOperationalDataService.json，你的安装已完成。 您可以将它保存在本地，并打开记事本或 Visual Studio 以查看内容。 

> [!WARNING]
> BizTalkOperationalDataService 应用程序在 IIS 中的使用的 web.config 文件。 Web.config 中的元素**区分大小写**。 因此在执行 Windows PowerShell 脚本，请确保输入正确的大小写的`-AuthorizationRoles`值。 如果您不确定的这种情况，下面是找出的简单办法： 
> 
> 1. 打开**计算机管理**，然后展开**本地用户和组**。
> 2. 选择**组**，向下滚动到**SQLServer...** 组。 
> 3. 在下面的示例，请注意**BOOTCAMPBTS2016**是在全大写形式。 如果您看到全部大写的则所有 caps 中输入计算机名称。 
> 
> ![计算机名称是在全大写形式](../core/media/groups-case.png)

## <a name="step-2-use-the-template-in-power-bi"></a>第 2 步：在 Power BI 中使用的模板

1. 下载并安装[Power BI Desktop](https://powerbi.microsoft.com/desktop/) BizTalk 服务器上。 您可以选择将其打开，它是可选的。 如果您有工作或学校帐户，可能有权访问 Power BI。 请尝试使用该帐户登录。 或者，您可以在注册后免费试用它。 
2. 打开`\Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService`文件夹，并打开`BizTalkOperationalData.pbit`文件：  
![打开 pbit 文件](../core/media/operational-data-pbit.png)

3. Power BI desktop 将打开，并且会提示输入一个 URL。 输入`http://localhost/<yourWebSite>`为 OData 数据源创建的 URL。 例如，输入 `http://localhost/BizTalkOperationalDataService`。 你的 URL 类似于以下内容：  
![输入的 URL](../core/media/operational-data-url.png)

4. 选择**负载**。 在窗口加载并连接到不同的 oData 源 BizTalkOperationalDataService.json 文件中。 操作完成时，仪表板显示有关你的环境的详细信息。

## <a name="couldnt-authenticate"></a>无法进行身份验证
如果收到`couldn't authenticate with the credentials provided`消息类似于以下内容，则可能你的应用程序池标识不具有足够到 BizTalk Server 数据库的访问权限。 您可以更改 IIS 中的应用程序池标识到具有更多权限的帐户可能已登录用户帐户 （它具有本地管理员权限）。 

![无法使用提供的凭据进行身份验证](../core/media/operational-data-authentication-error.png)

## <a name="do-more"></a>执行更多操作
这仅仅是个开始。 Power BI 还提供可以在本地 BizTalk Server 安装的网关。 使用网关，可以发布你的仪表板，获取实时数据，并创建计划以刷新仪表板。 以下博客能够很好地详细描述这些步骤： 

* [如何将发布 Power BI – 分步配置上的 BizTalk 操作数据](https://blog.sandro-pereira.com/2017/05/07/biztalk-server-2016-feature-pack-1-how-to-publish-biztalk-operational-data-power-bi-step-by-step-configuration-part-3/)

[引导式学习](https://powerbi.microsoft.com/guided-learning/)也是一个很好的了解有关 Power BI 的详细信息以及您可以执行的所有操作。 

## <a name="see-also"></a>另请参阅

[了解有关 Power BI 的详细信息](https://www.powerbi.com)  
[配置功能包](../core/configure-the-feature-pack.md)
