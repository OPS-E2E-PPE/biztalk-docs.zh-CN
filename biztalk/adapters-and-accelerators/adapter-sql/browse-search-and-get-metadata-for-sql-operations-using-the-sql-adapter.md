---
title: 浏览、 搜索和获取 SQL 操作使用 SQL 适配器的元数据 |Microsoft Docs
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
ms.openlocfilehash: 4bb61feb6b5c100a5cb99178029f3dedd3c3fc3b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370029"
---
# <a name="browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter"></a>浏览、 搜索和获取 SQL 操作使用 SQL 适配器的元数据
本部分提供有关如何使用信息[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 通过使用这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件，你可以：  
  
- 浏览查找要为其检索元数据的操作。  
  
- 搜索要为其检索元数据的操作。  
  
- 添加所选操作的消息架构和端口绑定的配置文件来[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目时使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
- 将 WCF 客户端类或所选的操作和配置文件 (app.config) 的 WCF 服务协定 （接口） 添加到非 BizTalk 编程项目时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]时浏览和搜索操作，因此同样的主题中介绍了所有三个组件显示实质上是相同的接口。  
  
## <a name="prerequisites"></a>先决条件  
 可以浏览、 搜索，或检索元数据的目标操作之前，必须连接到 SQL Server。 有关如何连接到 SQL Server 时使用的信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[连接到 SQL Server 在 Visual Studio 中使用适配器服务外接程序使用](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)。  
  
## <a name="browsing-for-operations"></a>浏览操作  
 可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]浏览到可执行 SQL Server 的出站和入站操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
### <a name="outbound-operations"></a>出站操作  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使客户端能够执行以下出站操作。  
  
- 插入、 选择、 更新和删除对表和视图的操作。  
  
- 设置对表和视图 < column_name > 操作。 此操作对具有 varchar （max）、 nvarchar （max） 或 varbinary （max） 的列的表公开。 此类操作启用流式传输的大型对象。  
  
- 存储的过程，弱类型和强类型化为操作。  
  
- 标量和表值函数作为操作。  
  
  适配器还公开泛型的出站操作如**ExecuteReader**， **ExecuteScalar**，并**ExecuteNonQuery**根级别。  
  
### <a name="inbound-operations"></a>入站的操作  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使客户端能够执行以下入站的操作。  
  
-   **轮询**从 SQL Server 接收基于轮询的数据更改消息的操作。 此操作收到的消息不是强类型。  
  
-   **TypedPolling**从 SQL Server 接收基于轮询的数据更改消息的操作。 强类型化对于此操作收到的消息。  
  
-   **通知**操作从 SQL Server 接收查询通知。  
  
> [!NOTE]
>  适配器还支持**XmlPolling**的入站操作以在使用 SELECT 语句和包含 FOR XML 子句的存储的过程的 SQL Server 数据库上启用轮询。 但是，该适配器不公开此入站特定操作。 有关 XmlPolling 详细信息，请参阅[接收轮询消息使用包含 FOR XML 子句中使用 BizTalk Server 的 SQL SELECT 语句](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)。  
  
 有关这些操作的详细信息，请参阅[连接到 SAP 系统使用的适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)。  
  
> [!NOTE]
>  通过使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，可以浏览类别和操作节点使用 Windows 界面。  
  
 有关浏览元数据的详细信息，请参阅[获取 Visual Studio 中使用 SQL 适配器中的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。  
  
##### <a name="to-browse-outbound-operations-on-sql-server"></a>若要浏览 SQL Server 上的出站操作  
  
1. 连接到 SQL Server 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 SQL Server 在 Visual Studio 中使用适配器服务外接程序使用](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)有关的说明。  
  
2. 从**选择协定类型**列表中，为出站操作选择**客户端 （出站操作）**。  
  
