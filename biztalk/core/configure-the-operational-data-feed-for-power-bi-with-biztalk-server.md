---
title: "配置操作数据源的 Power BI 与 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: "11"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 09b1b1fd7f350e168b2bb13d6bee2e45c12d49cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-operational-data-feed-for-power-bi-with-biztalk-server"></a>配置操作数据源的 Power BI 与 BizTalk Server
读取通过 oData 数据源提供的操作数据[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、 将跟踪发送到 Power BI 使用 Power BI 模板提供，或创建你自己。 

## <a name="what-is-operational-data"></a>操作数据是什么
操作数据是信息的实例和消息流经你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。 操作数据源是你在获取看组中心数据库中的相同数据[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]控制台。 数据可访问和使用可视化工具，包括 Power BI 查询。 

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
* 安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 在上安装 IIS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 在大多数[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境中，IIS 已安装。 请参阅[的硬件和软件要求 BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。 

## <a name="enable-operational-data-feed"></a>启用操作数据馈送

1. 以管理员身份运行 Windows PowerShell (**启动**菜单上，键入**PowerShell**，右键单击，然后选择**以管理员身份运行**)。 
2. 浏览到的文件夹位置[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]安装**Program Files (x86)/Microsoft BizTalk Server 2016**
3. 运行以下命令。 请务必更新你`website`， `domain\user`， `password`，和`domain\group`用你的值： 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1>, <domain>\<group2>'
    ```
4. 运行该脚本后，浏览新 IIS 应用程序：  
    1. 打开 web 浏览器
    2. 转到**http://localhost/BizTalkOperationalDataService**

## <a name="use-the-power-bi-template"></a>使用 Power BI 模板
若要访问 Power BI 模板文件，并使用从 Microsoft 提供的可视化效果，请使用以下步骤：

1. 下载并安装[Power BI Desktop](https://powerbi.microsoft.com/desktop/)。
2. 浏览到 BizTalk Server 文件夹下**Program Files (x86) \Microsoft BizTalk Server 2016\OperationalDataService**。
3. 打开**BizTalkOperationalData.pbit**文件。
4. 出现提示时从 Power BI，将粘贴**http://localhost/\<yourWebSite\>** 为 OData 数据源创建的 URL。 例如，输入**http://localhost/OperationalDataService**。 

    你的 URL 与以下类似： 
    
    ![粘贴到 Power BI 模板文件的 OData URL](../core/media/pasteurltopowerbitempaltefile.PNG)

5. 选择**负载**来填充你的 Power BI 报表中的字段。 
6. 模板文件自动生成的信息和可用表从 OData 数据源。

操作数据公开通过计算机，并可以访问和执行基于权限的其他应用程序。 

若要了解有关 Power BI 中，以及如何将发布的报表联机转至[PowerBI.com](http://powerbi.microsoft.com)

## <a name="see-also"></a>另请参阅

[了解有关 Power BI 的详细信息](https://www.powerbi.com)  
[配置功能包](../core/configure-the-feature-pack.md)