---
title: "步骤 13： 创建并配置端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, creating
- message enrichment tutorial, ports
- creating, ports
- configuring, ports
- ports, configuring
ms.assetid: cc0540d7-46fc-4d9f-bcf3-0b0e0179fd51
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 256b1618313605f0847d9328abfd003f41ac61cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-13-create-and-configure-ports"></a>步骤 13： 创建并配置端口
在此步骤中，你可以使用端口配置向导以创建和业务流程设计器中配置端口。 端口指定您的业务流程发送和接收消息与其他业务流程的方式。 每个端口都具有类型、 方向和绑定。 属性共同决定通信、 通信模式、 位置到或从其方向[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]发送或接收的消息和如何进行通信。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用作为发送端口的最小值较低层协议 (MLLP) 适配器。 MLLP 适配器将接口与其他应用程序，如实验室应用程序、 保险应用程序和旧的业务线应用程序中使用 TCP 套接字通信。 MLLP 发送适配器表示[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]适配器：  
  
-   自定义。 适配器仅附带[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]，而不是与传送[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]。  
  
-   协议/传输。 适配器不是应用程序或数据适配器。  
  
-   静态。 适配器配置不涉及自定义用户界面。  
  
-   异步。 适配器不会阻止消息引擎线程，从而使所有适配器的提高的性能，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主机。  
  
-   Nontransacted。 适配器不是事务处理的接收或发送[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]适配器。  
  
-   正则。 适配器不在单独的应用程序的进程中运行。  
  
-   同时单向和双向。 适配器支持交互的单向和请求-响应/请求-响应的模式。  
  
 MLLP 适配器可以提交单个消息，或提交批处理中的消息。 MLLP 消息的开头标记使用包装的字符，十六进制 0x0b （也称为启动块或 SB 字符），并且消息的末尾是通过十六进制 0x1c 字符 （也称为结束块或 EB 字符） 的组合紧接着是 0x0d 字符 （回车）。 BTAHL7 性能计数器仅统计发送消息的这些包装器字符。 在接收消息时，BTAHL7 性能计数器进行计数这些包装器字符。  
  
> [!NOTE]
>  标准的 MLLP 协议不消息有效负载中允许下 0x20 字符，因为它干扰检测 SB 和 EB 字符的能力。 你可以配置 SB 和 EB 的字符值，因此应谨慎此问题时进行更改。  
  
 在此步骤中，你可以配置 MLLP 适配器和 SOAP 适配器。  
  
### <a name="to-create-and-configure-the-ports"></a>创建并配置端口  
  
1.  业务流程的设计器中拖动**端口**从工具箱调整到的设计视图图面，左侧端口面和删除形状，以便与水平对齐**DoorbellReceive**形状。  
  
2.  在**端口配置向导**，单击**下一步**。  
  
3.  上**端口属性**页上，在**名称**字段中，键入**SOAPReceivePort**，然后单击**下一步**。  
  
4.  上**选择端口类型**页上，输入以下信息，，然后单击**下一步**以继续。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**端口类型名称**|类型**SOAPReceivePortType**。|  
    |**通信模式**|选择**单向**。|  
    |**访问限制**|选择**公有-无限制**。|  
  
5.  上**端口绑定**页上，单击**下一步**以接受默认值。  
  
6.  上**完成端口向导**页上，单击**完成**。  
  
7.  拖动**端口**从工具箱调整到的设计视图图面，右侧端口面和删除形状，以便与水平对齐**DoorbellSend**形状。  
  
8.  使用**端口配置向导**按步骤 2 至 7 中，创建使用以下参数的其他发送端口：  
  
    |属性|参数|  
    |--------------|---------------|  
    |**端口属性名称**|MLLPSendPort|  
    |**端口类型名称**|MLLPSendPortType|  
    |**通信模式**|单向|  
    |**访问限制**|公有 - 无限制|  
    |**端口绑定**|以后指定|  
    |**端口通信方向**|始终在此端口上发送消息。|  
  
9. 在**业务流程视图**窗口中，与**类型**，**端口类型**，和**SOAPReceivePortType**节点已展开，展开**Operation_1**，然后单击**请求**。  
  
10. 在**属性**窗口中的下拉列表**消息类型**，展开**架构**，然后单击**BTAHL7_Project.Doorbell**.  
  
11. 在**业务流程视图**窗口中，展开**MLLPSendPortType**，展开**Operation_1**，然后单击**请求**。  
  
12. 在**属性**窗口中的下拉列表**消息类型**，展开**多部分消息类型**，然后单击**BTAHL7_Project.DoorbellFinalMessageType**。  
  
13. 在**名称**字段中，键入**响应**，然后按**Enter**。  
  
14. 在业务流程设计视图图面中，单击**DoorbellReceive**操作形状。  
  
15. 在**属性**窗口中的下拉列表**消息**，选择**DoorbellInputMessage**。  
  
16. 在业务流程设计视图图面中，单击**DoorbellSend**形状。  
  
17. 在**属性**窗口中的下拉列表**消息**，选择**DoorbellFinalMessage**。  
  
18. 单击绿色的句柄以**SOAPReceivePort**并将其拖到绿色句柄**DoorbellReceive**接收形状连接**SOAPReceivePort**到**DoorbellReceive**接收形状。  
  
19. 单击绿色的句柄以**DoorbellSend**形状并将其拖到绿色句柄**MLLPSendPort**端口以连接**DoorbellSend**将形状发送到**MLLPSendPort**端口。  
  
20. 单击**解决方案资源管理器**Orchestration 视图下的选项卡。  
  
21. 在解决方案资源管理器，右键单击**BTAHL7V22Common**，然后单击**生成**。 确保在输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果不显示任何成功消息，对解决方案进行故障排除。  
  
22. 右键单击**BTAHL7 项目**，然后单击**部署**部署 BTAHL7 项目。  
  
 继续执行[步骤 14： 发布作为 Web 服务业务流程](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息扩充教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)