3. **选择一个类别**框列出了连接到 SQL Server 数据库中可用的项目。 单击项目以查看可对该项目中的操作**可用类别和操作**框。  
  
   > [!TIP]
   >  您可以直接转到"即时"类别节点或子类别节点在树中，键入项目的名称的树视图中聚焦时**选择一个类别**框。 例如，若要跳转到**员工**表节点中，重点介绍**表**节点，并键入`Employee`。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 选择根节点 （/），并且可用的根节点下的常规类别节点中列出**可用类别和操作**框。  
  
    ![操作和类别可在根级别](../../adapters-and-accelerators/adapter-sql/media/3eef7b99-da8e-4b98-8b14-8e48fd7b3801.gif "3eef7b99-da8e-4b98-8b14-8e48fd7b3801")  
  
   > [!NOTE]
   >  ExecuteReader、 ExecuteScalar ExecuteNonQuery 等标准的 SQL Server 操作的根级别均可用。 有关这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。  
  
4. 若要查看 SQL Server 数据库中提供的过程，请单击**过程**节点。 在下图中，**过程**中选择节点**选择一个类别**框中和相应的过程中列出**可用类别和操作框**.  
  
    ![浏览 SQL Server 中的过程](../../adapters-and-accelerators/adapter-sql/media/e3b1a070-4077-4e4d-bfc7-558df9b8b9d5.gif "e3b1a070-4077-4e4d-bfc7-558df9b8b9d5")  
  
   > [!NOTE]
   >  下列出的过程属于同一套**过程**节点下也有**Strongly-Typed 过程**节点。 区别在于生成架构的方式。 为下一个过程**过程**节点，该架构是弱类型化。 但是，对于下一个过程**Strongly-Typed 过程**节点，该架构强类型化。 强类型架构是如果你想要将某一操作的架构映射到另一个操作使用 BizTalk 映射器，因为该架构可供您在设计时创建 BizTalk 项目时很有用。 有关弱类型化的过程，在运行时作为响应消息的一部分接收过程的架构。  
  
5. 若要查看 SQL Server 数据库中的表，请单击**表**节点。 或者，依次展开**表**节点。  
  
6. 若要查看表支持的操作，请单击表名称。  
  
    下图显示了一系列中的表**选择一个类别**框。 **可用类别和操作**框列出了支持所选表的操作。  
  
    ![浏览 SQL Server 数据库中的表](../../adapters-and-accelerators/adapter-sql/media/3966f3b9-85a0-4354-8ed4-da5ae74c9885.gif "3966f3b9-85a0-4354-8ed4-da5ae74c9885")  
  
   > [!NOTE]
   >  如果 SQL Server 表中包含的类型 varchar （max）、 nvarchar （max） 和 varbinary （max） 列，该适配器还公开了特定操作来更新该列中的数据。 此操作的名称是设置 < column_name >。 例如，如果表包含列"Job_Description"的类型 varchar （max），该操作的名称是"SetJob_Description"。  
  
7. 若要查看 SQL Server 数据库中的视图，请单击**视图**节点。 或者，依次展开**视图**节点。  
  
8. 若要查看支持在视图上的操作，请单击视图名称。  
  
    下图显示了一系列中的视图**选择一个类别**框。 **可用类别和操作**框列出了支持的所选视图的操作。  
  
    ![浏览 SQL Server 数据库中的视图](../../adapters-and-accelerators/adapter-sql/media/67362fb2-35fb-4afb-8ff6-e519b26bd187.gif "67362fb2-35fb-4afb-8ff6-e519b26bd187")  
  
   > [!NOTE]
   >  如果视图包含的类型 varchar （max）、 nvarchar （max） 和 varbinary （max） 列，该适配器还公开了特定操作来更新该列中的数据。 此操作的名称是设置 < column_name >。 例如，如果表包含列"Job_Description"的类型 varchar （max），该操作的名称是"SetJob_Description"。  
  
