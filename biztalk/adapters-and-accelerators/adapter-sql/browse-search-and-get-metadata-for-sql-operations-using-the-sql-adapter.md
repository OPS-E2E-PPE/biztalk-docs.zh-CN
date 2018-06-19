---
title: 浏览、 搜索和使用 SQL 适配器的 SQL 操作中获取元数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdd5ca6f-30ff-4d32-a656-bbd54b9d072e
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fab8d26f7f4da3c60587bd7d2863941080c69953
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967955"
---
# <a name="browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter"></a>浏览、 搜索和使用 SQL 适配器的 SQL 操作中获取元数据
本部分提供有关如何使用信息[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 通过使用这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件，你可以：  
  
-   浏览要为其检索元数据的操作。  
  
-   搜索为其检索元数据的操作。  
  
-   添加所选操作的消息架构和端口绑定配置文件添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目时使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
-   WCF 客户端类或所选的操作和配置文件 (app.config) 的 WCF 服务协定 （接口） 向项目中添加非 BizTalk 编程时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]当您浏览和搜索操作，因此相同的主题中所述所有三个组件时所显示实质上是相同的接口。  
  
## <a name="prerequisites"></a>先决条件  
 你可以浏览、 搜索，或检索元数据的目标操作之前，你必须连接到 SQL Server。 有关如何连接到 SQL Server 中，当你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)。  
  
## <a name="browsing-for-operations"></a>浏览操作  
 你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要浏览的出站和入站操作，可以在 SQL Server 上执行使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
### <a name="outbound-operations"></a>出站操作  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使客户端可以执行以下出站操作。  
  
-   插入、 选择，更新和删除表和视图上的操作。  
  
-   设置 < column_name > 操作对表和视图。 此操作是在具有 varchar （max）、 nvarchar 或 varbinary （max） 的列的表上公开的。 此类操作启用流式处理的大型对象。  
  
-   存储的过程，弱和强类型化为操作。  
  
-   标量和表值函数作为操作。  
  
 适配器还公开泛型的出站操作如**ExecuteReader**， **ExecuteScalar**，和**ExecuteNonQuery**在根级别。  
  
### <a name="inbound-operations"></a>入站的操作  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使客户端可以执行以下入站的操作。  
  
-   **轮询**从 SQL Server 接收基于轮询的数据更改消息的操作。 对于此操作收到的消息不是强类型。  
  
-   **TypedPolling**从 SQL Server 接收基于轮询的数据更改消息的操作。 对于此操作收到的消息是强类型。  
  
-   **通知**操作从 SQL Server 接收查询通知。  
  
> [!NOTE]
>  适配器还支持**XmlPolling**入站操作以启用对使用 SELECT 语句和存储的过程中包含 FOR XML 子句的 SQL Server 数据库的轮询。 但是，该适配器不公开此入站特定操作。 有关 XmlPolling 的详细信息，请参阅[接收使用 FOR XML 子句中使用 BizTalk Server 的 SQL SELECT 语句的轮询消息](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)。  
  
 有关这些操作的详细信息，请参阅[连接到 SAP 系统使用适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)。  
  
> [!NOTE]
>  通过使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，你可以浏览类别和操作节点上使用 Windows 界面。  
  
 有关浏览元数据的详细信息，请参阅[为使用 SQL 适配器的 Visual Studio 中的 SQL Server 操作获取元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。  
  
##### <a name="to-browse-outbound-operations-on-sql-server"></a>若要浏览 SQL Server 上的出站操作  
  
1.  连接到 SQL Server 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)有关的说明。  
  
2.  从**选择协定类型**列出，请为出站操作选择**客户端 （出站操作）**。  
  
