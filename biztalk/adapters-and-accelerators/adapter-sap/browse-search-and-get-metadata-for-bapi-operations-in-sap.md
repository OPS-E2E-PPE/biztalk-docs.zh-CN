---
title: 浏览、 搜索和获取 BAPI 操作在 SAP 中的元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI operations
- WCF client, generating for BAPI operations
- BAPIs, browsing
- searching, BAPIs
- browsing, BAPIs
- BAPIs, searching
- BAPI operations, generating schema
ms.assetid: 2884215a-ddba-40c7-bf9f-bfc7831f90bb
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97a043c08cf8d7ef258ceb2a2f311d2a86302881
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978950"
---
# <a name="browse-search-and-get-metadata-for-bapi-operations-in-sap"></a>浏览、 搜索和获取 BAPI 操作在 SAP 中的元数据
本部分说明如何浏览、 搜索和检索 BAPI 操作使用的 sap 元数据[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 说明的大多数都是相同的所有三个用户界面。 只要为相关的用户界面提供了适用的单独操作步骤。  
  
 在执行之前提供以下各节中的步骤，您必须具有：  
  
- 创建[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。  
  
- 连接到 SAP 系统使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 有关说明，请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)。  
  
## <a name="browsing-bapis-in-an-sap-system"></a>在 SAP 系统中浏览 Bapi  
 浏览元数据中使用的同时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)][!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为业务对象和 Rfc 的图面 Bapi。 浏览 Bapi 作为 Rfc 是类似于在 SAP 系统中浏览 RFC。 在这种情况下，Bapi 都可用作下 Rfc **RFC**。 浏览 Rfc 的详细信息，请参阅[浏览、 搜索和获取 RFC 操作在 SAP 中的元数据](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)。  
  
 本部分上浏览 Bapi 中作为业务对象提供信息。 有关浏览 SAP 元数据的详细信息，请参阅[原理适配器面 SAP 元数据？](https://msdn.microsoft.com/library/dd788039.aspx)  
  
 执行以下步骤中 SAP 系统使用浏览 Bapi [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
 
  
#### <a name="to-browse-bapis-in-an-sap-system"></a>若要在 SAP 系统中浏览 Bapi  
  
1. 连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**下拉列表中，选择基于是否将执行使用该适配器的入站或出站操作的协定的类型。  
  
3. 在中**选择一个类别**框中，单击要查看中的 BAPI 功能区域的 BAPI 节点**可用类别和操作**框。 或者，您还可以通过展开 BAPI 节点来查看 BAPI 功能区域。  
  
   > [!TIP]
   >  您可以直接转到"即时"类别节点或子类别节点在树中，通过键入中项目的名称的树视图中聚焦时**选择一个类别**框。 例如，若要跳转到**控制**BAPI 功能区域中，重点介绍**BAPI**节点，并键入`Controlling`。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出 BAPI 功能区域。  
  
    ![浏览 BAPI 中的功能区](../../adapters-and-accelerators/adapter-sap/media/d4b03725-44d2-449d-a035-491cd7415139.gif "d4b03725-44d2-449d-a035-491cd7415139")  
  
4. 单击以查看更多的 BAPI 功能区类别的 BAPI 功能区域。  
  
5. 单击以查看相关的操作支持该功能区域的 BAPI 功能区域。 下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]与支持特定功能区域的操作。  
  
    ![浏览用于 BAPI 的操作](../../adapters-and-accelerators/adapter-sap/media/1a9be42e-1f9e-4cf6-a555-c4e755fcc0ea.gif "1a9be42e-1f9e-4cf6-a555-c4e755fcc0ea")  
  
## <a name="searching-bapis-in-an-sap-system"></a>SAP 系统中搜索 Bapi  
 在 SAP 系统使用搜索 Bapi 的元数据时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
- 搜索表达式中支持通配符字符。  
  
- 可以立即执行搜索操作的间隔的节点下的搜索。  
  
  下表列出了可用于搜索和通过其解释的特殊字符[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|+（加号）|匹配一个字符。<br /><br /> 例如，A + 匹配 AB，交流，AD|  
|*（星号）|匹配零个或多个字符。<br /><br /> 例如，A * A，AB，ABC 匹配。|  
  
 有关适配器支持的特殊字符的详细信息，请参阅[原理适配器面 SAP 元数据？](https://msdn.microsoft.com/library/dd788039.aspx)  
  
 执行以下步骤在 SAP 系统使用中搜索 Bapi [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-search-bapis-in-an-sap-system"></a>若要在 SAP 系统中搜索 Bapi  
  
1. 连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**下拉列表中，选择根据你是否将搜索使用的适配器的入站或出站操作的协定的类型。  
  
3. 在中**选择一个类别**框中，单击包含想要搜索的 BAPI 的 BAPI 功能区域。  
  
   > [!NOTE]
   >  您可以搜索仅在根级别的 Bapi。  
  
4. 在中**类别中的搜索**文字框中，输入要搜索特定 BAPI 的搜索表达式。 例如，若要搜索名称中含有"帐户"的 Bapi，请键入 * 帐户\*在文本框中。  
  
5. 单击开始搜索的向右箭头图标按钮。 搜索完成后**可用类别和操作**框中列出的 Bapi 满足搜索条件。  
  
6. 下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出 BAPI 搜索结果。  
  
    ![SAP 系统中搜索 Bapi](../../adapters-and-accelerators/adapter-sap/media/82771a47-b656-473e-a96d-998bced38b35.gif "82771a47-b656-473e-a96d-998bced38b35")  
  
## <a name="generating-schema-for-biztalk-projects"></a>对于 BizTalk 项目的生成架构  
 可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成所选的 SAP 项目的架构。 浏览并搜索你想要调用的项目后，您可以生成的项目的架构和发送消息，符合架构，到 SAP 系统。  
  
> [!NOTE]
>  可以选择要在该类别的子树中返回的所有操作的类别节点，例如，可以选择整个 BAPI 子功能是 （若要为该组中的所有 Bapi 生成架构） 或选择特定的 Bapi 为只这些 Bapi 生成架构。 有关节点的详细信息，请参阅[元数据节点 IDs4](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。  
  
#### <a name="to-retrieve-metadata-for-bapis"></a>若要检索 Bapi 的元数据  
  
1. 连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**下拉列表中，选择基于是否将执行使用该适配器的入站或出站操作的协定的类型。  
  
3. 在中**选择一个类别**框中，单击包含您要为其生成元数据的 BAPI 的 BAPI 功能组。  
  
4. 在中**可用类别和操作**框中，选择要为其生成元数据，并单击的操作的功能区域**添加**。 中列出的所选功能区域或操作**添加的类别和操作**框。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出所选的 Bapi。  
  
    ![检索 BAPI 的元数据](../../adapters-and-accelerators/adapter-sap/media/74170978-aef0-46c9-a6e2-36d6e9c2aefc.gif "74170978-aef0-46c9-a6e2-36d6e9c2aefc")  
  
    如果你想要为多个操作生成架构，可能有一些重复的元素定义由这些架构会导致在编译 BizTalk 项目中的问题。 例如，假设其中生成操作"Op1"的架构。 "Op1"的架构包含复杂数据类型"CT1"的参数。 对于"Op1"生成架构后关闭[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]并重新打开它以生成架构的另一项操作"Op2"。 假定"Op2"还包含复杂数据类型"CT1"的参数。 退出后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和编译项目，你将收到编译错误，因为两次在不同的 XSD 文件中定义的复杂数据类型"CT1"。 在这种情况下，我们建议：  
  
   - 生成的所有操作的架构中的一次运行[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 这可确保[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成复杂的数据类型"CT1"只有一个定义。  
  
   - 如果你想要在不同的运行中生成多个操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请确保选择**生成唯一的架构类型**复选框，以便生成的 XSD 文件包含复杂的唯一命名空间数据类型"CT1"。  
  
5. 单击“确定” 。 架构文件保存具有.xsd 扩展名为 BizTalk 项目所在的位置。  
  
   > [!NOTE]
   >  如果使用的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，默认情况下创建的文件命名约定"SAPBinding\<n\>.xsd"，其中 n 可为 1，2，等具体取决于架构创建的文件数。 或者，可以通过输入一个名称中的提供的架构文件的自定义名称**文件名前缀**文本框。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]现在使用的命名约定创建架构文件\<文件名前缀\>\<n\>.xsd。  
   > 
   > [!NOTE]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建包含在生成架构时指定的绑定属性的绑定文件 （XML 文件） 的操作和要调用该操作的 SOAP 操作。 可以在 BizTalk Server 管理控制台创建 WCF 自定义端口的连接 URI，绑定属性与此绑定文件导入和 SOAP 操作集。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
  
6. 在“文件”  菜单上，单击“全部保存” 。  
  
## <a name="generating-a-wcf-client-for-bapi-operations-using-the-add-adapter-service-reference-plug-in"></a>生成 WCF 客户端使用的 BAPI 操作添加适配器服务引用插件  
 可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 （入站的操作不支持的 Bapi） BAPI 操作的 WCF 客户端代码。  
  
#### <a name="to-generate-a-wcf-client-for-bapis"></a>若要生成 WCF 客户端的 Bapi  
  
1. 在中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从**选择协定类型**下拉列表中，选择**客户端 （出站操作）**。  
  
2. 在中**选择一个类别**框中，展开**BAPI**节点，然后浏览或搜索 BAPI 类别或你想要生成 WCF 客户端的操作。  
  
3. 在中**可用类别和操作**框中，选择的操作或类别 （BAPI 功能组） 要为其生成 WCF 客户端，然后单击**添加**。 所选的操作所示**添加的类别和操作**框。 可以选择中列出的任何节点**可用类别和操作**框。 如果选择的类别节点，则将选择所有可用的节点及其子节点下的操作。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成每个业务对象的唯一 WCF 客户端类。 根据类别和你选择的操作，可能会生成多个 WCF 客户端类。 有关详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目的 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
4. 在大多数情况下的默认序列化选项是不够的;但是，如果需要可以控制生成的代码有关的几个方面和序列化程序使用的类型。 若要设置这些选项：  
  
   1. 单击**高级选项**以打开**高级选项**框。  
  
   2. 在中**高级选项**框下**选择生成的代理的选项**，选择所需的选项。 例如，可以选择是否异步方法生成 WCF 客户端或禁用配置文件的生成。  
  
   3. 下**序列化程序**选择应使用的序列化程序。  
  
      下图显示**高级选项**具有默认选择框 (**自动**处于选中状态的选择序列化程序和任何其他选项)。  
  
      ![高级选项框默认设置](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      可以在中配置的选项**高级选项**使用 ServiceModel Metadata Utility Tool (svcutil.exe) 时，框将等效于一些可用的选项。 有关这些选项的详细信息，请参阅[ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。 
  
5. 单击“确定” 。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将 WCF 客户端类和帮助程序代码保存为所选的操作和类别在项目目录中。 默认情况下，还保存配置文件。 有关详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目的 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中获取 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)