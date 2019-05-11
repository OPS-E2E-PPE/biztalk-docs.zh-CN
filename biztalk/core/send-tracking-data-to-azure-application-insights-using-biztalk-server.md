---
title: 跟踪对 Application Insights 或事件中心的数据 |Microsoft Docs
description: 若要启用分析跟踪数据的 Azure Application Insights 或 Azure 事件中心在 BizTalk Server 中的功能包安装
ms.custom: fp1, fp2
ms.date: 11/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: 10
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 981fc1222b2a9b63c8d87cf6ac35bb82b954c857
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254457"
---
# <a name="send-biztalk-tracking-data-to-azure-application-insights-or-event-hubs"></a>发送到 Azure Application Insights 或事件中心跟踪数据的 BizTalk

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，可以处理和跟踪数据发送到 Azure Application Insights。 
          
**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**:

* Application Insights 支持 SQL 默认实例和命名实例的 SQL
* 你可以处理和跟踪数据发送到 Azure 事件中心

使用这些 Azure 服务从接收端口、 发送端口和业务流程跟踪你的实例。

## <a name="prerequisites"></a>先决条件
* 创建的新实例[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource)。 BizTalk Server 使用**检测密钥**进行身份验证。
* 创建[Azure 事件中心命名空间和事件中心](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)。 BizTalk Server 使用的 SAS （命名空间级别） 或事件中心级别策略进行身份验证。
* 安装[功能包 2](https://aka.ms/bts2016fp2)上你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

## <a name="enable-analytics-for-your-environment"></a>启用针对你的环境分析

1. 打开**BizTalk Server 管理**控制台中，右键单击**BizTalk 组**，然后选择**设置**。 
2. 检查**启用组级别分析**。
3. 有关**目标类型**，选择**Application Insight**或**事件中心**从列表中。
    ![启用针对你的环境分析](../core/media/environmentsettingapplicationinishgt.PNG)

4. 有关**连接参数**，选择 **...** 按钮，并**登录**到 Azure 帐户。  

    **Application insights**  
    选择你**订阅**，**资源组**，和 Application Insights 实例。

    ![启用针对你的环境分析](../core/media/analytics-group-application-insights.png)

    **事件中心**  
    选择你**订阅**，**资源组**，事件中心命名空间和事件中心。 对于身份验证，可以在命名空间级别或事件中心级别处的实体签名中使用的访问签名 (SAS)。 可用键内以前配置的值会自动填充[Azure](https://portal.azure.com)。

    ![启用针对你的环境分析](../core/media/send-tracking-data-to-azure.png)

5. 选择**确定**以保存所做的更改。 

启用后，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]已准备好将数据传输到 Azure 资源。 接下来，启用端口和业务流程上的分析。 

## <a name="enable-analytics-on-your-artifacts"></a>分析你的项目

1. 在 BizTalk Server 管理，右键单击**接收端口**，**发送端口**或**业务流程**，然后选择**跟踪**。
2. 下**Analytics**，检查**启用分析**，如下所示。 此设置启动跟踪和传输从项目到 Azure 资源的数据。
    
    ![业务流程的跟踪数据](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. 选择**确定**以保存所做的更改。
4. 重新启动跟踪主机实例，并确认 BizTalk 应用程序已启动。

> [!TIP]
> 与其他系统，若要了解更多的组织数据连接在 BizTalk Server 的分析。

## <a name="view-your-data"></a>查看你的数据

#### <a name="use-application-insights"></a>使用 Application Insights
一旦将数据发送到 Application Insights，可以使用在 Azure 中的分析工具来创建高级的查询和分析你的数据。

1. 登录到[Azure 门户](https://portal.azure.com)。
2. 打开 Application Insights 资源，并选择**指标资源管理器**。
3. 空图表可能会显示。 在图表中，选择**编辑**。 下**指标**，选择**自定义**若要查看可用的跟踪的属性。 选择一些不同的选项，在图表上看到所做的更改： 

    ![Azure Analytics](../core/media/azure-stream-metrics-custom.png)

4. 返回到 Application Insights 资源，并选择**Analytics**。 在中**使用情况**，选择**运行**。 执行示例查询，并在图表中显示结果。  

> [!TIP]
> Azure Application Insights 是一个强大的工具。 资源可帮助你在 Application Insights 在编写查询[Application Insights 中的 Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)，甚至可以开始在[什么是 Application Insights？](https://docs.microsoft.com/azure/application-insights/app-insights-overview)。

#### <a name="use-event-hubs"></a>使用事件中心
后的数据发送到事件中心，有两种方法查看的数据。 事件中心使用的用户数量事件中心捕获将流式处理数据加载到 Azure。 其目的是为您专注于数据处理，而不是数据捕获。 [事件中心捕获](https://docs.microsoft.com/azure/event-hubs/event-hubs-capture-overview)介绍它的工作原理，以及如何将其设置。

另一种方法是创建一个接收端口和接收位置使用事件中心适配器。 然后，您可以将数据输出到一个文件夹。 这一想法可能是最佳方案，如果你想要测试的方案。 [事件中心适配器](event-hubs-adapter.md)列出了消息接收到来自事件中心的 BizTalk Server 的步骤。

## <a name="where-the-data-is-stored"></a>存储数据

跟踪数据的显示应很快 （几分钟内） 对 Azure 资源内。 如果没有，则可能有跟踪主机的问题。 SQL Server 中的分析数据存储在 BizTalkMsgBoxDb 数据库中，在 TrackingData_2_*x*表。 在 SQL Server Management Studio，在以下四个表返回前 1000年行。 如果数据存在时，跟踪主机不到 BizTalkDTADb 数据库移动数据。 

一些可能的解决方法：

1. 重新启动跟踪主机。
2. 创建专用的跟踪主机。 安装 BizTalk Server 时，可能会在启用跟踪**BizTalk Server 应用程序 1**主机。 通常情况下，此应用程序还用于处理消息。 创建专用的跟踪主机使用以下步骤： 

    1. BizTalk Server 管理中打开 BizTalk Server 应用程序 1 主机的属性，并取消选中**允许主机跟踪**。 重新启动此主机实例。

    2. 创建一个名为的新主机**跟踪**，并检查**允许主机跟踪**。 创建主机实例，并启动它。

现在，再次查询 BizTalkMsgBoxDb TrackingData_2_x 表。 如果表为空，将数据移动，并且应开始显示在 Application Insights 中。
    
## <a name="see-also"></a>另请参阅
 [安装并配置功能包](../core/configure-the-feature-pack.md)