3.  **选择类别**框中列出的提供连接到 SQL Server 数据库中的项目。 单击要查看为该项目中的可用操作的项目**可用类别和操作**框。  
  
    > [!TIP]
    >  你可以直接转到"即时"类别节点或子类别节点在树中，通过键入该项目的名称上时将焦点的树视图中**选择类别**框。 例如，若要跳转到**员工**表节点，请关注**表**节点，并键入`Employee`。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 选择根节点 （/），并且中列出了可用的根节点下的常规类别节点**可用类别和操作**框。  
  
     ![操作和类别在根级别](../../adapters-and-accelerators/adapter-sql/media/3eef7b99-da8e-4b98-8b14-8e48fd7b3801.gif "3eef7b99-da8e-4b98-8b14-8e48fd7b3801")  
  
    > [!NOTE]
    >  在根级别均还提供如 ExecuteReader、 ExecuteScalar 和 ExecuteNonQuery 标准的 SQL Server 操作。 有关这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。  
  
4.  若要查看可用 SQL Server 数据库中的过程，请单击**过程**节点。 在下图中，**过程**中选择节点**选择类别**和对应的步骤中列出的在**可用类别和操作框中**.  
  
     ![浏览 SQL Server 中的过程](../../adapters-and-accelerators/adapter-sql/media/e3b1a070-4077-4e4d-bfc7-558df9b8b9d5.gif "e3b1a070-4077-4e4d-bfc7-558df9b8b9d5")  
  
    > [!NOTE]
    >  下列出的过程属于同一套**过程**节点下也有**Strongly-Typed 过程**节点。 差别在于生成架构的方式。 为下一个过程**过程**节点，架构是弱类型化。 但是，对于下一个过程**Strongly-Typed 过程**节点，强类型的架构。 强类型的架构是如果你想要将一个操作的架构映射到另一个操作使用 BizTalk 映射程序，因为在创建 BizTalk 项目中，架构可用于你在设计时有用。 有关弱类型化的过程，在运行时作为响应消息的一部分接收过程的架构。  
  
5.  若要查看 SQL Server 数据库中的表，单击**表**节点。 或者，展开**表**节点。  
  
6.  若要查看支持对表的操作，请单击表名称。  
  
     下图显示中的表列表**选择类别**框。 **可用类别和操作**框列出了支持所选表的操作。  
  
     ![浏览 SQL Server 数据库中的表](../../adapters-and-accelerators/adapter-sql/media/3966f3b9-85a0-4354-8ed4-da5ae74c9885.gif "3966f3b9-85a0-4354-8ed4-da5ae74c9885")  
  
    > [!NOTE]
    >  如果 SQL Server 表中包含的类型 varchar （max）、 nvarchar (max) 和 varbinary （max） 列，该适配器还公开特定的操作，以更新该列中的数据。 此操作的名称是设置 < column_name >。 例如，如果表中包含"Job_Description"的类型 varchar （max） 列，该操作的名称是"SetJob_Description"。  
  
7.  若要查看 SQL Server 数据库的视图中，单击**视图**节点。 或者，展开**视图**节点。  
  
8.  若要查看支持视图上的操作，请单击视图名称。  
  
     下图显示在视图的列表**选择类别**框。 **可用类别和操作**框中列出的选定视图支持的操作。  
  
     ![浏览 SQL Server 数据库中的视图](../../adapters-and-accelerators/adapter-sql/media/67362fb2-35fb-4afb-8ff6-e519b26bd187.gif "67362fb2-35fb-4afb-8ff6-e519b26bd187")  
  
    > [!NOTE]
    >  如果视图包含类型 varchar （max）、 nvarchar (max)，和 varbinary （max） 列，该适配器还公开特定的操作，以更新该列中的数据。 此操作的名称是设置 < column_name >。 例如，如果表中包含"Job_Description"的类型 varchar （max） 列，该操作的名称是"SetJob_Description"。  
  
