---
title: 如何配置 Windows SharePoint Services 发送处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], send handlers
- send handlers, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, send handlers
ms.assetid: 457767d9-6e39-4553-9bbe-212fcb7c04bc
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8e110fb2a671fc839fb96cfdc2ad03169649e6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969131"
---
# <a name="how-to-configure-a-windows-sharepoint-services-send-handler"></a>如何配置 Windows SharePoint Services 发送处理程序
使用以下步骤可更改与 Windows SharePoint Services 发送处理程序关联的主机。  
  
> [!NOTE]
>  每个主机只能有一个关联的发送处理程序。  
  
### <a name="to-change-global-variables-for-a-windows-sharepoint-services-send-handler"></a>更改 Windows SharePoint Services 发送处理程序的全局变量  
  
1.  在 BizTalk Server 管理控制台中，单击以展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，然后单击以展开**BizTalk 组 [\<servername\>:\<管理数据库\>]**，单击以展开**平台设置**，然后单击以展开**适配器**。 此时，适配器列表将显示在该文件夹下。  
  
2.  单击**Windows SharePoint Services**，然后在右窗格中，右键单击你想要配置，，然后单击发送处理程序**属性**。  
  
3.  在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择发送处理程序将与之关联的主机。  
  
4.  上**常规**选项卡上，单击**属性**。  
  
5.  在**Windows SharePoint Services 传输属性**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |发送批大小|Windows SharePoint Services Web Services 将按一批进行处理的最大文档数。 默认值为 20。 **注意：** 的最小值为 1。|  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 Windows SharePoint Services 接收位置](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [如何配置 Windows SharePoint Services 发送端口](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)   
 [支持的 Windows SharePoint Services 栏类型](../core/supported-windows-sharepoint-services-column-types.md)