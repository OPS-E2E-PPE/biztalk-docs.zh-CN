---
title: "将跟踪数据发送到 Azure Application Insights |Microsoft 文档"
description: "安装功能包启用的跟踪数据与 BizTalk Server 中的 Azure Application Insights 的分析"
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a65ffd2c5ee76d857effde6ab82dddf17b3de4b
ms.sourcegitcommit: 30189176c44873e3de42cc5f2b8951da51ffd251
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="send-tracking-data-to-azure-application-insights-using-biztalk-server"></a>将跟踪数据发送到 Azure Application Insights 使用 BizTalk Server

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，您可以过程，并将跟踪数据发送到 Azure Application Insights。 使用 Application Insights 功能来接收端口、 发送端口和业务流程从跟踪您的实例。
          
> [!IMPORTANT]
> 此功能当前并不适用于 SQL 命名实例。

## <a name="prerequisites"></a>先决条件
* 创建的新实例[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource)。 在其属性，复制**检测密钥**。 将其粘贴在另一个文件因此你必须准备就绪。 我们使用内 BizTalk Server 此密钥。 
* 安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

## <a name="enable-analytics-for-your-environment"></a>启用针对你的环境分析

1. 打开**BizTalk Server 管理**控制台中，右键单击**BizTalk 组**，然后选择**设置**。 
2. 检查**启用组级别分析**。
3. 有关**目标类型**，选择**Application Insight**从列表中。
4. 有关**连接参数**，输入你的 Application Insights **[检测密钥](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)** （在 Azure 门户中可用）。 你的组设置类似于以下内容： 

    ![启用针对你的环境分析](../core/media/environmentsettingapplicationinishgt.PNG)

5. 单击“确定”保存更改。 

在启用之后，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]已准备好将数据传输到 Application Insights。 接下来，启用在端口和业务流程的分析。 

## <a name="enable-analytics-on-your-artifacts"></a>启用你的项目上的分析

1. 在 BizTalk Server 管理中，右键单击**接收端口**，**发送端口**或**orchestration**，然后选择**跟踪**。
2. 下**分析**，检查**启用分析**，类似于以下。 此设置将开始跟踪和传输到 Application Insights 从项目的数据。
    
    ![业务流程的跟踪数据](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. 单击“确定”保存更改。
4. 重新启动跟踪主机实例，并确认启动 BizTalk 应用程序。

接下来，运行以查看你的数据的 Application Insights 中的查询。  

> [!TIP]
> 连接你的 BizTalk Server 分析与其他系统，若要了解更多的组织数据。

## <a name="view-your-data"></a>查看你的数据
后的数据发送到 Application Insights，可以使用在 Azure 中的分析工具来创建高级的查询，并分析你的数据。

1. 登录到[Azure 门户](https://portal.azure.com)。
2. 打开 Application Insights 资源，并选择**指标资源管理器**。
3. 空的图表可能会显示。 在图表中，选择**编辑**。 下**指标**，选择**自定义**若要查看可用的跟踪的属性。 选择的某些不同的选项来查看图表上的更改： 

    ![Azure 分析](../core/media/azure-stream-metrics-custom.png)

4. 返回到你的 Application Insights 资源，并选择**分析**。 在**用法**，选择**运行**。 示例查询将执行，并且结果将显示在图表中。  

> [!TIP]
> Azure 的 Application Insights 是一个功能强大的工具。 资源可帮助你在 Application Insights 在编写查询[Application Insights 中的分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)，甚至可以开始[什么是 Application Insights？](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-overview)。

## <a name="where-the-data-is-stored"></a>数据存储位置

跟踪数据应会显示相当迅速地 （在几分钟内） 在 Application Insights。 如果它不存在，然后可能有跟踪主机的问题。 在 SQL Server，分析数据存储在 BizTalkMsgBoxDb 数据库，请在 TrackingData_2_*x*表。 在 SQL Server Management Studio，在以下四个表上中返回前 1000年行。 如果数据不存在，然后跟踪主机是不将数据移到 BizTalkDTADb 数据库。 

一些可能的解决方法：

1. 重新启动跟踪主机。
2. 创建专用的跟踪主机。 安装 BizTalk Server 时，可能在启用跟踪**BizTalk Server 应用程序 1**主机。 通常情况下，此应用程序还用于处理消息。 创建于专用的跟踪主机可以使用以下步骤： 

    1. 在 BizTalk Server 管理中，打开 BizTalk Server 应用程序 1 主机的属性，并取消选中**允许主机跟踪**。 重新启动此主机实例。

    2. 创建新的主机名为**跟踪**，并检查**允许主机跟踪**。 创建一个主机实例，并启动它。

现在，再次查询 BizTalkMsgBoxDb TrackingData_2_x 表。 如果表为空，数据移动，，并且应开始在 Application Insights 中显示。
    
## <a name="see-also"></a>另请参阅
 [配置功能包](../core/configure-the-feature-pack.md)