9. 若要查看的 SQL Server 数据库中定义的标量函数的列表**可用类别和操作**框中，单击**标量函数**节点。  
  
     在下图中，**标量函数**中选择节点**选择类别**列入框中，以及相应的功能**可用类别和操作**框。  
  
     ![浏览 SQL Server 中的标量函数](../../adapters-and-accelerators/adapter-sql/media/78b9f720-2cb2-44a8-b8cc-49e4fb608a1f.gif "78b9f720-2cb2-44a8-b8cc-49e4fb608a1f")  
  
10. 若要查看的表列表值中的 SQL Server 数据库中定义的函数**可用类别和操作**框中，单击**表值函数**节点。  
  
     在下图中，**表值函数**中选择节点**选择类别**列入框中，以及相应的功能**可用类别和操作**框。  
  
     ![浏览 SQL Server 中的表值函数](../../adapters-and-accelerators/adapter-sql/media/b007059f-280e-40d7-9553-eca4216296f4.gif "b007059f-280e-40d7-9553-eca4216296f4")  
  
##### <a name="to-browse-inbound-operations-on-sql-server"></a>若要浏览 SQL Server 上的入站的操作  
  
1.  连接到 SQL Server 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)有关的说明。  
  
2.  从**选择协定类型**列表中的，对于入站操作，选择**服务 （入站操作）**。  
  
3.  支持的所有入站的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可在根节点上。 单击要查看可用的入站的操作的根节点 （/）。  
  
     ![入站操作适配器支持的](../../adapters-and-accelerators/adapter-sql/media/133732c0-ca8f-4e57-8a70-ba4fb561a37b.gif "133732c0-ca8f-4e57-8a70-ba4fb561a37b")  
  
## <a name="searching-for-operations"></a>搜索操作  
 你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]搜索 SQL Server 数据库中的特定项目。 搜索 SQL Server 元数据时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
-   在搜索表达式中支持通配符和转义字符。  
  
-   立即在从该处执行搜索操作的节点下启用搜索。 例如，若要搜索一个表，您必须搜索 \Table 下。 不支持多级搜索。  
  
 下表列出了可用于搜索项目和其解释的特殊字符[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
|特殊字符|解释|示例|  
|-----------------------|--------------------|-------------|  
|_（下划线）|完全匹配一个字符|"A_"匹配 AB、 AC、 AD。|  
|%|匹配零个或多个字符|"%"匹配 A，AB，交流。|  
|[ ]|-转义的特殊含义的 %和 _<br />-指定一个范围或一组要显示的字符|-%[%] %匹配包括 %符号的所有名称。<br />-[a f] 匹配所有名称之间 （并包括） 包含字符 a 和 f。<br />-[abc] 匹配具有字符 a，b 的所有名称和 c。|  
|[^]|指定的范围或组的字符不存在|-[^ a-f] 与不具有字符之间 （并包括） 的所有名称相都匹配 a 和 f。<br />-[^ abc] 匹配的所有名称都不具有字符 a，b 和 c。|  
  
> [!NOTE]
>  转义字符是通配符字符以指示作为常规字符而不是通配符，应解释通配符的前面放置一个字符。  
  
 有关详细信息，请参阅[为使用 SQL 适配器的 Visual Studio 中的 SQL Server 操作获取元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。  
  
 要搜索的元数据中使用 SQL Server [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，执行以下步骤。  
  
#### <a name="to-search-metadata-in-sql-server"></a>若要在 SQL Server 中搜索元数据  
  
1.  连接到 SQL Server 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)有关的说明。  
  
2.  从**选择协定类型**列表中，选择基于是否要搜索入站或出站操作的协定的类型。  
  
3.  在**选择类别**框中，单击要在其下搜索特定项目的类别节点。 例如，若要搜索一个表，请单击**表**节点。  
  
4.  在**类别中的搜索**框中，键入要搜索特定项目搜索表达式。 例如，若要搜索其名称中包含"客户"的表，请键入`%Customer%`。  
  
    > [!NOTE]
    >  区分大小写的搜索字符串。  
  
5.  若要开始搜索，请单击带有右箭头图标的按钮。 完成搜索后**可用类别和操作**框中列出的满足搜索条件的项目。  
  
     下图显示其名称中包含"客户"的 SQL Server 表。  
  
     ![SQL Server 中搜索元数据](../../adapters-and-accelerators/adapter-sql/media/62c24ed3-f4e5-47de-8e8d-35af96e6c5ec.gif "62c24ed3-f4e5-47de-8e8d-35af96e6c5ec")  
  
## <a name="generating-schema-for-biztalk-projects"></a>为 BizTalk 项目生成架构  
 你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成为选择的 SQL Server 项目的架构。 浏览并搜索你想要调用的项目后，你可以生成这些项目的架构和发送消息，符合架构，到 SQL Server。  
  
> [!NOTE]
>  你可以选择要在该类别的子树中返回的所有操作的类别节点-例如，你可以选择整个表 （以生成表中的所有操作的架构） 或表 （例如，Insert 和 Delete） 选择特定的操作生成对表的这些操作的架构。 有关节点的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)。  
  
#### <a name="to-generate-schema-for-sql-server-artifacts"></a>若要生成的 SQL Server 项目架构  
  
1.  连接到 SQL Server 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 请参阅[连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)有关的说明。  
  
    > [!IMPORTANT]
    >  若要生成使用执行操作的架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]必须设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。 建立与 SQL Server 数据库的连接时，必须设置此绑定属性。  
  
