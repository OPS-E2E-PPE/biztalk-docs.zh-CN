---
title: "步骤 1： 修改与 Siebel 适配器 vPrev BizTalk 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7bd95e2-bd51-420f-8156-6f17cc0e91d6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5465a80fd7b75dcbf7ec864b196d2fd5033cb003
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-modify-the-vprev-biztalk-project-with-the-siebel-adapter"></a>步骤 1： 修改与 Siebel 适配器 vPrev BizTalk 项目
![步骤 1，共 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **完成时间：** 10 分钟  
  
 **目标：**向现有 vPrev BizTalk 项目在此步骤中，进行以下更改：  
  
-   生成使用基于 WCF 的帐户在业务组件上的插入操作的元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
-   用于执行插入操作执行使用基于 WCF 的插入操作使用请求消息的 vPrev Siebel 适配器将请求消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
-   将使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到 vPrev Siebel 适配器的响应消息。  
  
## <a name="prerequisite"></a>前提条件  
  
-   你必须具有要在 Siebel 系统中执行插入操作帐户在业务组件上的 vPrev BizTalk 项目。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>若要修改 vPrev BizTalk 项目  
  
1.  生成使用基于 WCF 的帐户在业务组件上的插入操作的元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 你可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成的元数据。  
  
     有关如何生成元数据的说明，请参阅[获取 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。 生成架构后，其名称类似于文件*SiebelBindingSchema.xsd*添加到 BizTalk 项目。 此文件包含发送一条消息，执行使用基于 WCF 的帐户在业务组件上的插入操作的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
2.  生成插入操作的元数据还会创建端口绑定文件。 在下一步的步骤中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 Siebel 系统。 该操作的 SOAP 操作也设置为其生成元数据的操作。 例如，如果生成用于插入操作的元数据，请在发送端口上的 SOAP 操作中的操作名称将"插入"。 但是，该操作将在你为业务流程的一部分可能不同，例如，创建的逻辑发送端口上"Operation_1"。 结果是，当消息发送到 Siebel 系统使用发送端口时，你将收到错误。 若要防止此情况，请确保发送端口业务流程中的是为其生成元数据的操作名称相同的逻辑上的操作名称。  
  
     因此，本教程中，如果由于生成用于插入操作的元数据，更改到"插入"的逻辑发送端口操作的名称。  
  
3.  对于请求消息中，生成使用生成使用基于 WCF 的架构 vPrev Siebel 适配器将架构映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
    1.  将 BizTalk 映射程序添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。  
  
         在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定的名称映射，如**RequestMap.btm**。 单击 **“添加”**。  
  
    2.  从源架构窗格中，单击**打开源架构**。  
  
    3.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev Siebel 适配器请求消息的架构。 对于本教程中，选择*Siebel_BussComp_Migration.AccountService_Account_x5d*。 单击 **“确定”**。  
  
    4.  在**源架构的根节点**对话框中，选择*插入*，然后单击**确定**。  
  
    5.  从目标架构窗格中，单击**打开目标架构**。  
  
    6.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的请求消息的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 对于本教程中，选择*Siebel_BussComp_Migration.SiebelDBBindingSchema*，然后单击**确定**。  
  
    7.  在**目标架构的根节点**对话框中，选择*插入*，然后单击**确定**。  
  
    8.  映射这两个架构中的以下元素： **Currency_Code**， **Current_Volume**， **Customer_Account_Group**，**位置**，**Main_Phone_Number**，**名称**， **Party_Name**， **Primary_Address_Id**，  
  
    9. 保存映射。  
  
4.  响应消息中，生成使用生成使用基于 WCF 的架构 vPrev Siebel 适配器将架构映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
    1.  将 BizTalk 映射程序添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。  
  
         在添加新项对话框中，从左窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定的名称映射，如**ResponseMap.btm**。 单击 **“添加”**。  
  
    2.  从源架构窗格中，单击**打开源架构**。  
  
    3.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的响应消息的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 对于本教程中，选择*Siebel_BussComp_Migration.SiebelDBBindingSchema*。 单击 **“确定”**。  
  
    4.  在**源架构的根节点**对话框中，选择*InsertResponse*单击**确定**。  
  
    5.  从目标架构窗格中，单击**打开目标架构**。  
  
    6.  在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev Siebel 适配器的响应消息的架构。 对于本教程中，选择*Siebel_BussComp_Migration.AccountService_Account_x5d*。 单击 **“确定”**。  
  
    7.  在**目标架构的根节点**对话框中，选择*InsertResponse*单击**确定**。  
  
    8.  映射**数组： 字符串**到源架构中的元素**公开： 字符串**在目标架构中下, 图中所示的元素。  
  
         ![映射适配器版本之间的响应消息](../../adapters-and-accelerators/adapter-siebel/media/6352035b-79c0-4850-a8f7-e4f6581c8532.gif "6352035b-79c0-4850-a8f7-e4f6581c8532")  
  
    9. 保存映射。  
  
5.  保存并生成 BizTalk 解决方案。 右键单击解决方案，并依次**生成解决方案**。  
  
6.  部署该解决方案。 右键单击解决方案，并依次**部署解决方案**。  
  
## <a name="next-steps"></a>后续步骤  
 创建 WCF 自定义发送端口并将其配置为使用你在此步骤中创建的图中所述[步骤 2： 在 BizTalk Server 管理控制台，以使用 Oracle 数据库适配器中配置业务流程](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程 2： 迁移中 Siebel 的 BizTalk 项目](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)