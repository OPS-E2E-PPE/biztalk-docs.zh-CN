---
title: 浏览、 搜索和获取 IDOC 操作在 SAP 中的元数据 |Microsoft Docs
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 536a7ab77073c668378d65ffa29309a14a8159ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374138"
---
# <a name="browse-search-and-get-metadata-for-idoc-operations-in-sap"></a>浏览、 搜索和获取 IDOC 操作在 SAP 中的元数据
本部分提供有关如何浏览、 搜索和检索元数据从 SAP IDOC 操作使用的说明[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 说明的大多数都是相同的所有三个用户界面。 只要为相关的用户界面提供了适用的单独操作步骤。  
  
 在执行之前提供以下各节中的步骤，您必须具有：  
  
- 创建[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。  
  
- 连接到 SAP 系统使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 有关说明，请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)请注意，连接到 SAP 系统以生成架构或 Idoc 的 WCF 客户端之前，你必须设置某些绑定属性。  
  
  - GenerateFlatFileCompatibleIdocSchema  
  
  - ReceiveIdocFormat  
  
  - FlatFileSegmentIndicator  
  
    这些属性用于控制如何从 SAP 系统中检索 IDOC 的元数据。 有关这些属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。 有关如何设置绑定属性的说明，请参阅[配置的 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。  
  
## <a name="browsing-idocs-in-an-sap-system"></a>浏览 Idoc 中的 SAP 系统  
 浏览元数据中使用的同时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，则[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]图面区分用于发送和接收来自 SAP 系统的 Idoc 的操作。  
  
- **发送**并**接收**。 适配器客户端可以使用这些操作来发送和接收来自 SAP 系统使用强类型架构的 Idoc。 适配器单独为每个 IDOC 这些操作的图面，并提供相应的 IDOC 节点下。  
  
- **SendIdoc**并**ReceiveIdoc**。 适配器客户端可以使用这些操作来发送和接收来自 SAP 系统使用弱类型的架构的 Idoc。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]仅显示一个**SendIdoc**并**ReceiveIdoc**所有 idoc 的操作。 这些操作都直接位于**IDOC**节点。  
  
  执行以下步骤中 SAP 系统使用浏览 Idoc [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-browse-idocs-in-an-sap-system"></a>浏览 Idoc 中的 SAP 系统  
  
1. 连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**下拉列表中，选择基于是否将执行使用该适配器的入站或出站操作的协定的类型。  
  
3. 在中**选择一个类别**框中，单击要查看中的 IDOC 消息类型的 IDOC 节点**可用类别和操作**框。 或者，您还可以通过展开 IDOC 节点来查看 IDOC 消息类型。  
  
   > [!TIP]
   >  您可以直接转到"即时"类别节点或子类别节点在树中，通过键入中项目的名称的树视图中聚焦时**选择一个类别**框。 例如，若要跳转到**ACC_BILLING** IDOC 消息类型，重点介绍**IDOC**节点，并键入`ACC_BILLING`。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出 IDOC 的消息类型。 根 IDOC 节点还会呈现**SendIdoc**弱类型 Idoc 发送到 SAP 系统的选项。  
  
    ![浏览 IDOC 中的消息类型](../../adapters-and-accelerators/adapter-sap/media/3b8701c2-0530-4577-817c-92af0cd9a770.gif "3b8701c2-0530-4577-817c-92af0cd9a770")  
  
   > [!NOTE]
   >  对于入站的方案，根 IDOC 节点表面**ReceiveIdoc**操作接收弱类型化的 Idoc。  
  
4. 单击以查看相关的 IDOC 类型的 IDOC 消息类型。 下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]下特定 IDOC 的 IDOC 类型与消息类型。  
  
    ![浏览 IDOC 类型](../../adapters-and-accelerators/adapter-sap/media/fee70ed2-74c1-4c91-b2fd-3d281a335145.gif "fee70ed2-74c1-4c91-b2fd-3d281a335145")  
  
5. 单击以查看 IDOC 类型的不同版本的 IDOC 类型。 下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]特定 IDOC 类型的版本。  
  
    ![浏览 IDOC 类型的版本](../../adapters-and-accelerators/adapter-sap/media/35603fac-ff48-40b1-bb51-bd0548715cd3.gif "35603fac-ff48-40b1-bb51-bd0548715cd3")  
  