2.  从**选择协定类型**列表中，选择基于是否正在生成架构的入站或出站操作的协定的类型。  
  
3.  单击你想要生成元数据的类别节点。 例如，如果你想要生成表元数据，请单击**表**。  
  
4.  展开类别节点中，并选择你想要生成元数据节点中的特定项。 例如，若要生成元数据"CustomerTable"表上的操作，请展开**表**节点，，然后单击**CustomerTable**。  
  
5.  在**可用类别和操作**框中，选择你想要在 SQL Server 上执行，然后单击操作**添加**。 中列出了所选的操作**添加类别和操作**框。 例如，若要执行 Insert 和 Select 操作"CustomerTable"表上的，单击操作名称，然后单击**添加**。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了所选的操作。  
  
     ![从 SQL Server 检索元数据](../../adapters-and-accelerators/adapter-sql/media/a6a95291-f6ed-46d1-bacc-2dfc27638117.gif "a6a95291-f6ed-46d1-bacc-2dfc27638117")  
  
     如果你想要为多个操作生成架构，可能有一些重复的元素定义之间可能会导致失败编译 BizTalk 项目这些架构。 例如，考虑其中生成操作"Op1"的架构的方案。 "Op1"的架构包含数据类型"CT1"的参数。 为"Op1"生成架构后，你关闭[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]然后重新打开它以生成用于另一操作"Op2"的架构。 假定"Op2"还包含数据类型"CT1"的参数。 退出后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和编译该项目，你将收到编译错误，因为两次在不同的 XSD 文件中定义的复杂数据类型"CT1"。 在这种情况下，我们的建议如下：  
  
    -   中的一次运行生成的所有操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 这样可确保[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成只有一个定义的复杂数据类型"CT1"。  
  
    -   如果你想要跨不同运行的生成对多个操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请确保选择**生成唯一的架构类型**复选框，以便生成的 XSD 文件包含唯一的命名空间复杂数据类型"CT1"。  
  
6.  单击 **“确定”**。 架构文件保存带.xsd 扩展名为 BizTalk 项目所在的位置。  
  
    > [!NOTE]
    >  如果你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]使用特定的命名约定创建的文件的默认情况下生成 SQL Server 项目的元数据。 生成的 WSDL 将包含**fileNameHint**批注标记包含应分配到 XSD 文件的名称。 例如，表操作的架构文件的文件名称提示遵循的约定 TableOperation。\<架构\>。\<tablename\>。 如果你想要自定义生成的 XSD 文件的名称，你可以提供前缀的**文件名前缀**框。 最后，XSD 文件的名称后到达为文件名前缀 + fileNameHint + 唯一整数 （如果需要，确保文件名是唯一的）。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建包含时指定的绑定属性的绑定文件 （XML 文件） 生成某一操作和要调用的操作的 SOAP 操作的架构。 你可以导入中的此绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 WCF 自定义端口或 BizTalk SQL 适配器与连接 URI 的端口、 绑定属性和的 SOAP 操作设置。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
     你已成功生成 SQL Server 项目的元的数据。 元数据可用于将消息发送到 SQL Server 来执行特定操作。 请参阅[开发 BizTalk 应用程序使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)有关如何执行这些操作的详细信息。  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>生成 WCF 客户端或 WCF 服务协定使用添加插件的适配器服务引用  
 你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端代码用于出站操作，或者为入站操作的 WCF 服务代码。  
  
