---
title: 如何为发送端口配置备份传输选项 |Microsoft Docs
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
ms.openlocfilehash: 2ee35e6eb408ab8749e12a7747643783cabc3019
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341694"
---
# <a name="how-to-configure-backup-transport-options-for-a-send-port"></a>如何为发送端口配置备份传输选项
本主题介绍如何使用 BizTalk Server 管理控制台为发送端口配置备份传输选项。 您指定的备份传输事件的主传输无法正常中生效。 中所述配置主传输[如何创建发送端口](../core/how-to-create-a-send-port2.md)。  
  
> [!NOTE]
>  对于动态端口，没有属性可用于配置，因为在运行时自动确定传输选项。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-specify-transport-options-for-a-send-port"></a>若要指定发送端口的传输选项  
  
1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要为发送端口配置备份传输选项。  
  
3. 展开**发送端口**，右键单击发送端口配置，请单击**属性**，然后单击**备份传输**。  
  
4. 下表中所述配置备份传输属性，然后单击**确定**。  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**类型**|从下拉列表中，选择适当的备份传输类型或传输协议。 如果端口是要求响应端口，仅支持要求-响应的传输类型是出现在列表中。|  
   |**配置**|选择备份传输类型后，单击**配置**，然后配置传输属性。 有关配置属性的详细信息，请单击**帮助**。|  
   |**发送处理程序**|从下拉列表中，选择在其运行发送适配器的主机实例。|  
   |**重试次数**|指定的发送端口以重新发送消息失败的消息的次数。 默认值为 3;允许的范围是从 0 到 1000。|  
   |**重试间隔**|指定以分钟为单位次重发消息尝试之间的间隔。 默认值为 5;允许的范围是从 0 到 525600。|  
  
## <a name="see-also"></a>请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)