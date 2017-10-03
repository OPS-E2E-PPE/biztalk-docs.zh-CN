---
title: "连接到 Siebel 系统在 Visual Studio 使用添加适配器元数据向导 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0a82fcc-b3ac-4936-9210-03c99d3741d7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9fc38299ffdce6cf6227cacb7de0cae84b22091
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-metadata-wizard"></a>连接到 Siebel 系统在 Visual Studio 使用添加适配器元数据向导
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]名称还公开为 BizTalk 适配器，因此，你可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要为你想要在 Siebel 系统使用该适配器上执行的操作生成架构。  
  
## <a name="connecting-to-a-siebel-system-using-add-adapter-metadata-wizard"></a>连接到 Siebel 系统使用添加适配器元数据向导  
 执行以下步骤以连接到 Siebel 系统使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
#### <a name="to-connect-to-a-siebel-system"></a>若要连接到 Siebel 系统  
  
1.  若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：  
  
    1.  创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
    2.  右键单击解决方案资源管理器中的项目，指向**添加**，然后单击**添加生成的项**。  
  
    3.  在**添加生成的项**对话框框中，执行以下操作：  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**类别**|单击**使用适配器服务**。|  
        |**模板**|单击**使用适配器服务**。|  
  
    4.  单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  
  
    5.  在[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择 WCF Siebel。 选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。  
  
        > [!IMPORTANT]
        >  如果你已有**WCF Siebel**端口中配置的 BizTalk，选择从端口**端口**列表。  
  
    6.  单击 **“下一步”**。  
  
2.  从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**。  
  
3.  在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**.  
  
4.  指定的用户名和密码以连接到 Siebel 系统。  
  
5.  单击**URI 属性**选项卡，然后指定连接参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。  
  
    > [!NOTE]
    >  如果连接参数包含任何保留的字符，则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。 但是，如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。  
  
6.  单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。 有关绑定属性的详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。  
  
    > [!NOTE]
    >  如果正在生成元数据中使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]并且选择现有 WCF Siebel 发送端口，你不需要指定的绑定属性。 绑定属性是从发送端口配置中选取。 但是，你可以选择指定所需在设计时，如果任何绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定中发送端口配置的绑定属性的值将适用。  
  
7.  单击 **“确定”**。  
  
8.  单击 **“连接”**。 一旦建立连接，连接状态将显示为**已连接**。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。  
  
     ![使用适配器服务连接的对话框](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")  
  
     [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在 Siebel 系统执行的各种操作的不同节点。 例如，**业务对象**节点包含所有的业务对象和可以调用 Siebel 系统的业务组件。 同样，**业务服务**节点连接到 Siebel 系统中包含所有业务服务。 有关这些节点的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。