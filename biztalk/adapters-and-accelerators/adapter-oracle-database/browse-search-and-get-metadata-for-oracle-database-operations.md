---
title: "浏览、 搜索和为 Oracle 数据库操作获取元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF client, generating a
- operations, browsing for
- metadata, browsing
- browse, for operations
- schema, generating
- metadata, retrieving
- browse, metadata
- retrieve, metadata
- operations, searching for
- WCF service contract, generating a
- metadata, browsing, searching, and retrieving
ms.assetid: 65bd59e0-771d-40fe-966c-8cc8a629ce47
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8735040dd1cad2df59e18dbb572dad322ec46fcf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-metadata-for-oracle-database-operations"></a>浏览、 搜索和为 Oracle 数据库操作获取元数据
本部分提供有关如何使用信息[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 通过使用这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件，你可以：  
  
-   浏览要为其检索元数据的操作。  
  
-   搜索为其检索元数据的操作。  
  
-   添加所选操作的消息架构和端口绑定配置文件添加到 BizTalk 服务器项目时使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
-   WCF 客户端类或所选的操作和配置文件 (app.config) 的 WCF 服务协定 （接口） 向项目中添加非 BizTalk 编程时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
 你可以浏览、 搜索，或检索元数据的目标操作之前，你必须连接到 Oracle 数据库。 有关如何连接到 Oracle 数据库使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[连接到 Visual Studio 中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)。  
  
> [!NOTE]
>  -   [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]当您浏览和搜索操作，因此相同的主题中所述的所有三个组件时所显示实质上是相同的接口。  
> -   可以选择要在该类别的子树中返回的所有操作的类别节点-例如，为整个表或架构 （或甚至所有表架构中的）。  
  
## <a name="browsing-for-operations"></a>浏览操作  
 浏览元数据中使用的同时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]曲面：  
  
-   可以对表、 视图、 存储的过程、 函数和包执行的操作。  
  
-   SQLEXECUTE 操作，从而使适配器客户端要在 Oracle 数据库中执行任何一般数据操作语言 (DML) 或存储的过程。  
  
-   POLLINGSTMT 和通知操作，这样使适配器客户端，以获取从 Oracle 数据库的入站的数据。 它还使存储的过程、 函数和下公开作为操作进行轮询的相应架构的包的列表。  
  
> [!NOTE]
>  -   通过使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，你可以浏览类别和操作节点上使用 Windows 界面。  
> -   直接在类别树中的根节点下显示 SQLEXECUTE、 POLLINGSTMT 和通知操作。 必须选择要查看这些出站和入站操作的根节点。  
  
 有关浏览元数据的详细信息，请参阅[为 Visual Studio 中的 Oracle 数据库操作获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)  
  
 执行以下步骤以浏览公开在 Oracle 数据库中使用的不同项目的操作[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
#### <a name="to-browse-metadata-in-an-oracle-database"></a>若要浏览 Oracle 数据库中的元数据  
  
1.  连接到 Oracle 数据库使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**下拉列表中，选择基于你将可执行使用适配器的入站或出站操作的协定的类型。  
  
3.  **选择类别**框中列出的 Oracle 数据库中的架构。 单击以查看表、 过程、 函数、 包和视图中的架构可以访问的架构**可用类别和操作**框。 另外，还可以通过展开架构节点看到分类。  
  
    > [!TIP]
    >  你可以直接转到"即时"类别节点或子类别节点在树中，通过键入中项目的名称上时将焦点的树视图中**选择类别**框。 例如，若要跳转到**SCOTT**节点，关注根节点，然后键入`SCOTT`。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 在选定 SCOTT 架构节点，和中列出了可用 SCOTT 节点下的常规类别节点**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的用户](../../adapters-and-accelerators/adapter-oracle-database/media/c6e02d12-278b-4419-8c8d-d12d0d64f325.gif "c6e02d12-278b-4419-8c8d-d12d0d64f325")  
  
4.  单击**表**节点以查看有关 SCOTT 中的表**可用类别和操作**框。 另外，还可以通过展开看到表的列表**表**节点。  
  
5.  单击某个表名称以查看表支持的操作。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 可以在 SCOTT 架构中的表中列出**选择类别**框。 中列出了 EMP 表可执行的操作**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的表](../../adapters-and-accelerators/adapter-oracle-database/media/6df61a2f-3cd9-486c-9bf5-7968f8f1ce8d.gif "6df61a2f-3cd9-486c-9bf5-7968f8f1ce8d")  
  
