---
title: 如何配置发送端口的备份传输选项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- managing [send ports], configuring
- configuring, backing up [send ports]
- managing [send ports], backup options
- send ports, configuring
- send ports, backup options
ms.assetid: f05f57a6-e62b-4640-a6e2-cb73e9de2a14
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ff8b1354772290ce9e04742a6130a6f6f2df627
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248373"
---
# <a name="how-to-configure-backup-transport-options-for-a-send-port"></a>如何为发送端口配置备份传输选项
本主题将介绍如何使用 BizTalk Server 管理控制台为发送端口配置备份传输选项。 如果主传输无法正常工作，则您所指定的备份传输将生效。 中所述配置的主要传输[如何创建发送端口](../core/how-to-create-a-send-port2.md)。  
  
> [!NOTE]
>  对于动态端口，没有可进行配置的属性，因为其传输选项在运行时自动确定。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-specify-transport-options-for-a-send-port"></a>若要指定发送端口的传输选项  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其配置备份传输选项的发送端口所属的 BizTalk 组和 BizTalk 应用程序。  
  
3.  展开**发送端口**，右键单击发送端口配置，请单击**属性**，然后单击**备份传输**。  
  
4.  下表中所述配置备份传输属性，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类型**|从下拉列表中，选择适当的备份传输类型或传输协议。 如果端口是要求响应端口，则该列表中只显示支持要求响应的传输类型。|  
    |**配置**|选择备份传输类型后，单击**配置**，然后配置传输属性。 有关配置属性的详细信息，请单击**帮助**。|  
    |**发送处理程序**|从下拉列表中选择运行发送适配器的主机实例。|  
    |**重试计数**|指定在消息失败时发送端口重发消息的次数。 默认值为 3；允许的范围为 0 到 1,000。|  
    |**重试间隔**|指定两次重发消息尝试之间的时间间隔（以分钟为单位）。 默认值为 5;允许的范围从 0 为 525600。|  
  
## <a name="see-also"></a>另请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)