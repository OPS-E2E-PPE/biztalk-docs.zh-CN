---
title: 使用 BizTalk Server 项目中的 WCF LOB 适配器 SDK 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041f14cc-d00f-450d-b1e9-40a3e423c510
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0ad9b2659ce20876807d894f99751eeb265e92e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363829"
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-biztalk-server-project"></a>使用 BizTalk Server 项目中的 WCF LOB 适配器 SDK 适配器
本主题介绍如何使用使用构建适配器[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。  

> [!NOTE]
>  若要使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，则必须安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]工具在同一计算机承载[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  


## <a name="use-the-consume-adapter-service-add-in"></a>使用使用适配器服务外接程序  


1. 打开.NET 应用程序中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  

2. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，请在**项目**窗格中，右键单击你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目，，然后选择**添加**&#124;**添加生成的项** &#124; **使用适配器服务**。  

3. 在[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]屏幕上，选择一个适配器的绑定。  

4. 单击**配置**，配置所选的适配器绑定的连接 URI，它提供任何凭据、 URI 属性和绑定属性。 实际要求将因所选的适配器绑定。  

5. 单击**确定**配置 URI 时。  

6. 单击 **“连接”**。 如果连接 URI 有效并且接受客户端凭据 （如果有），**类别**窗格应填充的类别和适配器提供的操作。  

7. 如果适配器支持搜索，搜索字段将处于活动状态。 否则为可以按协定类型进行筛选，并通过单击中的节点浏览类型和操作**类别**窗格。  

8. 单击**确定**生成代理项目。 根据协定类型的项目数而有所不同：  


   | 协定类型 |  项目   |                         Description                         |                                                             |
   |---------------|-------------|-------------------------------------------------------------|-------------------------------------------------------------|
   |   出站    | XML 架构 | 包含所选的类型和操作的架构。 |                                                             |
   |   出站    |             |        WCF 自定义发送端口的绑定信息 XML         |  包含 XML 配置 Wcf-custom 发送端口。   |
   |    入站    | XML 架构 | 包含所选的类型和操作的架构。 |                                                             |
   |    入站    |             |       WCF 自定义接收端口的绑定信息 XML       | 包含配置 XML 为 WCF 自定义接收端口。 |


9. 现在可以使用中的 XML 架构文件在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序。  

## <a name="deploy-the-biztalk-server-project"></a>部署 BizTalk Server 项目  

1. 打开 **“BizTalk Server 管理”**。  

2. 导入要创建物理端口的端口绑定 XML 文件。 右键单击受测应用程序**应用程序**组中，选择**导入绑定**，然后导航到并选择适当的端口绑定信息 XML 文件。  

3. 映射中定义的逻辑端口在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]与新创建的物理端口的业务流程。  

4. 单击**业务流程**在应用程序中，右键单击业务流程以登记，然后单击**登记**。  

5. 单击**业务流程**在应用程序中，右键单击业务流程以登记，然后单击**启动**。  

6. 右键单击你[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序，，然后单击**启动**。  

## <a name="generate-multiple-schemas"></a>生成多个架构  
 如果使用使用适配器服务向导来生成多个架构，一个或多个元素可能会导致编译失败有关的架构中重复[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。 您可以避免此问题选择**生成唯一的架构类型**复选框以确保架构类型生成包含唯一命名空间。  

## <a name="see-also"></a>请参阅  
 [使用创建使用 WCF LOB 适配器 SDK 的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)