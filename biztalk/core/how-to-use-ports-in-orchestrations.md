---
title: 如何在业务流程中使用端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, adding ports
- Port Configuration Wizard [Orchestration Designer], configuring ports
- ports, operations
- operations, adding to ports
- configuring, ports
- ports, deleting
- deleting, ports
- ports, Port Configuration Wizard [Orchestration Designer]
- ports, adding to orchestrations
- ports, configuring
ms.assetid: da8665cd-ccde-4949-b5f5-01f9f8be5ce8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c076195aa9893dc4bb1c42a9b6a659422e3ec263
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333274"
---
# <a name="how-to-use-ports-in-orchestrations"></a>如何使用业务流程中的端口
你将端口添加到业务流程相同的方式向 Web 窗体或 Windows 窗体添加控件。 此外可以通过使用业务流程视图窗口来添加端口。  
  
### <a name="to-add-a-new-port"></a>若要添加新的端口  
  
-   右键单击**端口图面**或**角色链接**，然后单击**新建端口**。  
  
     -或-  
  
     在业务流程视图窗口中，右键单击**端口**，然后单击**新端口**。  
  
     此时将显示尚未完全配置的端口上。  
  
    > [!TIP]
    >  您还可以拖动到的端口**角色链接**。  
  
### <a name="to-add-and-configure-a-new-port"></a>若要添加和配置新端口  
  
1.  从**BizTalk 业务流程**选项卡的工具箱拖动**端口**形状拖至**端口图面**或者**角色链接**。  
  
     -或-  
  
     右键单击**端口图面**或**角色链接**，然后单击**新建配置的端口**。  
  
     -或-  
  
     在业务流程视图窗口中，右键单击**端口**，然后单击**新建配置的端口**。  
  
     端口配置向导将显示。  
  
2.  按照向导可配置的端口中的步骤。 有关详细信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。  
  
### <a name="to-remove-a-port"></a>若要删除端口  
  
-   右键单击要删除，然后单击端口**删除**。  
  
    > [!NOTE]
    >  已连接到后删除端口**发送**或**接收**编译之后，业务流程形状上的端口操作形状中将不会删除，并且你将收到错误时您尝试编译。 将该形状连接到另一个端口并重新配置的端口操作。  
  
### <a name="to-configure-a-port-by-using-the-port-configuration-wizard"></a>若要使用端口配置向导配置端口  
  
1.  右键单击要配置，然后单击端口**配置端口**。  
  
2.  按照端口配置向导，可配置的端口中的步骤。 有关详细信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。  
  
### <a name="to-configure-a-port-manually-by-using-the-properties-window"></a>若要通过使用属性窗口手动配置端口  
  
1.  选择要配置的端口。  
  
2.  在属性窗口中，指定以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |端口类型|确定通信模式、 操作和多部分消息类型与端口相关联。|  
    |通信方向|确定此业务流程为发送方或接收方为此通信。|  
    |通信模式|确定此端口用于请求-响应还是单向通信。 (此属性由**端口类型**属性是只读的。)|  
    |Binding|确定消息如何到达其目标：<br /><br /> 直接 — 与其他业务流程是通信。<br /><br /> 动态 — 通信是在运行时确定的终结点。<br /><br /> 以后指定 — 通信是由管理员在配置时的终结点。<br /><br /> 立即指定 — 通信是在设计时已知的终结点。|  
    |Identifier|此端口在业务流程中使用的名称。|  
    |按序的送达|对于接收端口，可确保发布到 MessageBox 数据库中给定订单的消息将传送到按相同顺序发布到消息框中的每个匹配的订户。 有关详细信息，请参阅[的消息按序送达](../core/ordered-delivery-of-messages.md)。|  
    |送达通知|对于发送端口，确定是否想要接收确认已成功发送消息。 详细信息，请参阅"送达通知"中[如何配置发送形状](../core/how-to-configure-the-send-shape.md)。|  
  
3.  剩余的属性来指定由**绑定**属性：  
  
    -   直接绑定 — 与另一个业务流程直接通信时使用。  
  
        |属性|Description|  
        |--------------|-----------------|  
        |合作伙伴业务流程端口|确定哪一个端口到合作伙伴业务流程直接绑定。|  
  
    -   动态绑定 — 在运行时确定的终结点进行通信时使用。  
  
        |属性|Description|  
        |--------------|-----------------|  
        |接收管道|确定使用传入消息的管道。|  
        |发送管道|确定管道用于传出消息。|  
  
    -   以后指定 — 由管理员配置的终结点进行通信时使用。  
  
    -   立即指定 — 在设计时已知的终结点进行通信时使用。  
  
        |属性|Description|  
        |--------------|-----------------|  
        |接收管道|确定使用传入消息的管道。|  
        |发送管道|确定管道用于传出消息。|  
        |Transport|确定要用于发送消息的传输。|  
        |URI|确定将消息发送到何处。|  
  
### <a name="to-add-a-port-operation"></a>若要添加端口操作  
  
-   右键单击你想要添加一个操作，然后单击的端口**新的操作**。  
  
### <a name="to-remove-a-port-operation"></a>若要删除端口操作  
  
-   右键单击端口操作以删除，然后单击**删除**。