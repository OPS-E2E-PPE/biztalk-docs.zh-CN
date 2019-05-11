---
title: 步骤 13:创建和配置端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, creating
- message enrichment tutorial, ports
- creating, ports
- configuring, ports
- ports, configuring
ms.assetid: cc0540d7-46fc-4d9f-bcf3-0b0e0179fd51
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09113f9fb108c79630597c5e930e13651e679944
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288944"
---
# <a name="step-13-create-and-configure-ports"></a>步骤 13:创建和配置端口
在此步骤中，使用端口配置向导来创建和业务流程设计器中配置的端口。 端口指定您的业务流程发送和接收消息与业务流程的方式。 每个端口都具有一个类型、 方向和绑定。 属性共同确定通信、 通信模式、 位置或从其方向[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]发送或接收的消息和进行通信的方式的位置。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 为发送端口使用的最小值较低层协议 (MLLP) 适配器。 MLLP 适配器到接口与其他应用程序，如实验室应用程序、 保险应用程序和旧业务线应用程序使用 TCP 套接字通信。 MLLP 发送适配器表示[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]适配器：  

- 自定义。 仅附带了适配器[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]，而不是与 BizTalk Server 的传送。  

- 协议/传输。 适配器不是一个应用程序或数据适配器。  

- 静态。 适配器配置不涉及自定义用户界面。  

- 异步。 适配器不会阻止消息引擎线程，从而使所有适配器的提高的性能的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主机。  

- 非事务。 适配器不是事务处理的接收或发送[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]适配器。  

- 正则。 适配器不在单独的应用程序的进程中运行。  

- 单向和双向。 该适配器支持交互单向和请求-响应/要求-响应的模式。  

  MLLP 适配器可以将单个消息提交或提交一批中的消息。 MLLP 消息的开始标记包装字符十六进制 0x0b （也称为开始块或 SB 字符），并且消息的结尾标记为十六进制 0x1c 字符 （也称为结束块或 EB 字符） 的组合紧接着是 0x0d 字符 （回车符）。 BTAHL7 性能计数器只计发送消息的这些包装器字符。 在接收消息时，BTAHL7 性能计数器进行计数这些包装器字符。  

> [!NOTE]
>  MLLP 协议标准不消息负载中允许字符下 0x20，因为它会影响检测 SB 和 EB 字符的能力。 可以配置 SB 和 EB 的字符值，因此请慎重考虑此问题时进行更改。  

 在此步骤中，您可以配置的 MLLP 适配器和 SOAP 适配器。  

### <a name="to-create-and-configure-the-ports"></a>若要创建和配置的端口  

1. 在业务流程设计器中拖动**端口**形状从工具箱拖到设计视图图面上，左侧端口图面并将该形状放以便与水平对齐**DoorbellReceive**形状。  

2. 在中**端口配置向导**，单击**下一步**。  

3. 上**端口属性**页上，在**名称**字段中，键入**SOAPReceivePort**，然后单击**下一步**。  

4. 上**选择端口类型**页上，输入以下信息，然后单击**下一步**以继续。  


   |         使用此选项          |          执行的操作           |
   |---------------------------|-------------------------------|
   |    **端口类型名称**     | 类型**SOAPReceivePortType**。 |
   | **通信模式** |      选择**单向**。      |
   |  **访问限制**  | 选择**公有-无限制**。 |


5. 上**端口绑定**页上，单击**下一步**以接受默认值。  

6. 上**完成端口向导**页上，单击**完成**。  

7. 拖动**端口**形状从工具箱拖到设计视图图面，右侧端口图面并将该形状放以便与水平对齐**DoorbellSend**形状。  

8. 使用**端口配置向导**与你在步骤 2 到 7 中，创建一个附加的发送端口使用以下参数：  


   |              属性               |                   参数                   |
   |-------------------------------------|-----------------------------------------------|
   |      **端口属性名称**       |                 MLLPSendPort                  |
   |         **端口类型名称**          |               MLLPSendPortType                |
   |      **通信模式**      |                    单向                    |
   |       **访问限制**       |               公有-无限制               |
   |          **端口绑定**           |                 以后指定                 |
   | **端口通信方向** | 我始终在发送消息此端口上。 |


9. 在中**业务流程视图**窗口中，使用**类型**，**端口类型**，以及**SOAPReceivePortType**节点已展开，展开**Operation_1**，然后单击**请求**。  

10. 在中**属性**窗口中的下拉列表中**消息类型**，展开**架构**，然后单击**BTAHL7_Project.Doorbell**.  

11. 在中**业务流程视图**窗口中，展开**MLLPSendPortType**，展开**Operation_1**，然后单击**请求**。  

12. 在中**属性**窗口中的下拉列表中**消息类型**，展开**多部分消息类型**，然后单击**BTAHL7_Project.DoorbellFinalMessageType**。  

13. 在中**名称**字段中，键入**响应**，然后按**Enter**。  

14. 在业务流程设计视图图面上，单击**DoorbellReceive**操作形状。  

15. 在中**属性**窗口中的下拉列表中**消息**，选择**DoorbellInputMessage**。  

16. 在业务流程设计视图图面上，单击**DoorbellSend**形状。  

17. 在中**属性**窗口中的下拉列表中**消息**，选择**DoorbellFinalMessage**。  

18. 单击中的绿色手柄**SOAPReceivePort**将其拖动到的绿色手柄**DoorbellReceive**接收形状连接**SOAPReceivePort** 到**DoorbellReceive**接收形状。  

19. 单击中的绿色手柄**DoorbellSend**形状，然后将其拖到绿色手柄**MLLPSendPort**端口以连接**DoorbellSend**将形状置于**MLLPSendPort**端口。  

20. 单击**解决方案资源管理器**下业务流程视图选项卡。  

21. 在解决方案资源管理器中右键单击**BTAHL7V22Common**，然后单击**生成**。 确保在输出窗口中显示一条成功消息。  

    > [!NOTE]
    >  如果不显示任何成功消息，进行故障排除解决方案。  

22. 右键单击**BTAHL7 项目**，然后单击**部署**部署 BTAHL7 项目。  

    请继续执行[步骤 14:发布为 Web 服务的业务流程](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)。  

## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)