9. 若要查看列表中的 SQL Server 数据库中定义的标量函数**可用类别和操作**框中，单击**标量函数**节点。  
  
     在下图中，**标量函数**中选择节点**选择一个类别**框中，以及相应的功能中列出**可用类别和操作**框。  
  
     ![浏览 SQL Server 中的标量函数](../../adapters-and-accelerators/adapter-sql/media/78b9f720-2cb2-44a8-b8cc-49e4fb608a1f.gif "78b9f720-2cb2-44a8-b8cc-49e4fb608a1f")  
  
10. 若要查看表的列表值中的 SQL Server 数据库中定义的函数**可用类别和操作**框中，单击**表值函数**节点。  
  
     在下图中，**表值函数**中选择节点**选择一个类别**框中，以及相应的功能中列出**可用类别和操作**框。  
  
     ![浏览 SQL Server 中的表值函数](../../adapters-and-accelerators/adapter-sql/media/b007059f-280e-40d7-9553-eca4216296f4.gif "b007059f-280e-40d7-9553-eca4216296f4")  
  
##### <a name="to-browse-inbound-operations-on-sql-server"></a>若要浏览 SQL Server 上的入站的操作  
  
1. 连接到 SQL Server 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 SQL Server 在 Visual Studio 中使用适配器服务外接程序使用](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)有关的说明。  
  
2. 从**选择协定类型**列表中的，对于入站操作，选择**服务 （入站操作）**。  
  
3. 支持的所有入站的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可在根节点上。 单击要查看可用的入站的操作的根节点 （/）。  
  
    ![入站适配器支持的操作](../../adapters-and-accelerators/adapter-sql/media/133732c0-ca8f-4e57-8a70-ba4fb561a37b.gif "133732c0-ca8f-4e57-8a70-ba4fb561a37b")  
  
## <a name="searching-for-operations"></a>搜索操作  
 可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]搜索 SQL Server 数据库中的特定项目。 搜索 SQL Server 元数据时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
- 搜索表达式中支持通配符和转义字符。  
  
- 可以立即执行搜索操作的间隔的节点下的搜索。 例如，若要搜索一个表，您必须搜索 \Table 下。 不支持多级别的搜索。  
  
  下表列出了可用于搜索项目和通过其解释的特殊字符[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
|特殊字符|解释|示例|  
|-----------------------|--------------------|-------------|  
|_（下划线）|只匹配一个字符|"A_"匹配 AB、 AC、 AD。|  
|%|匹配零个或多个字符|"%"匹配一个，AB，AC。|  
|[ ]|-转义的特殊含义的 %和 _<br />-指定一个范围或一组字符出现|-%[%] %匹配所有包含 %字符的名称。<br />-[a-f] 匹配所有名称之间 （也包括） 包含字符 a 和 f。<br />-[abc] 匹配所有名称中使用了字符 a、 b 和 c。|  
|[^]|指定的范围或组的字符不存在|-[^ a-f] 与不具有字符之间 （也包括） 的所有名称都匹配 a 和 f。<br />-[^ abc] 匹配不包含字符 a、 b 的所有名称和 c。|  
  
> [!NOTE]
>  转义符是放在通配符，以指示通配符应当解释为常规字符而不是通配符之前的字符。  
  
 有关详细信息，请参阅[获取 Visual Studio 中使用 SQL 适配器中的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。  
  
 若要在使用 SQL Server 中搜索元数据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，执行以下步骤。  
  
#### <a name="to-search-metadata-in-sql-server"></a>若要在 SQL Server 中搜索元数据  
  
1. 连接到 SQL Server 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 SQL Server 在 Visual Studio 中使用适配器服务外接程序使用](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)有关的说明。  
  
2. 从**选择协定类型**列表中，选择基于无论所搜索的入站或出站操作的协定的类型。  
  
3. 在中**选择一个类别**框中，单击要在其下搜索特定项目的类别节点。 例如，若要搜索的表，请单击**表**节点。  
  
4. 在中**类别中的搜索**框中，键入要搜索特定项目的搜索表达式。 例如，若要搜索其名称中包含"客户"表，请键入`%Customer%`。  
  
   > [!NOTE]
   >  区分大小写的搜索字符串。  
  
5. 若要开始搜索，单击向右箭头图标按钮。 搜索完成后**可用类别和操作**框列出了满足搜索条件的项目。  
  
    下图显示了其名称中包含"客户"的 SQL Server 表。  
  
    ![在 SQL Server 中搜索元数据](../../adapters-and-accelerators/adapter-sql/media/62c24ed3-f4e5-47de-8e8d-35af96e6c5ec.gif "62c24ed3-f4e5-47de-8e8d-35af96e6c5ec")  
  
## <a name="generating-schema-for-biztalk-projects"></a>对于 BizTalk 项目的生成架构  
 可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成所选 SQL Server 项目的架构。 浏览并搜索你想要调用的项目后，您可以生成的项目的架构和发送消息，符合架构，到 SQL Server。  
  
> [!NOTE]
>  可以选择要在该类别的子树中返回的所有操作的类别节点，例如，可以为选择整个表 （若要为表中生成的所有操作的架构） 或对表 （例如，Insert 和 Delete） 选择特定的操作针对对表的这些操作生成架构。 有关节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)。  
  