#### <a name="to-generate-wcf-client-class-or-service-contract-for-sql-server-operations"></a>若要生成 WCF 客户端类或服务协定的 SQL Server 操作  
  
1.  在[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从**选择协定类型**下拉列表中，选择基于你将会执行入站或出站操作的协定的类型。  
  
2.  浏览或搜索的类别 （如数据库表） 或你想要生成 WCF 客户端 （或 WCF 服务协定） 的特定操作。   
    例如，若要浏览查找员工表中的操作中**选择类别**框：  
  
    1.  展开根节点 (**/**) 若要查看在其下操作中加以表示为 SQL Server 数据库的类别。  
  
    2.  在根节点下展开**表**节点以查看可用的表。  
  
3.  单击**员工**表节点，然后在**可用类别和操作**框中，选择你想要生成 WCF 客户端 （或 WCF 服务协定） 的类别的操作，然后单击**添加**。 中列出了所选的操作**添加类别和操作**框。  
  
     下图显示[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]对 Insert 和用于选择的员工表选择操作。  
  
     ![生成 WCF 客户端或服务协定](../../adapters-and-accelerators/adapter-sql/media/sql-adap-add-adap-serv-ref.gif "sql_adap_add_adap_serv_ref")  
  
    > [!IMPORTANT]
    >  具体取决于的出站操作 （或类别），您选择，超过一个 WCF 客户端类可能会生成。 有关更多详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
4.  在大多数情况下的默认序列化选项已足够;但是，如果需要你可以控制生成的代码有关的几个方面和序列化程序使用的类型。 若要设置这些选项：  
  
    1.  单击**高级选项**以打开**高级选项**框。  
  
    2.  在**高级选项**下框中**选择生成的代理的选项**，选择所需的选项。 例如，你可以选择是否为 WCF 客户端生成异步方法，或禁用配置文件的生成。  
  
    3.  下**序列化程序**选择应使用的序列化程序。  
  
     下图显示**高级选项**包装盒默认选择 (**自动**选择为所选序列化程序和任何其他选项)。  
  
     ![高级选项框中的默认设置](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     你可以在配置的选项**高级选项**使用 ServiceModel 元数据实用工具 (svcutil.exe) 时，框将等效于某些可用的选项。 有关这些选项的详细信息，请参阅[ServiceModel 元数据实用工具 (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。 
  
5.  单击 **“确定”**。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将保存的 WCF 客户端类 （或 WCF 服务接口） 和帮助器代码的操作和你选择了你的项目目录中的类别。 默认情况下，也保存配置文件。 为入站和出站操作; 生成略有不同的文件有关详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
 你可以选择中列出的任何节点**可用类别和操作**框。 如果你选择的类别节点，则该节点及其子节点下可执行的操作的所有将被选中。 例如，若要生成的所有操作的员工表中加以表示的 WCF 客户端，可以选择员工节点。  
  
## <a name="see-also"></a>另请参阅  
 [使用 SQL 适配器的 Visual Studio 中的 SQL Server 操作中获取元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)