6.  单击**过程**节点列出架构 SCOTT 可以访问的过程中**可用类别和操作**框。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 中列出了可用 SCOTT 架构中的常规类别节点**选择类别**框。 可以在 SCOTT 架构中的过程中列出**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-database/media/9826e160-5295-4fdc-bd82-ccd456d89242.gif "9826e160-5295-4fdc-bd82-ccd456d89242")  
  
7.  单击**函数**节点可查看架构 SCOTT 函数中**可用类别和操作**框。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 中列出了可用 SCOTT 架构中的常规类别节点**选择类别**框。 SCOTT 架构中的可用功能中列出**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的函数](../../adapters-and-accelerators/adapter-oracle-database/media/ae02731e-7f26-4552-8e40-db797885af01.gif "ae02731e-7f26-4552-8e40-db797885af01")  
  
8.  单击**包**节点查看架构 SCOTT 包中**可用类别和操作**框。 另外，还可以通过展开中看到的包列表**包**节点。  
  
9. 单击某个包名称以查看包上支持的操作。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了包及对于特定的包，SCOTT 架构支持的操作。  
  
     ![浏览 Oracle 数据库中的包](../../adapters-and-accelerators/adapter-oracle-database/media/bts-r2-net-adapter-oracle-tut1-browse-pckgs.gif "bts_R2_NET_Adapter_Oracle_Tut1_Browse_Pckgs")  
  
10. 单击**视图**节点可查看架构 SCOTT 的视图中**可用类别和操作**框。 另外，还可以看到通过展开的视图的列表**视图**节点。  
  
11. 单击某个视图名称以查看视图上支持的操作。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了在视图中和特定的视图中，SCOTT 架构支持的操作。  
  
     ![浏览 Oracle 数据库中的视图](../../adapters-and-accelerators/adapter-oracle-database/media/cc1079bc-c1ca-4c2b-a291-abf87bf1ac4d.gif "cc1079bc-c1ca-4c2b-a291-abf87bf1ac4d")  
  
    > [!NOTE]
    >  使用 WCF 通道和服务模型，适配器客户端可以指定大批大小，以执行批量检索的元数据。  
  
## <a name="searching-for-operations"></a>搜索操作  
 当搜索元数据中使用 Oracle 时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
-   在搜索表达式中支持通配符和转义字符。  
  
-   立即在从该处执行搜索操作的节点下启用搜索。 例如，若要搜索的函数，您必须搜索下\\[架构] \Functions。 不支持多级搜索。  
  
 下表列出了可以用于搜索和其解释的特殊字符[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|_（下划线）|完全匹配一个字符<br /><br /> 例如，A_ 匹配 AB、 AC、 AD。|  
|%（百分比）|匹配零个或多个字符。<br /><br /> 例如，%匹配 A，AB，ABC。|  
|\ （转义）|转义的特殊含义的 %和 _<br /><br /> 例如，A\\_B 匹配 A_B。|  
  
> [!NOTE]
>  转义符是放置在要指示为常规字符而不是通配符，应解释通配符的通配符字符之前的字符。  
  
 有关详细信息请参阅[为 Visual Studio 中的 Oracle 数据库操作获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)  
  
#### <a name="to-search-metadata-in-an-oracle-database"></a>若要在 Oracle 数据库中搜索元数据  
  
1.  连接到 Oracle 数据库使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)有关的说明。  
  