6. 单击要查看受支持的操作对该 IDOC 类型的 IDOC 类型的版本。 下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]与特定的 IDOC 类型版本支持的操作。  
  
    ![浏览用于 IDOC 类型的操作](../../adapters-and-accelerators/adapter-sap/media/f37624b4-f1f2-4d44-8708-01eb51a2d2a7.gif "f37624b4-f1f2-4d44-8708-01eb51a2d2a7")  
  
## <a name="searching-idocs-in-an-sap-system"></a>SAP 系统中搜索 Idoc  
 在 SAP 系统使用搜索 idoc 的元数据时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]， [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，则[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
- 搜索表达式中支持通配符字符。  
  
- 可以立即执行搜索操作的间隔的节点下的搜索。  
  
  下表列出了可用于搜索和通过其解释的特殊字符[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|+（加号）|匹配一个字符。<br /><br /> 例如，A + 匹配 AB，交流，AD|  
|*（星号）|匹配零个或多个字符。<br /><br /> 例如，A * A，AB，ABC 匹配。|  
  
 有关适配器支持的特殊字符的详细信息，请参阅[将适配器设置为使用 WCF LOB 适配器 SDK 的绑定属性](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md)。
  
 执行以下步骤在 SAP 系统使用中搜索 Idoc [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]， [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-search-idocs-in-an-sap-system"></a>若要在 SAP 系统中搜索 Idoc  
  
1. 连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**下拉列表中，选择根据你是否将搜索使用的适配器的入站或出站操作的协定的类型。  
  
3. 在中**选择一个类别**框中，单击 IDOC 节点。  
  
   > [!IMPORTANT]
   >  您可以搜索仅在根级别的 Idoc。  
  
4. 在中**类别中的搜索**文字框中，输入要搜索特定的 IDOC 消息类型的搜索表达式。 例如，若要搜索名称中含有"MATMAS"的 Idoc，请键入 * MATMAS\*在文本框中。  
  
5. 单击开始搜索的向右箭头图标按钮。 搜索完成后**可用类别和操作**框列出了满足搜索条件的 Idoc。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出 IDOC 搜索结果。  
  
    ![SAP 系统中搜索 Idoc](../../adapters-and-accelerators/adapter-sap/media/tut1-lesson3-step3-idocsearch.gif "Tut1-Lesson3-Step3-IDOCSearch")  
  
## <a name="generating-schema-for-biztalk-projects"></a>对于 BizTalk 项目的生成架构  
 可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成所选的 SAP 项目的架构。 浏览并搜索你想要调用的项目后，您可以生成的项目的架构和发送消息，符合架构，到 SAP 系统。  
  
> [!NOTE]
>  可以选择要在该类别的子树中返回的所有操作的类别节点，例如，可以选择 （要在该组中生成的所有版本的 Idoc 的架构） 的 IDOC 类型或选择特定版本的 IDOC 生成仅该版本的架构IDOC。 有关节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。  
  
#### <a name="to-retrieve-metadata-for-idocs"></a>若要检索 Idoc 的元数据  
  
1. 连接到 SAP 服务器使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**下拉列表中，选择基于是否将执行使用该适配器的入站或出站操作的协定的类型。  
  
3. 在中**选择一个类别**框中，单击 IDOC 消息类型或你想要生成元数据的 IDOC 类型。  
  
4. 在中**可用类别和操作**框中，选择 IDOC 类型或支持的操作，您要为其生成元数据，并单击**添加**。 中列出的所选的 IDOC 类型或操作**添加的类别和操作**框。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]列出所选的 Idoc。  
  
    ![检索 Idoc 的元数据](../../adapters-and-accelerators/adapter-sap/media/d9765c62-68b2-4313-9292-9265ab095e2e.gif "d9765c62-68b2-4313-9292-9265ab095e2e")  
  
    如果你想要为多个操作生成架构，可能有一些重复的元素定义由这些架构会导致在编译 BizTalk 项目中的问题。 例如，假设其中生成操作"Op1"的架构。 "Op1"的架构包含复杂数据类型"CT1"的参数。 对于"Op1"生成架构后关闭[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]并重新打开它以生成架构的另一项操作"Op2"。 假定"Op2"还包含复杂数据类型"CT1"的参数。 退出后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和编译项目，你将收到编译错误，因为两次在不同的 XSD 文件中定义的复杂数据类型"CT1"。 在这种情况下，我们建议：  
  
   - 生成的所有操作的架构中的一次运行[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 这可确保[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成复杂的数据类型"CT1"只有一个定义。  
  
   - 如果你想要在不同的运行中生成多个操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请确保选择**生成唯一的架构类型**复选框，以便生成的 XSD 文件包含复杂的唯一命名空间数据类型"CT1"。  
  
5. 单击“确定” 。 架构文件保存具有.xsd 扩展名为 IDOC 项目所在的位置。  
  
   > [!NOTE]
   >  如果使用的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，默认情况下创建的文件命名约定"SAPBinding\<n\>.xsd"，其中 n 可为 1，2，等具体取决于架构创建的文件数。 或者，可以通过输入一个名称中的提供的架构文件的自定义名称**文件名前缀**文本框。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]现在使用的命名约定创建架构文件\<文件名前缀\>\<n\>.xsd。  
   > 
   > [!NOTE]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建包含在生成架构时指定的绑定属性的绑定文件 （XML 文件） 的操作和要调用该操作的 SOAP 操作。 可以在 BizTalk Server 管理控制台创建 WCF 自定义端口的连接 URI，绑定属性与此绑定文件导入和 SOAP 操作集。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。  
  
6. 在“文件”  菜单上，单击“全部保存” 。  
  
## <a name="generating-a-wcf-client-for-idoc-operations-using-the-add-adapter-service-reference-plug-in"></a>生成 IDOC 操作使用的 WCF 客户端添加适配器服务引用插件  
 可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端代码发送到 SAP 系统的 Idoc，还是 WCF 服务协定以接收来自 SAP 系统的 Idoc。  
  
#### <a name="to-generate-a-wcf-client-or-a-wcf-service-contract-for-idocs"></a>为 Idoc 生成 WCF 客户端或 WCF 服务约定  
  
1. 在中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从**选择协定类型**下拉列表中，选择基于是否将执行入站 (接收 Idoc) 或出站 （发送 Idoc） 操作的协定的类型。  
  
2. 在中**选择一个类别**框中，展开**IDOC**节点，然后浏览或搜索 IDOC 消息类型或你想要发送或接收 IDOC 类型。  
  
3. 在中**可用类别和操作**框中，选择 IDOC 类型或支持的操作，你想要生成 WCF 客户端 （或 WCF 服务约定），然后单击**添加**。 所选的操作所示**添加的类别和操作**框。 可以选择中列出的任何节点**可用类别和操作**框。 如果您选择的类别节点，则只提供该节点下的操作，并且将添加及其子节点。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]为每个 IDOC 类型生成一个唯一的 WCF 客户端类 （或 WCF 服务约定）。 根据类别和你选择的操作，可能会生成多个 WCF 客户端类。 有关详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目的 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
4. 在大多数情况下的默认序列化选项是不够的;但是，如果需要可以控制生成的代码有关的几个方面和序列化程序使用的类型。 若要设置这些选项：  
  
   1. 单击**高级选项**以打开**高级选项**框。  
  
   2. 在中**高级选项**框下**选择生成的代理的选项**，选择所需的选项。 例如，可以选择是否异步方法生成 WCF 客户端或禁用配置文件的生成。  
  
   3. 下**序列化程序**选择应使用的序列化程序。  
  
      下图显示**高级选项**具有默认选择框 (**自动**处于选中状态的选择序列化程序和任何其他选项)。  
  
      ![高级选项框默认设置](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      可以在中配置的选项**高级选项**使用 ServiceModel Metadata Utility Tool (svcutil.exe) 时，框将等效于一些可用的选项。 有关这些选项的详细信息，请参阅[ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。
  
5. 单击“确定” 。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]保存 WCF 客户端类 （或 WCF 服务接口） 和帮助程序代码的操作和已选择在项目目录中的类别。 默认情况下，还保存配置文件。 为入站和出站操作; 生成略有不同的文件有关详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目的 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中获取 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)