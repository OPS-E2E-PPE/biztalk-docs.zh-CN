---
title: Visual Studio 中使用连接到 SAP 使用适配器服务外接程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4f7d57a-fd88-4420-b893-49f42b449597
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb63593beb93555e8bc868a9bb3afdc121252350
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965035"
---
# <a name="connecting-to-sap-in-visual-studio-using-consume-adapter-service-add-in"></a>Visual Studio 中使用连接到 SAP 使用适配器服务外接程序
[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]安装 WCF LOB 适配器 SDK 时安装。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]加载在计算机上安装的所有 WCF 自定义绑定。 若要连接到 SAP 系统使用基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在 BizTalk 项目，你必须使用**sapbinding**。  
  
 本主题将说明了如何使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
## <a name="connecting-to-an-sap-system-using-consume-adapter-service-add-in"></a>连接到 SAP 系统使用使用适配器服务外接程序  
 执行以下步骤以连接到 SAP 系统使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
#### <a name="to-connect-to-an-sap-system"></a>若要连接到 SAP 系统  
  
1.  若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：  
  
    1.  创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
    2.  右键单击解决方案资源管理器中的项目名称，指向**添加**，然后单击**添加生成的项**。  
  
    3.  在**添加生成的项**对话框框中，执行以下操作：  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**类别**|单击**使用适配器服务**。|  
        |**模板**|单击**使用适配器服务**。|  
  
    4.  单击 **“添加”**。 此时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会打开。  
  
2.  从**选择的绑定**下拉列表中，选择**sapBinding**单击**配置**。  
  
3.  在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 SAP 系统。  
  
    > [!IMPORTANT]
    >  如果你使用 SAP 安全网络连接 (SNC) 库连接到 SAP 系统，则不指定用户名和密码。  
  
4.  单击**URI 属性**选项卡上，并指定连接参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
    > [!IMPORTANT]
    >  如果你使用 SAP SNC 库连接到 SAP 系统，设置**UseSnc**连接属性设置为**True**。  
  
    > [!NOTE]
    >  如果连接参数包含任何保留的字符，则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。 但是，如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。  
  
5.  单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。 例如，如果你想要针对 ReceiveIdoc 操作则必须设置**ReceiveIdocFormat**将属性绑定到字符串。 有关绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
    > [!IMPORTANT]
    >  如果你使用 SAP SNC 库连接到 SAP 系统，设置**SncLibrary**和**SncPartnerName**为适当的值。  
    >   
    >  **SncLibrary**绑定属性采用的路径以及使用 SNC 连接到 SAP 系统所需的 Dll 的文件名。 这些 Dll 必须存在 SAP 客户端计算机上和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装。 有关详细信息请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南位于\<安装指南\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。  
    >   
    >  **SncPartnerName**绑定属性将通信合作伙伴的 SNC 名称。  
  
6.  单击 **“确定”**。  
  
7.  单击 **“连接”**。 建立连接后，连接状态将显示为**已连接**。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。  
  
     ![使用适配器服务连接的对话框](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")  
  
     [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在某个 SAP 系统中调用的各种项目的不同节点。 例如， **RFC**节点包含在连接到 SAP 系统中可用的所有 Rfc。 有关这些节点的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在 Visual Studio 中连接到 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)