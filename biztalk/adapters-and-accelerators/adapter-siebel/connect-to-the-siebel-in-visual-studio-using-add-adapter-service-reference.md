---
title: 连接到 Siebel 系统中 Visual Studio 中使用添加适配器服务引用插件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d27121be-6407-4bb6-acb5-37dc8a3785c0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0995e8b96d54593045a0b044d7ec635acff5622e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371908"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-service-reference-plug-in"></a>连接到 Siebel 系统中 Visual Studio 中使用添加适配器服务引用插件
连接到 Siebel 系统[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在.NET 编程解决方案中，必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 本主题说明了如何使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
## <a name="connecting-to-a-siebel-system-using-add-adapter-service-reference-plug-in"></a>连接到 Siebel 系统使用添加适配器服务引用插件  
 执行以下步骤连接到 Siebel 系统[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-connect-to-a-siebel-system"></a>若要连接到 Siebel 系统  
  
1. 若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：  
  
   1. 创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
   2. 右键单击解决方案资源管理器中的项目，然后单击**添加适配器服务引用**。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]随即打开。  
  
2. 从**选择绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**。  
  
3. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**.  
  
4. 指定的用户名和密码以连接到 Siebel 系统。  
  
5. 单击**URI 属性**选项卡，并指定连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。  
  
   > [!NOTE]
   >  如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  
  
6. 单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。  
  
7. 单击“确定” 。  
  
8. 单击 **“连接”**。 建立连接后，连接状态显示为**已连接**。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。 图形用户界面是适用于[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    ![使用适配器服务连接对话框](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")  
  
    [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]显示包含可以在 Siebel 系统执行各种操作的不同节点。 例如，**业务对象**节点包含所有的业务对象和可以在 Siebel 系统调用的业务组件。 同样，**业务服务**节点连接到 Siebel 系统中包含所有业务服务。 有关这些节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。