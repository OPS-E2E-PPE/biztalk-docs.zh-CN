---
title: 浏览、 搜索和获取 Siebel 操作的元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving
- how to, browse metadata
- how to, retrieve metadata
- retrieving, metadata
- metadata, browsing
- browsing, metadata
- metadata, searching
- how to, seach metadata
- searching, metadata
ms.assetid: 7e474d8e-b030-47ea-b1b6-8048cddbba8a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a5edfbf9a5f1433721b3ce11a63d38aa259a4c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371967"
---
# <a name="browse-search-and-get-metadata-for-siebel-operations"></a>浏览、 搜索和获取 Siebel 操作的元数据
本部分提供有关如何使用信息[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 通过使用这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件，你可以：  
  
- 浏览查找要为其检索元数据的操作。  
  
- 搜索要为其检索元数据的操作。  
  
- 添加所选操作的消息架构和端口绑定的配置文件来[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目时使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
- 将 WCF 客户端类或所选的操作和配置文件 (app.config) 的 WCF 服务协定 （接口） 添加到非 BizTalk 编程项目时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]时浏览和搜索操作，因此同样的主题中介绍了所有三个组件显示实质上是相同的接口。  
  
## <a name="prerequisites"></a>先决条件  
 可以浏览、 搜索，或检索元数据的目标操作之前，必须连接到 Siebel 系统。 有关如何使用时，连接到 Siebel 系统的信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[连接到 Visual Studio 中的 Siebel 系统](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)。  
  
## <a name="browsing-metadata"></a>浏览元数据  
 浏览元数据中使用的同时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，则[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]图面：  
  
-   可以如 Siebel 业务组件执行的操作的插入、 查询、 更新和删除。  
  
-   可以通过适配器客户端调用的业务服务方法。  
  
> [!NOTE]
>  通过使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，可以浏览类别和操作节点使用 Windows 界面。  
  
 有关浏览 Siebel 元数据的详细信息，请参阅[浏览、 搜索和获取 Siebel 元数据](../../adapters-and-accelerators/adapter-siebel/browse-search-and-get-siebel-metadata.md) 
  
 执行以下步骤浏览 Siebel 系统使用的元数据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-browse-metadata-in-a-siebel-system"></a>若要在 Siebel 系统中浏览元数据  
  
1. 连接到 Siebel 系统中使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 Siebel 系统](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**下拉列表中，选择基于是否将执行使用该适配器的入站或出站操作的协定的类型。  
  
3. **选择一个类别**框列出了**业务对象**并**业务服务**节点。 单击**业务对象**节点以查看一系列中的业务对象**可用类别和操作**框。 或者，可以通过展开看到的业务对象的列表**业务对象**节点。  
  
   > [!TIP]
   >  您可以直接转到"即时"类别节点或子类别节点在树中，通过键入中项目的名称的树视图中聚焦时**选择一个类别**框。 例如，若要跳转到**帐户**业务对象，重点介绍**业务对象**节点，并键入`Account`。  
  
4. 单击要查看特定的业务对象的业务组件的列表的业务对象。 或者，您所见业务组件的列表展开的业务对象。  
  
5. 单击业务组件，若要查看支持的特定业务组件操作的列表。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了业务对象、 业务组件和支持的操作。  
  
    ![浏览 Siebel 业务组件](../../adapters-and-accelerators/adapter-siebel/media/11c63383-4269-4ba0-909b-e2cbec7eae04.gif "11c63383-4269-4ba0-909b-e2cbec7eae04")  
  
6. 单击**业务服务**节点以查看一系列中的业务服务**可用类别和操作**框。 或者，可以通过展开看到表的列表**业务服务**节点。  
  
7. 单击业务服务以查看相应的业务服务方法的列表。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了业务服务和相应的业务服务方法。  
  
    ![浏览 Siebel 业务服务](../../adapters-and-accelerators/adapter-siebel/media/60405c18-6035-42a5-851f-a0ed6d0570d6.gif "60405c18-6035-42a5-851f-a0ed6d0570d6")  
  
## <a name="searching-metadata"></a>搜索元数据  
 搜索 Siebel 元数据中使用时[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]:  
  
- 支持通配符和转义字符。  
  
- 可以立即执行搜索操作的间隔的节点下的搜索。 例如，若要搜索的业务服务，您必须搜索 \Business 服务下。  
  
  下表列出了可用于搜索和通过其解释的特殊字符[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|? （问号）|只匹配一个字符<br /><br /> 例如，一个？匹配 AB、 AC、 AD。|  
|*（星号）|匹配零个或多个字符。<br /><br /> 例如，A * A，AB，ABC 匹配。|  
  
 执行以下步骤，若要在 Siebel 系统中使用搜索元数据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-search-metadata-in-a-siebel-system"></a>若要在 Siebel 系统中搜索元数据  
  
1. 连接到 Siebel 系统中使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 Siebel 系统](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**下拉列表中，选择**客户端 （出站操作）** 协定。  
  
3. 在中**选择一个类别**框中，单击**业务对象**节点。  
  
4. 若要搜索特定的业务对象，请单击**业务对象**中的节点**类别中的搜索**文本输入的搜索表达式。 例如，若要搜索的业务对象的名称开头"帐户"，键入**帐户\\*** 在文本框中。  
  
5. 单击开始搜索的向右箭头图标按钮。 搜索完成后**可用类别和操作**框列出了满足搜索条件的业务对象。  
  
6. 若要搜索的特定业务组件在业务对象中，单击一个业务对象和在**类别中的搜索**文本框中输入的搜索表达式。 例如，若要搜索的业务组件的名称开头"帐户"，键入**帐户\\*** 在文本框中。  
  
7. 单击开始搜索的向右箭头图标按钮。 搜索完成后**可用类别和操作**框中列出的业务组件满足搜索条件。  
  
8. 若要搜索特定的业务组件操作，请单击业务组件并在**类别中的搜索**文本框中输入的搜索表达式。 例如，若要搜索的操作具有以"查询"开头的名称，请键入**查询\\*** 在文本框中。  
  
9. 单击开始搜索的向右箭头图标按钮。 搜索完成后**可用类别和操作**框中列出的业务组件满足搜索条件。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了在搜索结果。  
  
     ![搜索业务组件](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-04-search.gif "SIEBEL-ADPT-Lesson1-Step3-04-search")  
  
     执行类似的过程来搜索下**业务服务**节点。  
  
## <a name="generating-schema-for-biztalk-projects"></a>对于 BizTalk 项目中生成架构  
 可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成所选 Siebel 项目的架构。 浏览并搜索你想要调用的项目后，您可以生成的项目的架构和发送消息，符合架构，到 Siebel。  
  
> [!NOTE]
>  可以选择要在该类别的子树中返回的所有操作的类别节点，例如，可以选择在业务组件 （以业务组件中产生的所有操作的架构） 或 （对于在业务组件上选择特定的操作示例中，Insert 和 Delete） 若要为操作生成架构。 有关节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。  
  
#### <a name="to-generate-schema-for-siebel-artifacts"></a>若要为 Siebel 项目生成架构  
  
1. 连接到 Siebel 系统中使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 请参阅[连接到 Visual Studio 中的 Siebel 系统](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**下拉列表中，选择**客户端 （出站操作）** 协定。  
  
3. 在中**选择一个类别**框中，展开业务对象或业务服务节点。  
  
4. 在中**可用类别和操作**框中，选择业务组件或业务服务或相应的操作要为其生成元数据，然后单击**添加**。 中列出的所选功能区域或操作**添加的类别和操作**框。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了所选的操作。  
  
    ![检索业务对象的元数据](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-05-get.gif "SIEBEL-ADPT-Lesson1-Step3-05-get")  
  
    如果你想要为多个操作生成架构，可能有一些重复的元素定义由这些架构会导致在编译 BizTalk 项目中的问题。 例如，假设其中生成操作"Op1"的架构。 "Op1"的架构包含复杂数据类型"CT1"的参数。 对于"Op1"生成架构后关闭[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]并重新打开它以生成架构的另一项操作"Op2"。 假定"Op2"还包含复杂数据类型"CT1"的参数。 退出后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和编译项目，你将收到编译错误，因为两次在不同的 XSD 文件中定义的复杂数据类型"CT1"。 在这种情况下，我们建议：  
  
   - 生成的所有操作的架构中的一次运行[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 这可确保[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成复杂的数据类型"CT1"只有一个定义。  
  
   - 如果你想要在不同的运行中生成多个操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请确保选择**生成唯一的架构类型**复选框，以便生成的 XSD 文件包含复杂的唯一命名空间数据类型"CT1"。  
  
5. 单击“确定” 。 架构文件保存具有.xsd 扩展名为 BizTalk 项目所在的位置。  
  
    默认情况下，文件使用的命名约定创建"SiebelBindingSchema\<n\>.xsd"，其中 n 可以是 1、 2 和等等，具体取决于创建的架构文件数量。 或者，可以通过输入一个名称中的提供的架构文件的自定义名称**文件名前缀**文本框。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]现在使用的命名约定创建架构文件\<文件名前缀\>架构\<n\>.xsd。  
  
   > [!NOTE]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建包含时指定的绑定属性的绑定文件 （XML 文件） 生成的架构操作以及要调用该操作的 SOAP 操作。 可以在 BizTalk Server 管理控制台创建 WCF 自定义端口的连接 URI，绑定属性与此绑定文件导入和 SOAP 操作集。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件到 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。  
  
6. 在“文件”  菜单上，单击“全部保存” 。  
  
## <a name="generating-a-wcf-client-using-the-add-adapter-service-reference-plug-in"></a>生成 WCF 客户端使用添加适配器服务引用插件  
 可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端代码的 Siebel 系统的出站操作。  
  
#### <a name="to-generate-a-wcf-client"></a>若要生成 WCF 客户端  
  
1. 在中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从**选择协定类型**下拉列表中，选择**客户端 （出站操作）**。  
  
2. 在中**选择一个类别**框中，展开业务对象或业务服务节点。  
  
3. 在中**可用类别和操作**框中，选择业务组件、 业务服务或要为其生成 WCF 客户端，然后单击相应的操作**添加**。 中列出的所选功能区域或操作**添加的类别和操作**框。 可以选择中列出的任何节点**可用类别和操作**框。 如果选择的类别节点，则将选择所有可用的节点及其子节点下的操作。  
  
   > [!IMPORTANT]
   >  根据类别和你选择的操作，可能会生成多个 WCF 客户端类。 有关详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)。  
  
4. 在大多数情况下的默认序列化选项是不够的;但是，如果需要可以控制生成的代码有关的几个方面和序列化程序使用的类型。 若要设置这些选项：  
  
   1. 若要打开**高级选项**框中，单击**高级选项**。  
  
   2. 在中**高级选项**框下**选择生成的代理的选项**，选择所需的选项。 例如，可以选择是否为 WCF 客户端，则会生成异步方法也可以禁用配置文件的生成。  
  
   3. 下**序列化程序**，选择应使用的序列化程序。  
  
      下图显示**高级选项**具有默认选择框 (**自动**处于选中状态的选择序列化程序和任何其他选项)。  
  
      ![高级选项框默认设置](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      可以在中配置的选项**高级选项**使用 ServiceModel Metadata Utility Tool (svcutil.exe) 时，框将等效于一些可用的选项。 有关这些选项的详细信息，请参阅[ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。
  
5. 单击“确定” 。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]保存 WCF 客户端操作和已选择在项目目录中的类别的类和帮助程序代码。 默认情况下，还保存配置文件。 有关详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中获取 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)