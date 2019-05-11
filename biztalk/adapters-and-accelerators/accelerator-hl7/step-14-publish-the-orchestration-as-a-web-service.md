---
title: 步骤 14:业务流程发布为 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- publishing, orchestrations
- Web services, orchestrations
- message enrichment tutorial, orchestrations
- publishing, Web services
- message enrichment tutorial, Web services
ms.assetid: 8f29a7be-a679-4ca6-a648-35338d9e9e98
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f168acb351dc1546b304a5c0f8226b00aab9b213
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288866"
---
# <a name="step-14-publish-the-orchestration-as-a-web-service"></a>步骤 14:业务流程发布为 Web 服务
在此步骤中，使用 BizTalk Web Services 发布向导发布您的业务流程作为 Web 服务。  
  
 在发布之前该业务流程作为 Web 服务，你需要确保 BizTalkServerIsolatedHost 的登录帐户是 BizTalk Isolated Host Users 组的一部分，因此它有权访问 BizTalk 数据库。 这是必要的因为本教程创建的 Web 服务发布向导的 SOAPReceivePort 接收位置的接收处理程序为 BizTalkServerIsolatedHost，不是 BizTalkServerApplication。 接收处理程序是 BizTalkServerIsolatedHost 因为 SOAP 适配器在 IIS 进程，不是 BizTalk 进程下运行。  
  
### <a name="to-ensure-access-privileges-for-the-soapreceiveport-receive-location"></a>若要确保访问特权的 SOAPReceivePort 接收位置  
  
1.  在 BizTalk Server 管理控制台中下**主机实例**中**平台设置**节点，右键单击**BizTalkServerIsolatedHost**，然后单击**属性**。 在属性对话框中，单击**配置**。 请注意**登录**帐户。  
  
2.  在计算机管理对话框中下,**组**中**本地用户和组**节点中，双击**BizTalk Isolated Host Users**。 如果的登录帐户的**BizTalkServerIsolatedHost**不是的成员**BizTalkServerIsolatedHost**，将其添加到组。  
  
### <a name="to-run-the-biztalk-web-services-publishing-wizard"></a>若要运行 BizTalk Web Services 发布向导  
  
1. 在解决方案资源管理器的 Visual Studio 中，单击**解决方案 BTAHL7V22Common**。 上**工具**菜单上，单击**BizTalk Web Services 发布向导**。  
  
2. 在中**BizTalk Web Services 发布向导**，然后在**欢迎**页上，单击**下一步**。  
  
3. 上**创建 Web 服务**页上，选择**BizTalk 业务流程发布为 web services**，然后单击**下一步**。  
  
4. 上**BizTalk 程序集**页上，在**BizTalk 程序集文件 (\*.dll)** 字段中，浏览到或键入 **\<*驱动器*\>: \Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**，单击**BTAHL7 Project.dll**，单击**打开**，然后单击**下一步**.  
  
5. 上**业务流程和端口**页上，确保所有节点已选中，然后单击**下一步**。  
  
6. 上**Web 服务属性**页上，对于**web 服务的目标命名空间**，类型**http://localhost**，然后单击**下一步**。  
  
7. 上**Web 服务项目**页上，选择**允许匿名访问 web 服务**并**创建 BizTalk 接收位置在以下应用程序中**。 选择**BizTalk Application 1**应用程序。 保留默认值**位置**字段。 单击**下一步**以接受默认项目位置。  
  
8. 上**Web Services 项目摘要**页上，单击**创建**生成 ASP.NET Web 服务项目。  
  
9. 单击 **“完成”** 关闭向导。  
  
10. 打开 BizTalk Server 管理控制台。 在控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk Application 1**.  
  
11. 单击**接收位置**，右键单击**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**，然后单击**属性**.  
  
12. 在接收位置属性对话框中，单击**接收管道**，选择**Microsoft.BizTalk.DefaultPipelines.XMLReceive**从下拉列表中，然后单击**确定**.  
  
13. 右键单击**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**，然后单击**启用**。  
  
    请继续执行[步骤 15:配置发送和接收端口](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)。  
  
## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)