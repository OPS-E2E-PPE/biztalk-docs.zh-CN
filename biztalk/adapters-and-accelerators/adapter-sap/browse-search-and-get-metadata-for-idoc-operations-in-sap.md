---
title: 浏览、 搜索和 SAP 中的 IDOC 操作获取元数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF client, generating for IDOC operations
- IDOCs, searching
- searching, IDOCs
- IDOCs, browsing
- browsing, IDOCs
- IDOC operations, generating schema for
- IDOC operations
ms.assetid: 44d05129-ce06-4a10-bf28-9d3519a02a7a
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4c82ecf945e85c8e4c9b5f365c808598fcbbf3a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="browse-search-and-get-metadata-for-idoc-operations-in-sap"></a>浏览、 搜索和 SAP 中的 IDOC 操作获取元数据
此部分提供有关如何浏览、 搜索和检索元数据从 SAP IDOC 操作使用说明[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 说明大部分都是相同的所有三个用户界面。 任何位置都提供相关的用户界面的适用，单独的过程。  
  
 在执行之前提供下列部分中的步骤，你必须具有：  
  
-   创建[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。  
  
-   连接到 SAP 系统使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 有关说明，请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)请注意，连接至 SAP 系统生成架构或 Idoc 的 WCF 客户端之前，你必须设置某些绑定属性。  
  
    -   GenerateFlatFileCompatibleIdocSchema  
  
    -   ReceiveIdocFormat  
  
    -   FlatFileSegmentIndicator  
  
     这些属性控制从 SAP 系统检索 IDOC 的元数据的方式。 有关这些属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。 有关如何设置绑定属性的说明，请参阅[配置 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。  
  
## <a name="browsing-idocs-in-an-sap-system"></a>在某个 SAP 系统中浏览到的 Idoc  
 浏览元数据中使用的同时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]曲面将用于发送和接收到的 Idoc 从 SAP 系统的操作。  
  
-   **发送**和**接收**。 适配器客户端可以使用这些操作来发送和接收到的 Idoc 从 SAP 系统使用强类型的架构。 适配器呈现单独为每个 IDOC 这些操作，并且有各自的 IDOC 节点下。  
  
-   **SendIdoc**和**ReceiveIdoc**。 适配器客户端可以使用这些操作来发送和接收到的 Idoc 从 SAP 系统使用弱类型的架构。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]仅呈现一个**SendIdoc**和**ReceiveIdoc**所有 Idoc 的操作。 这些操作直接下有**IDOC**节点。  
  
 执行以下步骤浏览到的 Idoc 中 SAP 系统使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-browse-idocs-in-an-sap-system"></a>浏览到的 Idoc 中某个 SAP 系统  
  
1.  连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**下拉列表中，选择基于你将可执行使用适配器的入站或出站操作的协定的类型。  
  
3.  在**选择类别**框中，单击以查看中的 IDOC 消息类型的 IDOC 节点**可用类别和操作**框。 或者，你还可以通过展开 IDOC 节点来查看 IDOC 消息类型。  
  
    > [!TIP]
    >  你可以直接转到"即时"类别节点或子类别节点在树中，通过键入中项目的名称上时将焦点的树视图中**选择类别**框。 例如，若要跳转到**ACC_BILLING** IDOC 消息类型，关注**IDOC**节点，并键入`ACC_BILLING`。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出 IDOC 消息类型。 根 IDOC 节点还显示**SendIdoc**选项将弱类型 Idoc 发送到 SAP 系统。  
  
     ![浏览 IDOC 中的消息类型](../../adapters-and-accelerators/adapter-sap/media/3b8701c2-0530-4577-817c-92af0cd9a770.gif "3b8701c2-0530-4577-817c-92af0cd9a770")  
  
    > [!NOTE]
    >  对于入站的方案，根 IDOC 节点曲面**ReceiveIdoc**操作接收弱类型化 Idoc。  
  
4.  单击以查看相关的 IDOC 类型的 IDOC 消息类型。 下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]下特定 IDOC 的 IDOC 类型消息类型。  
  
     ![浏览 IDOC 类型](../../adapters-and-accelerators/adapter-sap/media/fee70ed2-74c1-4c91-b2fd-3d281a335145.gif "fee70ed2-74c1-4c91-b2fd-3d281a335145")  
  
