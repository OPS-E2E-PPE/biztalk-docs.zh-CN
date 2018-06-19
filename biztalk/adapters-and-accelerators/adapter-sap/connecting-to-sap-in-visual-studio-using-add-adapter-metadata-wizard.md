---
title: Visual Studio 中使用连接到 SAP 添加适配器元数据向导 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a442837b-e7d8-4edb-9c5e-5603d4c58fe5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db24d079dc428c69733e36141280504f97728b26
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966235"
---
# <a name="connecting-to-sap-in-visual-studio-using-add-adapter-metadata-wizard"></a>Visual Studio 中使用连接到 SAP 添加适配器元数据向导
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]名称还公开为 BizTalk 适配器，因此，你可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要为你想要在使用该适配器的 SAP 系统上执行的操作生成架构。  
  
## <a name="connecting-to-an-sap-system-using-add-adapter-metadata-wizard"></a>连接到 SAP 系统使用添加适配器元数据向导  
 执行以下步骤以连接到 SAP 系统使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
#### <a name="to-connect-to-an-sap-system"></a>若要连接到 SAP 系统  
  
1.  若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：  
  
    1.  创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
    2.  右键单击解决方案资源管理器中的项目名称，指向**添加**，然后单击**添加生成的项**。  
  
    3.  在**添加生成的项**对话框框中，执行以下操作：  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**类别**|单击**添加适配器**。|  
        |**模板**|单击**添加适配器元数据**。|  
  
    4.  单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  
  
    5.  在添加适配器向导中，选择**WCF SAP**。 选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。  
  
        > [!IMPORTANT]
        >  如果你已经在 BizTalk 中配置 WCF SAP 端口，选择从端口**端口**列表。  
  
    6.  单击 **“下一步”**。  
  
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
  
    > [!NOTE]
    >  如果正在生成元数据中使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]并且选择现有 WCF SAP 发送端口，你不需要指定的绑定属性。 绑定属性是从发送端口配置中选取。 但是，你可以选择指定所需在设计时，如果任何绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定中发送端口配置的绑定属性的值将适用。  
  
    > [!IMPORTANT]
    >  如果你使用 SAP SNC 库连接到 SAP 系统，设置**SncLibrary**和**SncPartnerName**为适当的值。  
    >   
    >  **SncLibrary**绑定属性采用的路径以及使用 SNC 连接到 SAP 系统所需的 Dll 的文件名。 这些 Dll 必须存在 SAP 客户端计算机上和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装。 有关详细信息请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南位于\<安装指南\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。  
    >   
    >  **SncPartnerName**绑定属性将通信合作伙伴的 SNC 名称。  
  
6.  单击 **“确定”**。  
  
7.  单击 **“连接”**。 建立连接后，连接状态将显示为**已连接**。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。 图形用户界面是适用于[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
     ![使用适配器服务连接的对话框](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")  
  
     [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在某个 SAP 系统中调用的各种项目的不同节点。 例如， **RFC**节点包含在连接到 SAP 系统中可用的所有 Rfc。 有关这些节点的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在 Visual Studio 中连接到 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)