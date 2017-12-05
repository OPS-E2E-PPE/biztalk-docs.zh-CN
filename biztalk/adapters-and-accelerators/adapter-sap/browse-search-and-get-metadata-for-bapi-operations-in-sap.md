---
title: "浏览、 搜索和 SAP 中的 BAPI 操作获取元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaf2145bd288d844a3ad02e222a8d8193f32b7de
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="browse-search-and-get-metadata-for-bapi-operations-in-sap"></a>浏览、 搜索和 SAP 中的 BAPI 操作获取元数据
此部分提供有关如何浏览、 搜索和检索元数据从 SAP BAPI 操作使用说明[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 说明大部分都是相同的所有三个用户界面。 任何位置都提供相关的用户界面的适用，单独的过程。  
  
 在执行之前提供下列部分中的步骤，你必须具有：  
  
-   创建[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。  
  
-   连接到 SAP 系统使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 有关说明，请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)。  
  
## <a name="browsing-bapis-in-an-sap-system"></a>在某个 SAP 系统中浏览 BAPIs  
 浏览元数据中使用的同时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)][!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现 BAPIs 作为业务对象和 Rfc。 浏览作为 Rfc BAPIs 等同于 SAP 系统中浏览 RFC。 在这种情况下，BAPIs 都可用作下 Rfc **RFC**。 浏览 Rfc 的详细信息，请参阅[浏览、 搜索和 SAP 中的 RFC 操作的 get 元数据](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)。  
  
 本部分提供浏览 BAPIs 作为业务对象上的信息。 有关浏览 SAP 元数据的详细信息，请参阅[原理适配器面 SAP 元数据？](https://msdn.microsoft.com/library/dd788039.aspx)  
  
 执行以下步骤浏览 BAPIs 中 SAP 系统使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
 
  
#### <a name="to-browse-bapis-in-an-sap-system"></a>浏览 BAPIs 中某个 SAP 系统  
  
1.  连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**下拉列表中，选择基于你将可执行使用适配器的入站或出站操作的协定的类型。  
  
3.  在**选择类别**框中，单击以查看 BAPI 功能区域中的 BAPI 节点**可用类别和操作**框。 或者，你还可以通过展开 BAPI 节点来查看 BAPI 功能区域。  
  
    > [!TIP]
    >  你可以直接转到"即时"类别节点或子类别节点在树中，通过键入中项目的名称上时将焦点的树视图中**选择类别**框。 例如，若要跳转到**控制**BAPI 功能区域中，使得侧重于**BAPI**节点，并键入`Controlling`。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出 BAPI 功能区域。  
  
     ![浏览功能区域中 BAPI](../../adapters-and-accelerators/adapter-sap/media/d4b03725-44d2-449d-a035-491cd7415139.gif "d4b03725-44d2-449d-a035-491cd7415139")  
  
4.  单击 BAPI 功能区域，以查看 BAPI 功能区域的进一步分类。  
  
5.  单击 BAPI 功能区域，以查看相关的操作以支持该功能区域。 下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]与支持特定功能区域的操作。  
  
     ![浏览 BAPI 操作](../../adapters-and-accelerators/adapter-sap/media/1a9be42e-1f9e-4cf6-a555-c4e755fcc0ea.gif "1a9be42e-1f9e-4cf6-a555-c4e755fcc0ea")  
  
## <a name="searching-bapis-in-an-sap-system"></a>在某个 SAP 系统中搜索 BAPIs  
 在 SAP 系统使用 BAPIs 搜索元数据时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
-   在搜索表达式中支持通配符。  
  
-   立即在从该处执行搜索操作的节点下启用搜索。  
  
 下表列出了可以用于搜索和其解释的特殊字符[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|+ （加）|完全匹配一个字符。<br /><br /> 例如，A + 匹配 AB、 AC、 AD|  
|*（星号）|匹配零个或多个字符。<br /><br /> 例如，A * A，AB，与 ABC 匹配。|  
  
 有关支持的适配器的特殊字符的详细信息，请参阅[原理适配器面 SAP 元数据？](https://msdn.microsoft.com/library/dd788039.aspx)  
  
 执行以下步骤，在其中进行搜索 BAPIs SAP 系统使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-search-bapis-in-an-sap-system"></a>在其中进行搜索 BAPIs SAP 系统  
  
1.  连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**下拉列表中，选择根据你是否将搜索的入站或出站使用适配器的操作的协定的类型。  
  
3.  在**选择类别**框中，单击包含您想要搜索的 BAPI BAPI 功能区域。  
  
    > [!NOTE]
    >  你可以搜索 BAPIs 仅在根级别。  
  
4.  在**类别中的搜索**文本框中，输入要搜索特定 BAPI 搜索表达式。 例如，若要搜索 BAPIs 其名称中有"帐户"，键入 * 帐户\*在文本框中。  
  
5.  单击与右箭头图标以开始搜索按钮。 完成搜索后**可用类别和操作**框中列出的 BAPIs 满足搜索条件。  
  
6.  下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出 BAPI 搜索结果。  
  
     ![在某个 SAP 系统中搜索 BAPIs](../../adapters-and-accelerators/adapter-sap/media/82771a47-b656-473e-a96d-998bced38b35.gif "82771a47-b656-473e-a96d-998bced38b35")  
  
## <a name="generating-schema-for-biztalk-projects"></a>为 BizTalk 项目生成架构  
 你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成为选择的 SAP 项目的架构。 浏览并搜索你想要调用的项目后，你可以生成这些项目的架构和发送消息，符合架构，到 SAP 系统。  
  
> [!NOTE]
>  你可以选择要在该类别的子树中返回的所有操作的类别节点-例如，你可以选择整个 BAPI 子功能将 （若要为该组中的所有 BAPIs 生成架构） 或选择特定 BAPIs 为只这些 BAPIs 生成架构。 有关节点的详细信息，请参阅[元数据节点 IDs4](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。  
  
#### <a name="to-retrieve-metadata-for-bapis"></a>若要为 BAPIs 检索元数据  
  
1.  连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**下拉列表中，选择基于你将可执行使用适配器的入站或出站操作的协定的类型。  
  
3.  在**选择类别**框中，单击包含你想要生成元数据的 BAPI BAPI 功能组。  
  
4.  在**可用类别和操作**框中，选择你想要生成元数据，并单击的操作的功能区域**添加**。 中列出的所选的功能区域或操作**添加类别和操作**框。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出所选的 BAPIs。  
  
     ![元数据检索 BAPI](../../adapters-and-accelerators/adapter-sap/media/74170978-aef0-46c9-a6e2-36d6e9c2aefc.gif "74170978-aef0-46c9-a6e2-36d6e9c2aefc")  
  
     如果你想要为多个操作生成架构，可能有一些重复的元素定义之间可能会导致失败编译 BizTalk 项目这些架构。 例如，考虑其中生成操作"Op1"的架构的方案。 "Op1"的架构包含复杂数据类型"CT1"的参数。 为"Op1"生成架构后，你关闭[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]然后重新打开它以生成用于另一操作"Op2"的架构。 假定"Op2"还包含复杂数据类型"CT1"的参数。 退出后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和编译该项目，你将收到编译错误，因为两次在不同的 XSD 文件中定义的复杂数据类型"CT1"。 在这种情况下，我们的建议如下：  
  
    -   中的一次运行生成的所有操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 这样可确保[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成只有一个定义的复杂数据类型"CT1"。  
  
    -   如果你想要跨不同运行的生成对多个操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请确保选择**生成唯一的架构类型**复选框，以便生成的 XSD 文件包含对复杂的唯一命名空间数据类型"CT1"。  
  
5.  单击 **“确定”**。 架构文件保存带.xsd 扩展名为 BizTalk 项目所在的位置。  
  
    > [!NOTE]
    >  如果你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，默认情况下会使用创建文件的命名约定"SAPBinding\<n\>.xsd"，其中 n 可以是 1，2，等等具体取决于架构创建的文件数。 或者，您可以通过输入中的名称提供自定义名称的架构文件到**文件名前缀**文本框。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]现在使用的命名约定创建架构文件\<文件名前缀\>\<n\>.xsd。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建包含你在生成架构时指定的绑定属性的绑定文件 （XML 文件） 的操作和要调用的操作的 SOAP 操作。 你可以导入在 BizTalk Server 管理控制台中创建 WCF 自定义端口连接 URI，绑定属性与此绑定文件和设置的 SOAP 操作。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件，以便 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
  
6.  在“文件”  菜单上，单击“全部保存” 。  
  
## <a name="generating-a-wcf-client-for-bapi-operations-using-the-add-adapter-service-reference-plug-in"></a>生成 WCF 客户端使用的 BAPI 操作添加插件的适配器服务引用  
 你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 BAPI 操作 （入站的操作不支持为 BAPIs） 的 WCF 客户端代码。  
  
#### <a name="to-generate-a-wcf-client-for-bapis"></a>若要生成 BAPIs 的 WCF 客户端  
  
1.  在[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从**选择协定类型**下拉列表中，选择**客户端 （出站操作）**。  
  
2.  在**选择类别**框中，展开**BAPI**节点，，然后浏览或搜索 BAPI 类别或你想要生成 WCF 客户端的操作。  
  
3.  在**可用类别和操作**框中，选择您要为其生成 WCF 客户端，并依次的类别 （BAPI 功能组） 的操作**添加**。 中列出了所选的操作**添加类别和操作**框。 你可以选择中列出的任何节点**可用类别和操作**框。 如果你选择的类别节点，则该节点及其子节点下可执行的操作的所有将被选中。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成每个业务对象的唯一 WCF 客户端类。 根据类别和你选择的操作，可能会生成多个 WCF 客户端类。 有关详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
4.  在大多数情况下的默认序列化选项已足够;但是，如果需要你可以控制生成的代码有关的几个方面和序列化程序使用的类型。 若要设置这些选项：  
  
    1.  单击**高级选项**以打开**高级选项**框。  
  
    2.  在**高级选项**下框中**选择生成的代理的选项**，选择所需的选项。 例如，你可以选择是否为 WCF 客户端生成异步方法，或禁用配置文件的生成。  
  
    3.  下**序列化程序**选择应使用的序列化程序。  
  
     下图显示**高级选项**包装盒默认选择 (**自动**选择为所选序列化程序和任何其他选项)。  
  
     ![高级选项框中的默认设置](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     你可以在配置的选项**高级选项**使用 ServiceModel 元数据实用工具 (svcutil.exe) 时，框将等效于某些可用的选项。 有关这些选项的详细信息，请参阅[ServiceModel 元数据实用工具 (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。 
  
5.  单击 **“确定”**。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将 WCF 客户端类和帮助程序代码保存在项目目录的所选的操作和类别。 默认情况下，也保存配置文件。 有关详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在 Visual Studio 中获取 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)