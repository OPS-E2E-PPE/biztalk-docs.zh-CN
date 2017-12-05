---
title: "启用 Power BI |Microsoft 文档"
description: "BizTalk server 中功能包安装 Power BI 模板"
ms.custom: fp1
ms.date: 11/07/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 585927b494f51ddd3ab7abd0503df7586c30b041
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configure-the-power-bi-operational-data-feed-in-biztalk-server"></a>配置 Power BI 操作数据馈送 BizTalk Server 中

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、 将跟踪发送到 Power BI 使用 Power BI 模板提供，或创建你自己。 

## <a name="what-is-operational-data"></a>操作数据是什么
操作数据是信息的实例和消息流经你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。 操作数据源是你在获取看组中心数据库中的相同数据[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]。 数据访问和使用可视化工具，包括 Power BI 查询。 

源包括以下表，数据：
* 应用程序数据
* AS2 状态记录
* 批处理的信息
* 实例信息
* 交换聚合记录
* 交换状态记录
* 消息
* 订阅
* 被跟踪的事件
* 事务报表
* 事务集

> [!TIP]
> [PowerBI.com](http://powerbi.microsoft.com)是一个很好的资源，若要了解，并了解有关 Power BI 的详细信息。

## <a name="prerequisites"></a>先决条件
* 下载并安装[Power BI Desktop](https://powerbi.microsoft.com/desktop/)具有对网络访问的任何计算机上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 安装[功能包 2](https://aka.ms/bts2016fp2)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 在上安装 IIS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 在大多数[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境中，IIS 已安装。 请参阅[的硬件和软件要求 BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。 确认通过打开安装了 IIS **Internet Information Services Manager**。 
* 可选。 安装和配置[Power BI 网关](https://powerbi.microsoft.com/gateway/)连接[PowerBI.com](http://powerbi.microsoft.com)与你的本地 BizTalk Server。 如果你不使用本地 BizTalk Server，则不需要网关。

## <a name="step-1-enable-operational-data"></a>步骤 1： 启用操作数据

1. 以管理员身份运行 Windows PowerShell (**启动**菜单上，键入**PowerShell**，右键单击，然后选择**以管理员身份运行**)。 
2. 转到 BizTalk 安装文件夹 (例如，键入： `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。
3. 在以下文本，将`Default Web Site`， `operationalDataServiceAppPool`， `domain\user`， `password`，和`domain\group`用你的值：

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user\> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1\>, <domain>\<group2\>, <domain>\<user\>, <domain>\<user2\>'
    ```

    * **服务**： 服务配置 (**OperationalData**适用于 Power BI)
    * **WebSiteName**： 现有 IIS 网站承载该服务。 默认值是**Default Web Site**。
    * **ApplicationPool**： 服务使用的应用程序池。 如果存在，将不会创建一个新。 默认值是**DefaultAppPool**。
    * **ApplicationPoolUser**： 配置要作为此用户标识运行的应用程序池。 必须具有 BizTalk Server 运算符或更高特权。
    * **ApplicationPoolUserPassword**: ApplicationPoolUser 密码
    * **AuthorizationAccount**： 的授权组或用户可以使用此服务的列表

    在以下示例中，我们使用`Default Web Site`，创建名为应用程序池`PowerBIAppPool`，运行作为应用程序池`bootcampbts2016\btsservice`帐户，请使用`BIZTALK-serviceacct`作为用户帐户密码，然后让`BizTalk Server Administrators`组权限。 请务必输入以下、 包括单报价周围用带空格的值： 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName 'Default Web Site' -ApplicationPool PowerBIAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    完成后，在 IIS 内创建 BizTalkOperationalDataService 应用程序：  
    ![BizTalkMOperationalDataServer 应用程序](../core/media/biztalkmanagementservice-apppool.png)


4. 若要确认它是否工作，请浏览到`http://localhost/BizTalkOperationalDataService`。 

    如果你提示登录，请使用是你在上一步中输入域 \ 组的成员的帐户登录 (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。 

    如果提示你打开或保存 BizTalkOperationalDataService.json，然后完成您的安装。 你可以将它保存到本地，，然后在记事本或 Visual Studio 能够看到的内容中打开它。 

> [!WARNING]
> 在 IIS 中的 BizTalkOperationalDataService 应用程序使用 web.config 文件。 Web.config 中的元素**区分大小写**。 因此当你执行 Windows PowerShell 脚本，请确保输入正确的大小写的`-AuthorizationRoles`值。 如果你不确定的这种情况，下面是找出的简单办法： 
> 
> 1. 打开**计算机管理**，然后展开**本地用户和组**。
> 2. 选择**组**，向下滚动到**SQLServer...** 组。 
> 3. 在下面的示例，请注意**BOOTCAMPBTS2016**处于全部大写。 如果看到全部大写，然后在全部大写中输入计算机名称。 
> 
> ![计算机名显示在全部大写](../core/media/groups-case.png)

## <a name="step-2-use-the-template-in-power-bi"></a>步骤 2： 在 Power BI 中使用模板

1. 下载并安装[Power BI Desktop](https://powerbi.microsoft.com/desktop/) BizTalk 服务器上。 你可以选择打开它，它是可选的。 如果你有工作或学校帐户，可能有权访问 Power BI。 请尝试使用该帐户登录。 或者，你可以免费试用注册后。 
2. 打开`\Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService`文件夹，然后打开`BizTalkOperationalData.pbit`文件：  
![打开 pbit 文件](../core/media/operational-data-pbit.png)

3. Power BI desktop 将打开，并且系统提示你提供 URL。 输入`http://localhost/<yourWebSite>`为 OData 数据源创建的 URL。 例如，输入`http://localhost/BizTalkOperationalDataService`。 你的 URL 与以下类似：  
![输入的 URL](../core/media/operational-data-url.png)

4. 选择**负载**。 窗口加载并连接到不同的 oData 源 BizTalkOperationalDataService.json 文件中。 操作完成时，仪表板将显示有关你的环境的详细信息。

## <a name="couldnt-authenticate"></a>无法进行身份验证
如果你收到`couldn't authenticate with the credentials provided`消息类似于以下内容，则可能你的应用程序池标识没有足够的访问权限与 BizTalk Server 数据库。 你可以更改 IIS 中的应用程序池标识为具有多个权限的帐户可能你的登录的用户帐户 （其本地管理员权限）。 

![无法使用提供的凭据进行身份验证](../core/media/operational-data-authentication-error.png)

## <a name="do-more"></a>执行更多操作
这仅仅是个开始。 Power BI 还具有可以安装在本地 BizTalk Server 的网关。 使用网关，可以发布你的仪表板、 获取实时数据，并创建一个计划来刷新仪表板。 以下博客能够很好地详细说明这些步骤： 

* [如何发布 Power bi – 分步配置 BizTalk 操作数据](https://blog.sandro-pereira.com/2017/05/07/biztalk-server-2016-feature-pack-1-how-to-publish-biztalk-operational-data-power-bi-step-by-step-configuration-part-3/)

[引导学习](https://powerbi.microsoft.com/guided-learning/)也是若要了解有关 Power BI 的详细信息，并且可以执行的所有操作的好地方。 

## <a name="see-also"></a>另请参阅

[了解有关 Power BI 的详细信息](https://www.powerbi.com)  
[配置功能包](../core/configure-the-feature-pack.md)
