---
title: 如何配置接收和发送位置及端口用于 BAM WCF 侦听 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501194dc-427a-4910-88c9-19cf47daeaad
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9e74d8ef0f6d58b005cf5af873718c927c55dcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386204"
---
# <a name="how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception"></a>如何配置接收和发送位置及端口用于 BAM WCF 侦听
在此过程中配置接收和发送基于内容的路由 (CBR) 方案中的位置，以便直接演示关键概念。 此处演示的概念可以应用于业务流程公开为[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]服务。  

## <a name="prerequisites"></a>先决条件  
 此过程假定你具有：  

-   修改 machince.config 文件，如中所示[如何将 BAM 侦听器行为添加到 Machine.config 文件](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md)。  

-   创建 WCF 适配器的 BizTalk Server 中所示[如何创建用于 BizTalk Server 的 WCF 适配器](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md)。  

### <a name="to-configure-the-receive-and-send-locations"></a>若要配置接收和发送位置  

1. 打开 BizTalk 管理控制台。 若要执行此操作，请单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 展开控制台树以找到 BizTalk 应用程序的接收位置节点。 单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，单击**应用程序**，单击应用程序中所选[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务类型对话框的，然后单击**接收位置**。 将有新的接收位置对应于您创建一个。 它将处于禁用状态。  

3. 双击接收位置以打开**接收位置属性**对话框框中，，然后选择 Wcf-custom 作为传输类型。  

4. 单击**配置**按钮以打开**Wcf-custom 传输属性**对话框。  

5. 单击**绑定**选项卡并选择你想要使用的绑定。  

6. 单击**行为**选项卡上，右键单击**EndpointBehavior**节点，并选择**添加扩展**。  

7. 选择的 BAMEndPointExtension （这是添加到 machine.config 文件的扩展名），然后依次**确定**。  

    ![选择行为扩展屏幕](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")  

8. 选择刚创建的扩展，输入以下值，然后单击**确定**:  


   |      属性      |                                                        ReplTest1                                                         |
   |--------------------|----------------------------------------------------------------------------------------------------------------------|
   | PollingIntervalSec |                                                          10                                                          |
   |  ConnectionString  | ConnectionString:Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=BAMPrimaryImport;Data Source= |


9. 在中**接收位置属性**对话框中，选择**PassThruReceive**从**接收管道**下拉列表中，并单击**确定**.  

10. 启用接收位置并刷新管理控制台。 已启动的状态表示安装成功。  

## <a name="see-also"></a>请参阅  
 [配置 WCF 适配器以侦听 BAM 数据](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)