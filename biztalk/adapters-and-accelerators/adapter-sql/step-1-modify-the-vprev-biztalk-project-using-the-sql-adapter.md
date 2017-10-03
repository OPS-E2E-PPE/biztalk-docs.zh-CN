---
title: "步骤 1： 修改 vPrev BizTalk 项目使用的 SQL 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25ad959b-2818-47b8-9a09-3681abb75887
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f0eb02594251fa5ab1c209c1d2655056cf489df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter"></a>步骤 1： 修改 vPrev BizTalk 项目使用的 SQL 适配器
![步骤 1，共 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **完成时间：** 10 分钟  
  
 **目标：**向现有 vPrev BizTalk 项目在此步骤中，进行以下更改：  
  
-   生成上使用基于 WCF 的 Customer 表的插入操作的元数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
-   用于执行插入操作执行使用基于 WCF 的插入操作使用请求消息的 vPrev SQL 适配器将请求消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
-   将使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到使用 vPrev SQL 适配器接收响应消息。  
  
## <a name="prerequisites"></a>先决条件  
 你必须有一个 vPrev BizTalk 项目，在 SQL Server 数据库中执行对 Customer 表的插入操作。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>若要修改 vPrev BizTalk 项目  
  
1.  生成上使用基于 WCF 的 Customer 表的插入操作的元数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 你可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成的元数据。  
  
     有关如何生成元数据的说明，请参阅[获取元数据使用的 SQL 适配器的 Visual Studio 中的 SQL Server 操作](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。 生成架构后，其名称类似于文件*TableOperation.dbo.Customer.xsd*添加到 BizTalk 项目。 此文件包含用于发送一条消息，在使用基于 WCF 的 SQL Server 数据库中执行对 Customer 表的 Insert 操作架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
2.  生成插入操作的元数据还会创建端口绑定文件。 在下一步的步骤中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到的 SQL Server 数据库。 该操作的 SOAP 操作也设置为其生成元数据的操作。 例如，如果生成用于插入操作的元数据，请在发送端口上的 SOAP 操作中的操作名称将"插入"。 但是，该操作将在你为业务流程的一部分可能不同，例如，创建的逻辑发送端口上"Operation_1"。 结果是，当消息发送到使用发送端口的 SQL Server 数据库时，你将收到错误。 若要防止此情况，请确保发送端口业务流程中的是为其生成元数据的操作名称相同的逻辑上的操作名称。  
  
     因此，本教程中，如果由于生成用于插入操作的元数据，更改到"插入"的逻辑发送端口操作的名称。  
  
3.  对于请求消息中，生成使用 vPrev 到生成使用基于 WCF 的架构的 SQL 数据库适配器将架构映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
    1.  将 BizTalk 映射程序添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。  
  
         在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定的名称映射，如**RequestMap.btm**。 单击 **“添加”**。  
  
    2.  从源架构窗格中，单击**打开源架构**。  
  
    3.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev SQL 适配器请求消息的架构。 对于本教程中，选择*New_Migration.InsertCustomerService*，然后单击**确定**。  
  
    4.  在**源架构的根节点**对话框中，选择*插入*，然后单击**确定**。  
  
    5.  从目标架构窗格中，单击**打开目标架构**。  
  
    6.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择的基于 WCF 的请求消息的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 对于本教程中，选择*New_Migration.TableOperation.dbo.Customer*，然后单击**确定**。  
  
    7.  在**目标架构的根节点**对话框中，选择*插入*，然后单击**确定**。  
  
    8.  下图中所示映射这两个架构中的相应元素。  
  
         ![将请求架构映射](../../adapters-and-accelerators/adapter-sql/media/850bbf52-fc3e-42c5-b879-51c6e39a502d.gif "850bbf52-fc3e-42c5-b879-51c6e39a502d")  
  
    9. 保存映射。  
  
4.  响应消息中，使用架构生成使用基于 WCF 的 vPrev SQL 适配器生成将架构映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
    1.  将 BizTalk 映射程序添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。  
  
         在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定的名称映射，如**ResponseMap.btm**，然后单击**添加**。  
  
    2.  从源架构窗格中，单击**打开源架构**。  
  
    3.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择的基于 WCF 的响应消息的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 对于本教程中，选择*New_Migration.TableOperation.dbo.Customer*，然后单击**确定**。  
  
    4.  在**源架构的根节点**对话框中，选择*InsertResponse*，然后单击**确定**。  
  
    5.  从目标架构窗格中，单击**打开目标架构**。  
  
    6.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev 响应消息的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 对于本教程中，选择*New_Migration.InsertCustomerService*，然后单击**确定**。  
  
    7.  在**目标架构的根节点**对话框中，选择*InsertResponse*，然后单击**确定**。  
  
    8.  你将注意到的响应架构之间有些差异生成的两个适配器。 可以按以下方式解释这些差异：  
  
        -   使用基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，如果插入一条记录到表包含一个主键 （并且也是一个标识字段） 的响应为插入操作将返回插入的行的标识字段的值。 因此，符合基于 WCF 的响应消息的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]包含附加*InsertResult*元素。 此元素包含一个数组，其中又包含插入的行的标识字段。  
  
        -   使用 vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，如果表中插入一条记录，该适配器仅返回一个空"成功"元素作为响应消息的一部分。  
  
         因此，将架构映射的方式，从基于 WCF 的响应[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]包含的标识字段的值"复制"为"成功"元素，这是来自 vPrev 的响应消息的一部分的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 可以使用大容量复制 functoid 将元素从一个架构复制到另一个。  
  
         若要使用大容量复制 functoid，从**工具箱**、 大容量复制 functoid 拖放映射器网格。 连接**InsertResult** functoid 源架构中的元素。 同样，连接**成功**functoid 到目标架构中的元素。 下图说明了如何通过提取 functoid 映射的两个元素。  
  
         ![将响应架构映射](../../adapters-and-accelerators/adapter-sql/media/c4a347ae-8d2d-4357-b18d-37f36bef17c7.gif "c4a347ae-8d2d-4357-b18d-37f36bef17c7")  
  
        > [!NOTE]
        >  有关大容量复制 functoid 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=119749](http://go.microsoft.com/fwlink/?LinkId=119749)。  
  
    9. 保存映射。  
  
5.  保存并生成 BizTalk 解决方案。 右键单击解决方案，并依次**生成解决方案**。  
  
6.  部署该解决方案。 右键单击解决方案，并依次**部署解决方案**。  
  
## <a name="next-steps"></a>后续步骤  
 创建 WCF 自定义发送端口，并将其配置为使用你在此步骤中创建的图中所述[步骤 2： 在 BizTalk Server 管理控制台中使用的 SQL 适配器配置业务流程](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程 1： 将 BizTalk 项目迁移到 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)