#### <a name="to-generate-schema-for-sql-server-artifacts"></a>若要为 SQL Server 项目生成架构  
  
1. 连接到 SQL Server 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 请参阅[连接到 SQL Server 在 Visual Studio 中使用适配器服务外接程序使用](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)有关的说明。  
  
   > [!IMPORTANT]
   >  若要生成使用执行操作的架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]必须设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。 必须建立与 SQL Server 数据库的连接时设置此绑定属性。  
  
2. 从**选择协定类型**列表中，选择基于是否正在生成架构的入站或出站操作的协定的类型。  
  
3. 单击你要为其生成元数据的类别节点。 例如，如果你想要生成的表的元数据，请单击**表**。  
  
4. 展开类别节点，然后选择你想要生成元数据该节点内的特定项。 例如，若要生成"CustomerTable"表的操作的元数据，请展开**表**节点，并单击**CustomerTable**。  
  
5. 在中**可用类别和操作**框中，选择你想要在 SQL Server 上执行，并单击操作**添加**。 所选的操作所示**添加的类别和操作**框。 例如，若要执行的插入和选择操作"CustomerTable"表上的，单击操作名称，然后单击**添加**。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，其中列出了所选的操作。  
  
    ![从 SQL Server 检索元数据](../../adapters-and-accelerators/adapter-sql/media/a6a95291-f6ed-46d1-bacc-2dfc27638117.gif "a6a95291-f6ed-46d1-bacc-2dfc27638117")  
  
    如果你想要为多个操作生成架构，可能有一些重复的元素定义由这些架构会导致在编译 BizTalk 项目中的问题。 例如，假设其中生成操作"Op1"的架构。 "Op1"的架构包含数据类型"CT1"的参数。 对于"Op1"生成架构后关闭[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]并重新打开它以生成架构的另一项操作"Op2"。 假定"Op2"还包含数据类型"CT1"的参数。 退出后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和编译项目，你将收到编译错误，因为两次在不同的 XSD 文件中定义的复杂数据类型"CT1"。 在这种情况下，我们建议：  
  
   - 生成的所有操作的架构中的一次运行[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 这可确保[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成复杂的数据类型"CT1"只有一个定义。  
  
   - 如果你想要在不同的运行中生成多个操作的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请确保选择**生成唯一的架构类型**复选框，以便生成的 XSD 文件包含的唯一命名空间复杂数据类型"CT1"。  
  
6. 单击“确定” 。 架构文件保存具有.xsd 扩展名为 BizTalk 项目所在的位置。  
  
   > [!NOTE]
   >  如果使用的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]与特定的命名约定创建的文件的默认情况下生成 SQL Server 项目的元数据。 包含生成的 WSDL **fileNameHint**批注标记包含应分配到 XSD 文件的名称。 例如，针对表操作的架构文件的文件名称提示遵循约定 TableOperation。\<架构\>。\<tablename\>。 如果你想要自定义生成的 XSD 文件的名称，则可以提供中的前缀**文件名前缀**框。 最后，XSD 文件的名称后到达为文件名前缀 + fileNameHint + 唯一整数 （如果需要，以确保文件名是唯一的）。  
   > 
   > [!NOTE]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建包含时指定的绑定属性的绑定文件 （XML 文件） 生成的架构操作以及要调用该操作的 SOAP 操作。 可以在此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 WCF 自定义端口或 BizTalk SQL 适配器与连接 URI 的端口、 绑定属性和 SOAP 操作集。 有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
    已成功生成 SQL Server 项目的元数据。 元数据可用于将消息发送到 SQL Server 来执行特定操作。 请参阅[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)有关如何执行这些操作的详细信息。  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>生成 WCF 客户端或 WCF 服务协定使用添加适配器服务引用插件  
 可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端代码的出站操作，或者入站操作的 WCF 服务代码。  
  
#### <a name="to-generate-wcf-client-class-or-service-contract-for-sql-server-operations"></a>若要生成 WCF 客户端类或服务约定的 SQL Server 操作  
  
1. 在中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从**选择协定类型**下拉列表中，选择基于是否将执行入站或出站操作的协定的类型。  
  
2. 浏览或搜索类别 （如数据库表） 或你想要生成 WCF 客户端 （或 WCF 服务协定） 的特定操作。   
   例如，若要在浏览 Employee 表中的操作**选择一个类别**框：  
  
   1.  展开根节点 (**/**) 若要查看其下操作提供的 SQL Server 数据库的类别。  
  
   2.  在根节点下，展开**表**节点以查看可用的表。  
  
3. 单击**员工**表节点，然后在**可用类别和操作**框中，选择的操作或你想要生成 WCF 客户端 （或 WCF 服务约定） 的类别，然后单击**添加**。 所选的操作所示**添加的类别和操作**框。  
  
    下图显示[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]对 Insert 和 Select 操作为 Employee 表选择。  
  
    ![生成 WCF 客户端或服务协定](../../adapters-and-accelerators/adapter-sql/media/sql-adap-add-adap-serv-ref.gif "sql_adap_add_adap_serv_ref")  
  
   > [!IMPORTANT]
   >  具体取决于出站操作 （或类别），您选择，超过一个 WCF 客户端类可能会生成。 有关更多详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
4. 在大多数情况下的默认序列化选项是不够的;但是，如果需要可以控制生成的代码有关的几个方面和序列化程序使用的类型。 若要设置这些选项：  
  
   1. 单击**高级选项**以打开**高级选项**框。  
  
   2. 在中**高级选项**框下**选择生成的代理的选项**，选择所需的选项。 例如，可以选择是否异步方法生成 WCF 客户端或禁用配置文件的生成。  
  
   3. 下**序列化程序**选择应使用的序列化程序。  
  
      下图显示**高级选项**具有默认选择框 (**自动**处于选中状态的选择序列化程序和任何其他选项)。  
  
      ![高级选项框默认设置](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      可以在中配置的选项**高级选项**使用 ServiceModel Metadata Utility Tool (svcutil.exe) 时，框将等效于一些可用的选项。 有关这些选项的详细信息，请参阅[ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。 
  
5. 单击“确定” 。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]保存 WCF 客户端类 （或 WCF 服务接口） 和帮助程序代码的操作和已选择在项目目录中的类别。 默认情况下，还保存配置文件。 为入站和出站操作; 生成略有不同的文件有关详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
   可以选择中列出的任何节点**可用类别和操作**框。 如果您选择类别节点，然后将选择所有可用的节点及其子节点下的操作。 例如，若要生成的所有操作显示 Employee 表的 WCF 客户端，可以选择员工节点。  
  
## <a name="see-also"></a>请参阅  
 [获取 Visual Studio 中使用 SQL 适配器中的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)