2.  在[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，从**选择协定类型**下拉列表中，选择根据你是否将搜索的入站或出站使用适配器的操作的协定的类型。  
  
3.  在**选择类别**框中，单击包含表、 过程、 函数、 包和您想要搜索的视图的架构。 如果不确定单击的架构，请单击根节点。  
  
4.  在**类别中的搜索**文本框中，输入要搜索特定的架构的搜索表达式。 例如，若要搜索其名称中包含"SC"的架构，请键入**%SC%**在文本框中。  
  
5.  单击与右箭头图标以开始搜索按钮。 完成搜索后**可用类别和操作**框中列出的满足搜索条件的架构。  
  
6.  在**选择类别**框中，到架构中，展开相对应的节点，然后再单击数据库项目，您想要在中搜索。 在**类别中的搜索**文本框中，输入要搜索的特定数据库项的搜索表达式。  
  
     例如，若要搜索其名称中有"EMP"的表，选择**表**，类型**%EMP%**中**类别中的搜索**文本中，，然后单击与按钮右箭头图标。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了搜索结果。  
  
     ![在 Oracle 数据库中搜索元数据](../../adapters-and-accelerators/adapter-oracle-database/media/1ee912f8-896e-4b45-ba98-1bbd36b56574.gif "1ee912f8-896e-4b45-ba98-1bbd36b56574")  
  
    > [!NOTE]
    >  使用 WCF 通道和服务模型，适配器客户端可以指定批大小执行 batch-wise 搜索的元数据。  
  
## <a name="generating-schema-using-the-consume-adapter-service-add-in-or-add-adapter-metadata-wizard"></a>生成架构使用使用适配器服务外接程序或添加适配器元数据向导  
 你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成为选择的 Oracle 数据库项目的架构。 浏览并搜索你想要调用的项目后，你可以生成这些项目的架构和发送消息，符合架构，到 Oracle 数据库。 执行以下步骤来检索元数据从 Oracle 数据库使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
> [!NOTE]
>  你可以选择要在该类别的子树中返回的所有操作的类别节点-例如，你可以选择整个表 （以生成表中的所有操作的架构） 或表 （例如，Insert 和 Delete） 选择特定的操作生成对表的这些操作的架构。 有关节点的详细信息，请参阅[元数据节点 IDs3](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)。  
  
#### <a name="to-retrieve-metadata-from-an-oracle-database"></a>若要从 Oracle 数据库中检索元数据  
  
1.  连接到 Oracle 数据库使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 请参阅[连接到 Visual Studio 中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**下拉列表中，选择基于你将可执行使用适配器的入站或出站操作的协定的类型。  
  
3.  在**选择类别**框中，展开架构节点。  
  
4.  选择你想要生成元数据的类别。 例如，如果你想要生成表元数据，则选择**表**。  
  
5.  展开该特定类别节点，然后选择你想要生成元数据节点中的特定项。  
  
     例如，若要生成为特定表的元数据，请展开**表**节点，然后选择特定的表名称。  
  
    > [!NOTE]
    >  如前面的过程中所述，还可以搜索的特定数据库项目。  
  
6.  在**可用类别和操作**框中，选择适用于你在前一步骤中选择的数据库项的操作，然后单击**添加**。 中列出了所选的操作**添加类别和操作**框。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了所选的操作。  
  
     ![从 Oracle 数据库中检索元数据](../../adapters-and-accelerators/adapter-oracle-database/media/d3950566-8720-4c15-8a16-4ade14bf6221.gif "d3950566-8720-4c15-8a16-4ade14bf6221")  
  
     如果你想要为多个操作生成架构，可能有一些重复的元素定义之间可能会导致失败编译 BizTalk 项目这些架构。 例如，考虑其中生成操作"Op1"的架构的方案。 "Op1"的架构包含复杂数据类型"CT1"的参数。 为"Op1"生成架构后，你关闭[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]然后重新打开它以生成用于另一操作"Op2"的架构。 假定"Op2"还包含复杂数据类型"CT1"的参数。 退出后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和编译该项目，你将收到编译错误，因为两次在不同的 XSD 文件中定义的复杂数据类型"CT1"。 在这种情况下，我们的建议如下：  
  
    -   中的一次运行生成的所有操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 这样可确保[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成只有一个定义的复杂数据类型"CT1"。  
  
    -   如果你想要跨不同运行的生成对多个操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请确保选择**生成唯一的架构类型**复选框，以便生成的 XSD 文件包含对复杂的唯一命名空间数据类型"CT1"。  
  
7.  单击 **“确定”**。 架构文件保存带.xsd 扩展名为 BizTalk 项目所在的位置。  
  
     默认情况下，文件使用的命名约定创建"OracleDBBindingSchema\<n >.xsd"，其中 n 可以是 1、 2 和等等，具体取决于架构创建的文件数。 或者，您可以通过输入中的名称提供自定义名称的架构文件到**文件名前缀**文本框。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]现在使用的命名约定创建架构文件\<文件名前缀 > 架构\<n >.xsd。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建包含时指定的绑定属性的绑定文件 （XML 文件） 生成某一操作和要调用的操作的 SOAP 操作的架构。 你可以导入在 BizTalk Server 管理控制台中创建 WCF 自定义端口连接 URI，绑定属性与此绑定文件和设置的 SOAP 操作。 有关详细信息，请参阅[配置使用端口绑定文件到 Oracle 数据库的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
    > [!IMPORTANT]
    >  使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]不会生成绑定文件。  
  
8.  在“文件”  菜单上，单击“全部保存” 。  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>生成 WCF 客户端或 WCF 服务协定使用添加插件的适配器服务引用  
 你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端代码用于出站操作，或者为入站操作的 WCF 服务代码。  
  
#### <a name="to-retrieve-metadata-from-an-oracle-database"></a>若要从 Oracle 数据库中检索元数据  
  
1.  在[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从**选择协定类型**下拉列表中，选择基于是否你将执行入站 (POLLINGSTMT) 或出站操作的协定的类型。  
  
2.  浏览或搜索的类别 （例如，Oracle 数据库表） 或者你想要生成 WCF 客户端 （或 WCF 服务协定） 的特定操作。   
    例如，若要浏览 SCOTT 中的操作。EMP 表**选择类别**框：  
  
    1.  展开根节点 (**/**) 若要查看针对 Oracle 数据库显示架构。  
  
    2.  在根节点下展开**SCOTT**节点以查看公开 for SCOTT 架构的类别。  
  
    3.  下**SCOTT**节点，展开**表**节点以查看的表中加以表示为 SCOTT 架构。  
  
    4.  下**表**节点，请选择**EMP**节点。 中列出了为 EMP 表中加以表示的操作**可用类别和操作**框。  
  
3.  在**可用类别和操作**框中，选择的操作或您要为其生成 WCF 客户端 （或 WCF 服务约定），然后单击的类别**添加**。 中列出了所选的操作**添加类别和操作**框。  
  
     下图显示[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]与 SCOTT 的 Insert 和 Update 操作。EMP 选择表。  
  
     ![选择选择和更新操作。] (../../adapters-and-accelerators/adapter-oracle-database/media/4c41ac7b-784a-494c-ac82-c007e22a4fdf.gif "4c41ac7b-784a-494c-ac82-c007e22a4fdf")  
  
    > [!IMPORTANT]
    >  具体取决于的出站操作 （或类别），您选择，超过一个 WCF 客户端类可能会生成。 有关更多详细信息，请参阅[生成 WCF 客户端或 Oracle 数据库解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
4.  在大多数情况下的默认序列化选项已足够;但是，如果需要你可以控制生成的代码有关的几个方面和序列化程序使用的类型。 若要设置这些选项：  
  
    1.  单击**高级选项**以打开**高级选项**框。  
  
    2.  在**高级选项**下框中**选择生成的代理的选项**，选择所需的选项。 例如，你可以选择是否为 WCF 客户端生成异步方法，或禁用配置文件的生成。  
  
    3.  下**序列化程序**选择应使用的序列化程序。  
  
     下图显示**高级选项**包装盒默认选择 (**自动**选择为所选序列化程序和任何其他选项)。  
  
     ![高级选项框中的默认设置](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     你可以在配置的选项**高级选项**使用 ServiceModel 元数据实用工具 (svcutil.exe) 时，框将等效于某些可用的选项。 有关这些选项的详细信息，请参阅[ServiceModel 元数据实用工具 (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。
  
5.  单击 **“确定”**。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将保存的 WCF 客户端类 （或 WCF 服务接口） 和帮助器代码的操作和你选择了你的项目目录中的类别。 默认情况下，也保存配置文件。 为入站和出站操作; 生成略有不同的文件有关详细信息，请参阅[生成 WCF 客户端或 Oracle 数据库解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
 你可以选择中列出的任何节点**可用类别和操作**框。 如果你选择的类别节点，则该节点及其子节点下可执行的操作的所有将被选中。 例如，若要生成的所有操作 EMP 表中加以表示的 WCF 客户端，也可以选择 EMP 节点中;若要在 SCOTT 架构中生成 WCF 客户端的所有表，也可以选择表节点中;等等。  
  
## <a name="see-also"></a>另请参阅  
[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)