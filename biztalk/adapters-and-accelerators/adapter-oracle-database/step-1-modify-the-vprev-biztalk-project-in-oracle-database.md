---
title: "步骤 1： 修改 vPrev Oracle 数据库中的 BizTalk 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e3e22ac-126b-46ec-a6dc-3421ad721392
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f8911a31eeec34a5508d29ff598a2f7624e5cd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-modify-the-vprev-biztalk-project-in-oracle-database"></a>步骤 1： 修改 vPrev Oracle 数据库中的 BizTalk 项目
![步骤 1，共 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **完成时间：** 10 分钟  
  
 **目标：**向现有 vPrev BizTalk 项目在此步骤中，进行以下更改：  
  
-   生成 SCOTT 上的插入操作的元数据。使用基于 WCF 的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
-   用于执行插入操作执行使用基于 WCF 的插入操作使用请求消息的 vPrev Oracle 数据库适配器将请求消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
-   将使用基于 WCF 的接收响应消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到 vPrev Oracle 数据库适配器的响应消息。  
  
## <a name="prerequisites"></a>先决条件  
  
-   你必须具有 vPrev BizTalk 项目，以执行插入操作上 SCOTT。Oracle 数据库中的 CUSTOMER 表。  
  
## <a name="modify-the-vprev-biztalk-project"></a>修改 vPrev BizTalk 项目  
  
1.  生成 SCOTT 上的插入操作的元数据。使用基于 WCF 的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 你可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成的元数据。  
  
     有关如何生成元数据的说明，请参阅[为 Visual Studio 中的 Oracle 数据库操作获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)。 生成架构后，其名称类似于文件*OracleDBBindingSchema.xsd*添加到 BizTalk 项目。 此文件包含用于发送一条消息，执行插入操作上 SCOTT 架构。使用基于 WCF 的 Oracle 数据库中的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
2.  生成插入操作的元数据还会创建端口绑定文件。 在下一步的步骤中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 Oracle 数据库。 该操作的 SOAP 操作也设置为其生成元数据的操作。 例如，如果生成用于插入操作的元数据，请在发送端口上的 SOAP 操作中的操作名称将"插入"。 但是，该操作将在你为业务流程的一部分可能不同，例如，创建的逻辑发送端口上"Operation_1"。 结果是，当消息发送到使用发送端口的 Oracle 数据库时，你将收到错误。 若要防止此情况，请确保发送端口业务流程中的是为其生成元数据的操作名称相同的逻辑上的操作名称。  
  
     因此，本教程中，如果由于生成用于插入操作的元数据，更改到"插入"的逻辑发送端口操作的名称。  
  
3.  对于请求消息中，生成使用 vPrev 到生成使用基于 WCF 的架构的 Oracle 数据库适配器将架构映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
    1.  将 BizTalk 映射程序添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。  
  
         在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定的名称映射，如**RequestMap.btm**。 单击 **“添加”**。  
  
    2.  从源架构窗格中，单击**打开源架构**。  
  
    3.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev Oracle 数据库适配器请求消息的架构。 对于本教程中，选择*Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*。 单击 **“确定”**。  
  
    4.  在**源架构的根节点**对话框中，选择*插入*单击**确定**。  
  
    5.  从目标架构窗格中，单击**打开目标架构**。  
  
    6.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的请求消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 对于本教程中，选择*Oracle_Migration.OracleDBBindingSchema*。 单击 **“确定”**。  
  
    7.  在**目标架构的根节点**对话框中，选择*插入*单击**确定**。  
  
    8.  下图中所示映射这两个架构中的相应元素。  
  
         ![映射到 Oracle 数据库发送的请求](../../adapters-and-accelerators/adapter-oracle-database/media/4cb59338-40d1-4eb1-bd89-b5a3183959e1.gif "4cb59338-40d1-4eb1-bd89-b5a3183959e1")  
  
    9. 保存映射。  
  
4.  响应消息中，生成使用 vPrev 到生成使用基于 WCF 的架构的 Oracle 数据库适配器将架构映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
    1.  将 BizTalk 映射程序添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。  
  
         在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定的名称映射，如**ResponseMap.btm**。 单击 **“添加”**。  
  
    2.  从源架构窗格中，单击**打开源架构**。  
  
    3.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的响应消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 对于本教程中，选择*Oracle_Migration.OracleDBBindingSchema*。 单击 **“确定”**。  
  
    4.  在**源架构的根节点**对话框中，选择*InsertResponse*单击**确定**。  
  
    5.  从目标架构窗格中，单击**打开目标架构**。  
  
    6.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev Oracle 数据库适配器的响应消息的架构。 对于本教程中，选择*Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*。 单击 **“确定”**。  
  
    7.  在**目标架构的根节点**对话框中，选择*InsertResponse*，然后单击**确定**。  
  
    8.  你将注意到，符合基于 WCF 的响应消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]包含附加*InsertResult*元素。 你必须从架构和映射中删除此*InsertResponse*这两个架构中的元素。  
  
         为此，请从**工具箱**，拖动**字符串左侧 Trim** functoid 并将其放映射器网格。 连接**InsertResponse** functoid 源架构中的元素。 同样，连接**InsertResponse** functoid 到目标架构中的元素。 下图说明了如何通过提取 functoid 映射的两个元素。  
  
         ![从 Oracle 数据库接收的响应映射](../../adapters-and-accelerators/adapter-oracle-database/media/7fe18f5b-100f-4fe2-ac92-c111629d7fe9.gif "7fe18f5b-100f-4fe2-ac92-c111629d7fe9")  
  
        > [!NOTE]
        >  有关详细信息，请参阅**字符串左侧 Trim Functoid** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。
  
    9. 保存映射。  
  
5.  保存并生成 BizTalk 解决方案。 右键单击解决方案，并依次**生成解决方案**。  
  
6.  部署该解决方案。 右键单击解决方案，并依次**部署解决方案**。  
  
## <a name="next-steps"></a>后续步骤  
 创建 WCF 自定义发送端口并将其配置为使用你在此步骤中创建的图中所述[步骤 2： 在 Biztalk Server 管理控制台中使用的 SQL 适配器配置业务流程](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程： 迁移 BizTalk 项目](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)