5.  单击以查看 IDOC 类型的不同版本的 IDOC 类型。 下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]与特定的 IDOC 类型版本。  
  
     ![浏览 IDOC 类型版本](../../adapters-and-accelerators/adapter-sap/media/35603fac-ff48-40b1-bb51-bd0548715cd3.gif "35603fac-ff48-40b1-bb51-bd0548715cd3")  
  
6.  单击要查看该 IDOC 类型支持的操作的 IDOC 类型版本。 下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]与特定的 IDOC 类型版本支持该操作。  
  
     ![浏览 IDOC 类型的操作](../../adapters-and-accelerators/adapter-sap/media/f37624b4-f1f2-4d44-8708-01eb51a2d2a7.gif "f37624b4-f1f2-4d44-8708-01eb51a2d2a7")  
  
## <a name="searching-idocs-in-an-sap-system"></a>在某个 SAP 系统中搜索到的 Idoc  
 搜索到的 Idoc 中 SAP 系统使用元数据时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]， [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
-   在搜索表达式中支持通配符。  
  
-   立即在从该处执行搜索操作的节点下启用搜索。  
  
 下表列出了可以用于搜索和其解释的特殊字符[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|+（加号）|完全匹配一个字符。<br /><br /> 例如，A + 匹配 AB、 AC、 AD|  
|*（星号）|匹配零个或多个字符。<br /><br /> 例如，A * A，AB，与 ABC 匹配。|  
  
 有关支持的适配器的特殊字符的详细信息，请参阅[将适配器设置公开为使用 WCF LOB 适配器 SDK 绑定属性](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md)。
  
 执行以下步骤，在其中进行搜索到的 Idoc SAP 系统使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]， [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-search-idocs-in-an-sap-system"></a>若要在某个 SAP 系统中搜索到的 Idoc  
  
1.  连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**下拉列表中，选择根据你是否将搜索的入站或出站使用适配器的操作的协定的类型。  
  
3.  在**选择类别**框中，单击 IDOC 节点。  
  
    > [!IMPORTANT]
    >  你可以搜索仅在根级别的 Idoc。  
  
4.  在**类别中的搜索**文本框中，输入搜索表达式以搜索特定的 IDOC 消息类型。 例如，若要搜索其名称中有"MATMAS"的 Idoc，键入 * MATMAS\*在文本框中。  
  
5.  单击与右箭头图标以开始搜索按钮。 完成搜索后**可用类别和操作**框中列出的 Idoc 满足搜索条件。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出 IDOC 搜索结果。  
  
     ![在某个 SAP 系统中搜索到的 Idoc](../../adapters-and-accelerators/adapter-sap/media/tut1-lesson3-step3-idocsearch.gif "Tut1 Lesson3-步骤 3 IDOCSearch")  
  
## <a name="generating-schema-for-biztalk-projects"></a>为 BizTalk 项目生成架构  
 你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成为选择的 SAP 项目的架构。 浏览并搜索你想要调用的项目后，你可以生成这些项目的架构和发送消息，符合架构，到 SAP 系统。  
  
> [!NOTE]
>  你可以选择要在该类别的子树中返回的所有操作的类别节点-例如，你可以选择 （要在该组中生成架构的 Idoc 的所有版本） 的 IDOC 类型或选择特定版本的 IDOC 生成仅该版本的架构IDOC。 有关节点的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。  
  
#### <a name="to-retrieve-metadata-for-idocs"></a>若要检索到的 Idoc 的元数据  
  
1.  连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**下拉列表中，选择基于你将可执行使用适配器的入站或出站操作的协定的类型。  
  
3.  在**选择类别**框中，单击 IDOC 消息类型或你想要生成元数据的 IDOC 类型。  
  
4.  在**可用类别和操作**框中，选择 IDOC 类型或支持的操作，你想要生成元数据，并单击**添加**。 中列出的所选的 IDOC 类型或操作**添加类别和操作**框。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出所选的 Idoc。  
  
     ![元数据检索到的 Idoc](../../adapters-and-accelerators/adapter-sap/media/d9765c62-68b2-4313-9292-9265ab095e2e.gif "d9765c62-68b2-4313-9292-9265ab095e2e")  
  
     如果你想要为多个操作生成架构，可能有一些重复的元素定义之间可能会导致失败编译 BizTalk 项目这些架构。 例如，考虑其中生成操作"Op1"的架构的方案。 "Op1"的架构包含复杂数据类型"CT1"的参数。 为"Op1"生成架构后，你关闭[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]然后重新打开它以生成用于另一操作"Op2"的架构。 假定"Op2"还包含复杂数据类型"CT1"的参数。 退出后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和编译该项目，你将收到编译错误，因为两次在不同的 XSD 文件中定义的复杂数据类型"CT1"。 在这种情况下，我们的建议如下：  
  
    -   中的一次运行生成的所有操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 这样可确保[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成只有一个定义的复杂数据类型"CT1"。  
  
    -   如果你想要跨不同运行的生成对多个操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请确保选择**生成唯一的架构类型**复选框，以便生成的 XSD 文件包含对复杂的唯一命名空间数据类型"CT1"。  
  
5.  单击 **“确定”**。 架构文件保存带.xsd 扩展名为 IDOC 项目所在的位置。  
  
    > [!NOTE]
    >  如果你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，默认情况下会使用创建文件的命名约定"SAPBinding\<n\>.xsd"，其中 n 可以是 1，2，等等具体取决于架构创建的文件数。 或者，您可以通过输入中的名称提供自定义名称的架构文件到**文件名前缀**文本框。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]现在使用的命名约定创建架构文件\<文件名前缀\>\<n\>.xsd。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建包含你在生成架构时指定的绑定属性的绑定文件 （XML 文件） 的操作和要调用的操作的 SOAP 操作。 你可以导入在 BizTalk Server 管理控制台中创建 WCF 自定义端口连接 URI，绑定属性与此绑定文件和设置的 SOAP 操作。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件，以便 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。  
  
6.  在“文件”  菜单上，单击“全部保存” 。  
  
## <a name="generating-a-wcf-client-for-idoc-operations-using-the-add-adapter-service-reference-plug-in"></a>生成 WCF 客户端使用的 IDOC 操作添加插件的适配器服务引用  
 你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端代码，以发送到 SAP 系统的 Idoc，或者从某个 SAP 系统接收到的 Idoc 的 WCF 服务协定。  
  
#### <a name="to-generate-a-wcf-client-or-a-wcf-service-contract-for-idocs"></a>若要为 Idoc 生成 WCF 客户端或 WCF 服务协定  
  
1.  在[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从**选择协定类型**下拉列表中，选择基于是否你将执行入站 (接收到的 Idoc) 或出站 （发送到的 Idoc） 的操作的协定的类型。  
  
2.  在**选择类别**框中，展开**IDOC**节点，，然后浏览或搜索 IDOC 消息类型或你想要发送或接收的 IDOC 类型。  
  
3.  在**可用类别和操作**框中，选择 IDOC 类型或支持的操作，你要为其生成 WCF 客户端 （或 WCF 服务约定），然后单击**添加**。 中列出了所选的操作**添加类别和操作**框。 你可以选择中列出的任何节点**可用类别和操作**框。 如果选择类别节点中，则所有该节点下可执行的操作，并且将添加及其子节点。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]对于每种 IDOC 类型生成一个唯一的 WCF 客户端类 （或 WCF 服务协定）。 根据类别和你选择的操作，可能会生成多个 WCF 客户端类。 有关详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
4.  在大多数情况下的默认序列化选项已足够;但是，如果需要你可以控制生成的代码有关的几个方面和序列化程序使用的类型。 若要设置这些选项：  
  
    1.  单击**高级选项**以打开**高级选项**框。  
  
    2.  在**高级选项**下框中**选择生成的代理的选项**，选择所需的选项。 例如，你可以选择是否为 WCF 客户端生成异步方法，或禁用配置文件的生成。  
  
    3.  下**序列化程序**选择应使用的序列化程序。  
  
     下图显示**高级选项**包装盒默认选择 (**自动**选择为所选序列化程序和任何其他选项)。  
  
     ![高级选项框中的默认设置](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     你可以在配置的选项**高级选项**使用 ServiceModel 元数据实用工具 (svcutil.exe) 时，框将等效于某些可用的选项。 有关这些选项的详细信息，请参阅[ServiceModel 元数据实用工具 (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。
  
5.  单击 **“确定”**。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将保存的 WCF 客户端类 （或 WCF 服务接口） 和帮助器代码的操作和你选择了你的项目目录中的类别。 默认情况下，也保存配置文件。 为入站和出站操作; 生成略有不同的文件有关详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在 Visual Studio 中获取 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)