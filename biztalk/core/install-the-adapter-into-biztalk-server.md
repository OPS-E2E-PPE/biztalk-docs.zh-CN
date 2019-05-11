---
title: 将适配器安装到 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1164468d-75a9-4116-87a6-6055948c198b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8d6093776f0359e79731a3ba273e319e7cd3765
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332013"
---
# <a name="install-the-adapter-into-biztalk-server"></a>将适配器安装到 BizTalk Server
适当后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]条目已写入的注册表必须将适配器添加到 BizTalk 管理数据库。 将适配器添加到此数据库后它是当前可配置的适配器，并已正确配置的情况下可以处理的消息。 通过使用的适配器安装到数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在安装后，适配器在数据库中，重新启动主机实例。  

> [!NOTE]
>  要看到中添加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，适配器必须在 HKLM 注册表中正确注册并且必须实现必要的适配器接口。  

### <a name="to-install-the-static-sample-adapter"></a>若要安装示例静态适配器  

1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，双击**BizTalk 组**节点。  

3. 展开**平台设置**，然后选择**适配器**。  

4. 右键单击**适配器**，单击**新建**，然后单击**适配器**。  

5. 在中**适配器属性**对话框框中，执行以下操作。  


   |  使用此选项   |                      执行的操作                       |
   |-------------|-------------------------------------------------------|
   |    “属性”     |                   类型**静态**。                    |
   |   适配器   | 选择**Static DotNetFile**从下拉列表。 |
   | Description |            类型**示例静态适配器**。            |


6. 单击“确定” 。  

    静态适配器现在显示在右侧窗口中的适配器列表[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

### <a name="to-stop-and-restart-the-host-instance"></a>若要停止并重新启动主机实例  

1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，双击**BizTalk 组**节点。  

3. 展开**平台设置**，选择**主机**，然后选择**BizTalkServerApplication**在结果窗格中。  

4. 右键单击主机实例 （通常情况下，计算机名称），然后依次**停止**。  

    主机实例的状态将变为**已停止**。  

5. 在结果窗格中，右键单击该主机实例，然后依次**启动**。  

    主机实例的状态将变为**启动挂起**。 您必须单击**刷新**，或右键单击主机实例，然后单击**刷新**，以将状态更改为**运行**。