---
title: 浏览、 搜索和获取 Oracle 数据库操作的元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e761e81e4f0aaee56611a13e9c84e78056f4da0c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529627"
---
# <a name="browse-search-and-get-metadata-for-oracle-database-operations"></a>浏览、 搜索和获取 Oracle 数据库操作的元数据
本部分提供有关如何使用信息[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 通过使用这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件，你可以：  
  
- 浏览查找要为其检索元数据的操作。  
  
- 搜索要为其检索元数据的操作。  
  
- 添加所选操作的消息架构和端口绑定到 BizTalk server 项目的配置文件时使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
- 将 WCF 客户端类或所选的操作和配置文件 (app.config) 的 WCF 服务协定 （接口） 添加到非 BizTalk 编程项目时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
  可以浏览、 搜索，或检索元数据的目标操作之前，必须连接到 Oracle 数据库。 有关如何连接到 Oracle 数据库的信息时则使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[连接到 Visual Studio 中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)。  
  
> [!NOTE]
> - [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]时浏览和搜索操作，因此同样的主题中介绍了所有三个组件显示实质上是相同的接口。  
>   -   可以选择要返回该类别的子树中的所有操作的类别节点，例如，整个表或架构 （或甚至所有架构的表）。  
  
## <a name="browsing-for-operations"></a>浏览操作  
 浏览元数据中使用的同时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，则[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面：  
  
-   可以对表、 视图、 存储的过程、 函数和包执行的操作。  
  
-   SQLEXECUTE 操作，这使适配器客户端能够在 Oracle 数据库中执行任何泛型数据操作语言 (DML) 或存储的过程。  
  
-   POLLINGSTMT 和通知操作，这使适配器客户端能够从 Oracle 数据库中获取入站的数据。 它还公开存储的过程、 函数和作为用于轮询的操作公开的相应架构下的包的列表。  
  
> [!NOTE]
> - 通过使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，可以浏览类别和操作节点使用 Windows 界面。  
>   -   SQLEXECUTE、 POLLINGSTMT 和通知操作直接呈现中的类别树的根节点。 必须选择要查看这些出站和入站操作的根节点。  
  
 有关浏览元数据的详细信息，请参阅[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)  
  
 执行以下步骤浏览到的 Oracle 数据库使用的不同产物公开的操作[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
#### <a name="to-browse-metadata-in-an-oracle-database"></a>若要浏览 Oracle 数据库中的元数据  
  
1. 连接到 Oracle 数据库使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**下拉列表中，选择基于是否将执行使用该适配器的入站或出站操作的协定的类型。  
  
3. **选择一个类别**框中列出的 Oracle 数据库中的架构。 单击以查看表、 过程、 函数、 包和视图中的架构可访问的架构**可用类别和操作**框。 或者，您可以通过展开 schema 节点中看到分类。  
  
   > [!TIP]
   >  您可以直接转到"即时"类别节点或子类别节点在树中，通过键入中项目的名称的树视图中聚焦时**选择一个类别**框。 例如，若要跳转到**SCOTT**节点，将重点始终放在根节点，然后键入`SCOTT`。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 选择 SCOTT schema 节点，并且可用 SCOTT 节点下的常规类别节点中列出**可用类别和操作**框。  
  
    ![浏览 Oracle 数据库中的用户](../../adapters-and-accelerators/adapter-oracle-database/media/c6e02d12-278b-4419-8c8d-d12d0d64f325.gif "c6e02d12-278b-4419-8c8d-d12d0d64f325")  
  
4. 单击**表**节点以查看的表为中 SCOTT**可用类别和操作**框。 或者，可以通过展开看到表的列表**表**节点。  
  
5. 单击表名以查看表支持的操作。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 SCOTT 架构中可用的表中列出**选择一个类别**框。 中列出了可对 EMP 表的操作**可用类别和操作**框。  
  
    ![浏览 Oracle 数据库中的表](../../adapters-and-accelerators/adapter-oracle-database/media/6df61a2f-3cd9-486c-9bf5-7968f8f1ce8d.gif "6df61a2f-3cd9-486c-9bf5-7968f8f1ce8d")  
  
6. 单击**过程**节点以列出架构 SCOTT 可以访问的过程中**可用类别和操作**框。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 SCOTT 架构中的常规类别节点中列出**选择一个类别**框。 SCOTT 架构中提供的过程中列出**可用类别和操作**框。  
  
    ![浏览 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-database/media/9826e160-5295-4fdc-bd82-ccd456d89242.gif "9826e160-5295-4fdc-bd82-ccd456d89242")  
  
7. 单击**函数**节点以查看架构 SCOTT 的函数中**可用类别和操作**框。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 SCOTT 架构中的常规类别节点中列出**选择一个类别**框。 SCOTT 架构中可用的函数所示**可用类别和操作**框。  
  
    ![浏览 Oracle 数据库中的函数](../../adapters-and-accelerators/adapter-oracle-database/media/ae02731e-7f26-4552-8e40-db797885af01.gif "ae02731e-7f26-4552-8e40-db797885af01")  
  
8. 单击**包**节点以查看架构 SCOTT 的包中**可用类别和操作**框。 或者，可以通过展开看到的包列表**包**节点。  
  
9. 单击包名称，若要查看支持包上的操作。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了包和特定包，为 SCOTT 架构支持的操作。  
  
     ![浏览 Oracle 数据库中的软件包](../../adapters-and-accelerators/adapter-oracle-database/media/bts-r2-net-adapter-oracle-tut1-browse-pckgs.gif "bts_R2_NET_Adapter_Oracle_Tut1_Browse_Pckgs")  
  
10. 单击**视图**节点以查看 SCOTT 的架构的视图中**可用类别和操作**框。 或者，可以通过展开看到视图的列表**视图**节点。  
  
11. 单击视图名称，若要查看支持在视图上的操作。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了视图，并为特定视图中，SCOTT 架构支持的操作。  
  
     ![浏览 Oracle 数据库中的视图](../../adapters-and-accelerators/adapter-oracle-database/media/cc1079bc-c1ca-4c2b-a291-abf87bf1ac4d.gif "cc1079bc-c1ca-4c2b-a291-abf87bf1ac4d")  
  
    > [!NOTE]
    >  使用 WCF 通道和服务模型，适配器客户端可以指定批大小，以执行批量检索的元数据。  
  
## <a name="searching-for-operations"></a>搜索操作  
 搜索 Oracle 元数据中使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，则[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
- 搜索表达式中支持通配符和转义字符。  
  
- 可以立即执行搜索操作的间隔的节点下的搜索。 例如，若要搜索一个函数，您必须搜索下\\[Schema] \Functions。 不支持多级别的搜索。  
  
  下表列出了可用于搜索和通过其解释的特殊字符[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|_（下划线）|只匹配一个字符<br /><br /> 例如，A_ 匹配 AB，交流，AD。|  
|%（百分比）|匹配零个或多个字符。<br /><br /> 例如，%匹配一个，AB，ABC。|  
|\ （转义）|转义的特殊含义的 %和 _<br /><br /> 例如，一个\\_B 匹配 A_B。|  
  
> [!NOTE]
>  转义符是放置在通配符字符以指示通配符应当解释为常规字符而不是通配符之前的字符。  
  
 有关详细信息请参阅[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)  
  
#### <a name="to-search-metadata-in-an-oracle-database"></a>若要在 Oracle 数据库中搜索元数据  
  
1. 连接到 Oracle 数据库使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)有关的说明。  
  
2. 在中[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，从**选择协定类型**下拉列表中，选择根据你是否将搜索使用的适配器的入站或出站操作的协定的类型。  
  
3. 在中**选择一个类别**框中，单击包含表、 过程、 函数、 包和要搜索的视图的架构。 如果不确定要单击的架构，请单击根节点。  
  
4. 在中**类别中的搜索**文字框中，输入要搜索的特定架构的搜索表达式。 例如，若要搜索其名称中包含"SC"的架构，请键入 **%SC%** 在文本框中。  
  
5. 单击开始搜索的向右箭头图标按钮。 搜索完成后**可用类别和操作**框列出了满足搜索条件的架构。  
  
6. 在中**选择一个类别**框中，为架构中，展开相对应的节点，然后和单击数据库项目中，您想要在其中搜索。 在中**类别中的搜索**文字框中，输入要搜索特定的数据库项的搜索表达式。  
  
    例如，若要搜索名称中含有"EMP"表，请选择**表**，类型 **%EMP%** 中**类别中的搜索**文本框，并单击与按钮向右箭头图标。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了在搜索结果。  
  
    ![搜索 Oracle 数据库中的元数据](../../adapters-and-accelerators/adapter-oracle-database/media/1ee912f8-896e-4b45-ba98-1bbd36b56574.gif "1ee912f8-896e-4b45-ba98-1bbd36b56574")  
  
   > [!NOTE]
   >  使用 WCF 通道和服务模型，适配器客户端可以指定批大小执行 batch-wise 搜索的元数据。  
  
## <a name="generating-schema-using-the-consume-adapter-service-add-in-or-add-adapter-metadata-wizard"></a>生成架构使用使用适配器服务外接程序或添加适配器元数据向导  
 可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成所选 Oracle 数据库项目的架构。 浏览并搜索你想要调用的项目后，您可以生成的项目的架构和发送消息，符合架构的 Oracle 数据库。 执行以下步骤来检索元数据从 Oracle 数据库使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
> [!NOTE]
>  可以选择要在该类别的子树中返回的所有操作的类别节点，例如，可以为选择整个表 （若要为表中生成的所有操作的架构） 或对表 （例如，Insert 和 Delete） 选择特定的操作针对对表的这些操作生成架构。 有关节点的详细信息，请参阅[元数据节点 IDs3](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)。  
  
#### <a name="to-retrieve-metadata-from-an-oracle-database"></a>若要从 Oracle 数据库中检索元数据  
  
1. 连接到 Oracle 数据库使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 请参阅[连接到 Visual Studio 中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**下拉列表中，选择基于是否将执行使用该适配器的入站或出站操作的协定的类型。  
  
3. 在中**选择一个类别**框中，展开 schema 节点。  
  
4. 选择你想要生成元数据的类别。 例如，如果你想要生成的表的元数据，则选择**表**。  
  
5. 展开该特定的类别节点，然后选择你想要生成元数据该节点内的特定项。  
  
    例如，若要生成特定表的元数据，请展开**表**节点，然后选择特定的表名。  
  
   > [!NOTE]
   >  如前面的过程中所述，还可以搜索特定的数据库项。  
  
6. 在中**可用类别和操作**框中，选择与你在上一步中选择的数据库项相关的操作，然后单击**添加**。 所选的操作所示**添加的类别和操作**框。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了所选的操作。  
  
    ![从 Oracle 数据库中检索元数据](../../adapters-and-accelerators/adapter-oracle-database/media/d3950566-8720-4c15-8a16-4ade14bf6221.gif "d3950566-8720-4c15-8a16-4ade14bf6221")  
  
    如果你想要为多个操作生成架构，可能有一些重复的元素定义由这些架构会导致在编译 BizTalk 项目中的问题。 例如，假设其中生成操作"Op1"的架构。 "Op1"的架构包含复杂数据类型"CT1"的参数。 对于"Op1"生成架构后关闭[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]并重新打开它以生成架构的另一项操作"Op2"。 假定"Op2"还包含复杂数据类型"CT1"的参数。 退出后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和编译项目，你将收到编译错误，因为两次在不同的 XSD 文件中定义的复杂数据类型"CT1"。 在这种情况下，我们建议：  
  
   - 生成的所有操作的架构中的一次运行[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 这可确保[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成复杂的数据类型"CT1"只有一个定义。  
  
   - 如果你想要在不同的运行中生成多个操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请确保选择**生成唯一的架构类型**复选框，以便生成的 XSD 文件包含复杂的唯一命名空间数据类型"CT1"。  
  
7. 单击“确定” 。 架构文件保存具有.xsd 扩展名为 BizTalk 项目所在的位置。  
  
    默认情况下，文件使用的命名约定创建"OracleDBBindingSchema\<n\>.xsd"，其中 n 可以是 1、 2 和等等，具体取决于创建的架构文件数量。 或者，可以通过输入一个名称中的提供的架构文件的自定义名称**文件名前缀**文本框。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]现在使用的命名约定创建架构文件\<文件名前缀\>架构\<n\>.xsd。  
  
   > [!NOTE]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建包含时指定的绑定属性的绑定文件 （XML 文件） 生成的架构操作以及要调用该操作的 SOAP 操作。 可以在 BizTalk Server 管理控制台创建 WCF 自定义端口的连接 URI，绑定属性与此绑定文件导入和 SOAP 操作集。 有关详细信息，请参阅[配置使用的 Oracle 数据库的端口绑定文件的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
   > 
   > [!IMPORTANT]
   >  使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]不会生成绑定文件。  
  
8. 在“文件”  菜单上，单击“全部保存” 。  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>生成 WCF 客户端或 WCF 服务协定使用添加适配器服务引用插件  
 可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端代码的出站操作，或者入站操作的 WCF 服务代码。  
  
#### <a name="to-retrieve-metadata-from-an-oracle-database"></a>若要从 Oracle 数据库中检索元数据  
  
1. 在中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从**选择协定类型**下拉列表中，选择基于是否将执行入站 (POLLINGSTMT) 或出站操作的协定的类型。  
  
2. 浏览或搜索类别 （如 Oracle 数据库表） 或你想要生成 WCF 客户端 （或 WCF 服务协定） 的特定操作。   
   例如，若要浏览 SCOTT 中的操作。EMP 表，在**选择一个类别**框：  
  
   1.  展开根节点 (**/**) 若要查看提供的 Oracle 数据库的架构。  
  
   2.  在根节点下，展开**SCOTT**节点以查看为 SCOTT 架构公开的类别。  
  
   3.  下**SCOTT**节点，展开**表**节点以查看的表显示为 SCOTT 的架构。  
  
   4.  下**表**节点，请选择**EMP**节点。 操作显示的 EMP 表中列出**可用类别和操作**框。  
  
3. 在中**可用类别和操作**框中，选择的操作或您要为其生成 WCF 客户端 （或 WCF 服务约定），然后单击的类别**添加**。 所选的操作所示**添加的类别和操作**框。  
  
    下图显示[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]与 SCOTT 的 Insert 和 Update 操作。选择 EMP 表。  
  
    ![选择的 Select 和 Update 操作。](../../adapters-and-accelerators/adapter-oracle-database/media/4c41ac7b-784a-494c-ac82-c007e22a4fdf.gif "4c41ac7b-784a-494c-ac82-c007e22a4fdf")  
  
   > [!IMPORTANT]
   >  具体取决于出站操作 （或类别），您选择，超过一个 WCF 客户端类可能会生成。 有关更多详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定用于 Oracle 数据库解决方案项目](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
4. 在大多数情况下的默认序列化选项是不够的;但是，如果需要可以控制生成的代码有关的几个方面和序列化程序使用的类型。 若要设置这些选项：  
  
   1. 单击**高级选项**以打开**高级选项**框。  
  
   2. 在中**高级选项**框下**选择生成的代理的选项**，选择所需的选项。 例如，可以选择是否异步方法生成 WCF 客户端或禁用配置文件的生成。  
  
   3. 下**序列化程序**选择应使用的序列化程序。  
  
      下图显示**高级选项**具有默认选择框 (**自动**处于选中状态的选择序列化程序和任何其他选项)。  
  
      ![高级选项框默认设置](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      可以在中配置的选项**高级选项**使用 ServiceModel Metadata Utility Tool (svcutil.exe) 时，框将等效于一些可用的选项。 有关这些选项的详细信息，请参阅[ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。
  
5. 单击“确定” 。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]保存 WCF 客户端类 （或 WCF 服务接口） 和帮助程序代码的操作和已选择在项目目录中的类别。 默认情况下，还保存配置文件。 为入站和出站操作; 生成略有不同的文件有关详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定用于 Oracle 数据库解决方案项目](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
   可以选择中列出的任何节点**可用类别和操作**框。 如果您选择类别节点，然后将选择所有可用的节点及其子节点下的操作。 例如，若要生成的所有显示的 EMP 表操作的 WCF 客户端，可以选择的 EMP 节点中;若要在 SCOTT 架构中生成 WCF 客户端有关的所有表，也可以选择表节点中;等等。  
  
## <a name="see-also"></a>请参阅  
[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)