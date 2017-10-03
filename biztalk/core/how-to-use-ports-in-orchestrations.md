---
title: "如何在业务流程中使用端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3edef29376d8724d93192040ee88951ced245ac3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-ports-in-orchestrations"></a>如何使用在业务流程中的端口
向业务流程添加端口的方式与向 Web 窗体或 Windows 窗体添加控件的方式相同。 还可以使用“业务流程视图”窗口来添加端口。  
  
### <a name="to-add-a-new-port"></a>添加新端口  
  
-   右键单击**端口图面**或**角色链接**，然后单击**新端口**。  
  
     -或者-  
  
     在业务流程视图窗口中，右键单击**端口**，然后单击**新端口**。  
  
     此时未完全配置的端口上将显示设计提示。  
  
    > [!TIP]
    >  您还可以拖动到端口**角色链接**。  
  
### <a name="to-add-and-configure-a-new-port"></a>添加和配置新端口  
  
1.  从**BizTalk 业务流程**选项卡的工具箱拖**端口**形状拖到**端口图面**或**角色链接**。  
  
     -或者-  
  
     右键单击**端口图面**或**角色链接**，然后单击**新配置端口**。  
  
     -或者-  
  
     在业务流程视图窗口中，右键单击**端口**，然后单击**新配置端口**。  
  
     此时将出现端口配置向导。  
  
2.  按照该向导中的步骤进行端口配置。 有关详细信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。  
  
### <a name="to-remove-a-port"></a>删除端口  
  
-   右键单击要删除，，然后单击的端口**删除**。  
  
    > [!NOTE]
    >  如果你已连接到后删除端口**发送**或**接收**形状中业务流程已编译形状上的端口操作不会被删除，并将收到错误时您尝试编译。 应将该形状连接到其他端口并重新配置端口操作。  
  
### <a name="to-configure-a-port-by-using-the-port-configuration-wizard"></a>使用端口配置向导配置端口  
  
1.  右键单击要配置，，然后单击的端口**配置端口**。  
  
2.  按照端口配置向导中的步骤进行端口配置。 有关详细信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。  
  
### <a name="to-configure-a-port-manually-by-using-the-properties-window"></a>使用“属性”窗口手动配置端口  
  
1.  选择要配置的端口。  
  
2.  在“属性”窗口中，指定以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |端口类型|确定与端口相关的通信模式、操作和多部分消息类型。|  
    |通信方向|确定此业务流程是通信的发送方还是接收方。|  
    |通信模式|确定此端口是用于请求-响应还是单向通信。 (此属性由**端口类型**属性是只读的和。)|  
    |Binding|确定消息如何到达目的地：<br /><br /> 直接-与另一个业务流程进行通信。<br /><br /> 动态-在运行时确定的终结点进行通信。<br /><br /> 指定更高版本-由管理员在配置时的终结点进行通信。<br /><br /> 立即指定 — 通过设计时就已知的终结点传递通信。|  
    |Identifier|此端口在业务流程中的名称。|  
    |按序送达|对于接收端口，请确保将按给定顺序发布到 MessageBox 数据库的消息仍依照其发布顺序送往每个匹配的订户。 有关详细信息，请参阅[有序的消息的传递](../core/ordered-delivery-of-messages.md)。|  
    |传递通知|对于发送端口，确定是否要在消息成功发送后接收确认。 有关详细信息，请参阅"传递通知"[如何配置发送形状](../core/how-to-configure-the-send-shape.md)。|  
  
3.  剩余的属性，以指定由**绑定**属性：  
  
    -   直接绑定-与另一个业务流程直接通信时使用。  
  
        |属性|Description|  
        |--------------|-----------------|  
        |合作伙伴业务流程端口|确定合作伙伴业务流程直接绑定到的端口。|  
  
    -   动态绑定-在运行时确定的终结点通信时使用。  
  
        |属性|Description|  
        |--------------|-----------------|  
        |接收管道|确定传入消息使用的管道。|  
        |发送管道|确定传出消息使用的管道。|  
  
    -   指定更高版本-与由管理员配置的终结点通信时使用。  
  
    -   现在指定 — 在设计时已知的终结点通信时使用。  
  
        |属性|Description|  
        |--------------|-----------------|  
        |接收管道|确定传入消息使用的管道。|  
        |发送管道|确定传出消息使用的管道。|  
        |Transport|确定发送消息使用的传输。|  
        |URI|确定消息的送达目的地。|  
  
### <a name="to-add-a-port-operation"></a>添加端口操作  
  
-   右键单击你想要添加某一操作，，然后单击的端口**新操作**。  
  
### <a name="to-remove-a-port-operation"></a>删除端口操作  
  
-   右键单击要删除，，然后单击的端口操作**删除**。