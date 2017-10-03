---
title: "将跟踪数据发送到 Azure Application Insights 使用 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: f587c3049e191505c87ba456b5ddfd41011862c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="send-tracking-data-to-azure-application-insights-using-biztalk-server"></a>将跟踪数据发送到 Azure Application Insights 使用 BizTalk Server
发送[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]到 Azure 应用程序 Inisights 跟踪数据。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，您可以过程，并将跟踪数据发送到 Azure Application Insights。 使用 Application Insights 功能来接收端口、 发送端口和业务流程从跟踪您的实例。

## <a name="prerequisites"></a>先决条件
* 创建的新实例[Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)
* 安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

## <a name="enable-analytics-for-your-environment"></a>启用针对你的环境分析

1. 打开**BizTalk Server 管理**控制台中，展开**BizTalk 管理**，右键单击**BizTalk 组**，然后选择**设置**. 
2. 检查**启用组级别分析**。
3. 有关**目标类型**，选择**Application Insight**从列表中。
4. 有关**连接参数**，输入你的 Application Insights **[检测密钥](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)** （在 Azure 门户中可用）。

    你的组设置类似于以下内容： 

    ![启用针对你的环境分析](../core/media/environmentsettingapplicationinishgt.PNG)

5. 单击“确定”保存更改。 

在启用之后，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]已准备好将数据传输到 Application Insights。 接下来，启用在端口和业务流程的分析。 

## <a name="enable-analytics-on-your-artifacts"></a>启用你的项目上的分析

1. 在 BizTalk Server 管理中，右键单击**接收端口**，**发送端口**或**orchestration**，然后选择**跟踪**。
2. 下**分析**，检查**启用分析**。 此设置将开始跟踪和传输到 Application Insights 从项目的数据。

    你的项目设置类似于以下内容： 
    
    ![业务流程的跟踪数据](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. 单击“确定”保存更改。

接下来，运行以查看你的数据的 Application Insights 中的查询。  

> [!TIP]
> 连接你的 BizTalk Server 分析与其他系统，若要了解更多的组织数据。

## <a name="run-queries-on-your-data"></a>对数据运行查询
后的数据发送到 Application Insights，可以使用在 Azure 中的分析工具来创建高级的查询，并分析你的数据。

1. 登录到[Azure 门户](https://portal.azure.com)。
2. 打开 Application Insights 资源，并选择**分析**。
3. 选择**用法**，并运行查询提供。

    > [!TIP]
    > 了解有关如何在 Application Insights 在编写查询[Application Insights 中的分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)。
    
## <a name="see-also"></a>另请参阅
 [配置功能包](../core/configure-the-feature-pack.md)