---
title: 第 1 步：修改 vPrev BizTalk 项目使用 Siebel 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd95e2-bd51-420f-8156-6f17cc0e91d6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68a3bc43e3f8f946652b75768c1846a388a28c13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370899"
---
# <a name="step-1-modify-the-vprev-biztalk-project-with-the-siebel-adapter"></a>第 1 步：修改 vPrev BizTalk 项目使用 Siebel 适配器
![3 的第 1 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **若要完成的时间：** 10 分钟。  
  
 **目标：** 在此步骤中，向现有 vPrev BizTalk 项目进行以下更改：  
  
- 为使用基于 WCF 的帐户业务组件上的插入操作生成元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
- 执行插入操作执行 Insert 操作使用基于 WCF 的使用 vPrev Siebel 适配器添加到请求消息的请求消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
- 使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到 vPrev Siebel 适配器的响应消息。  
  
## <a name="prerequisite"></a>先决条件  
  
-   必须具有要在 Siebel 系统中执行插入操作帐户业务组件上的 vPrev BizTalk 项目。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>若要修改 vPrev BizTalk 项目  
  
1. 为使用基于 WCF 的帐户业务组件上的插入操作生成元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成元数据。  
  
    有关如何生成元数据的说明，请参阅[获取 Siebel 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。 生成架构后，具有类似名称的文件*SiebelBindingSchema.xsd*添加到 BizTalk 项目。 此文件包含发送消息来执行插入操作中使用基于 WCF 的帐户业务组件上的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
2. 生成插入操作的元数据还会创建端口绑定文件。 在下一步中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 Siebel 系统。 该操作的 SOAP 操作也设置为其生成元数据的操作。 例如，如果生成插入操作的元数据，请在发送端口上的 SOAP 操作中的操作名称将"Insert"。 但是，该操作命名时创建的业务流程的一部分可能会有所不同，例如，在逻辑发送端口上"Operation_1"。 因此时将消息发送到 Siebel 系统使用的发送端口，, 则会出错。 若要防止此情况，请确保发送端口在业务流程中的为其生成元数据的操作名称相同的操作名称上的逻辑。  
  
    因此，对于本教程中，由于生成插入操作的元数据，更改到"插入"的逻辑发送端口操作名称。  
  
3. 请求消息映射使用 vPrev Siebel 适配器添加到使用基于 WCF 的生成的架构生成的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
   1. 将 BizTalk 映射器添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**外**，然后单击**新项**。  
  
       在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定映射的名称，如**RequestMap.btm**。 单击 **“添加”**。  
  
   2. 在源架构窗格中，单击**打开源架构**。  
  
   3. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev Siebel 适配器的请求消息的架构。 对于本教程中，选择*Siebel_BussComp_Migration.AccountService_Account_x5d*。 单击“确定” 。  
  
   4. 在中**源架构的根节点**对话框中，选择*插入*，然后单击**确定**。  
  
   5. 从目标架构窗格中，单击**打开目标架构**。  
  
   6. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的请求消息的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 对于本教程中，选择*Siebel_BussComp_Migration.SiebelDBBindingSchema*，然后单击**确定**。  
  
   7. 在中**目标架构的根节点**对话框中，选择*插入*，然后单击**确定**。  
  
   8. 映射这两个架构中的下列元素：**Currency_Code**， **Current_Volume**， **Customer_Account_Group**，**位置**， **Main_Phone_Number**， **名称**， **Party_Name**， **Primary_Address_Id**，  
  
   9. 保存该映射。  
  
4. 响应消息中，将映射生成使用 vPrev Siebel 适配器添加到使用基于 WCF 的生成的架构的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
   1. 将 BizTalk 映射器添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**外**，然后单击**新项**。  
  
       在添加新项对话框中，从左窗格中，选择**地图文件**。 从右窗格中，选择**映射**。 指定映射的名称，如**ResponseMap.btm**。 单击 **“添加”**。  
  
   2. 在源架构窗格中，单击**打开源架构**。  
  
   3. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的响应消息的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 对于本教程中，选择*Siebel_BussComp_Migration.SiebelDBBindingSchema*。 单击“确定” 。  
  
   4. 在中**源架构的根节点**对话框中，选择*InsertResponse*然后单击**确定**。  
  
   5. 从目标架构窗格中，单击**打开目标架构**。  
  
   6. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev Siebel 适配器的响应消息的架构。 对于本教程中，选择*Siebel_BussComp_Migration.AccountService_Account_x5d*。 单击“确定” 。  
  
   7. 在中**目标架构的根节点**对话框中，选择*InsertResponse*然后单击**确定**。  
  
   8. 地图**数组： 字符串**到源架构中的元素**公开： 字符串**在目标架构中下, 图中所示的元素。  
  
       ![映射响应消息在适配器各版本之间](../../adapters-and-accelerators/adapter-siebel/media/6352035b-79c0-4850-a8f7-e4f6581c8532.gif "6352035b-79c0-4850-a8f7-e4f6581c8532")  
  
   9. 保存该映射。  
  
5. 保存并生成 BizTalk 解决方案。 右键单击解决方案，然后依次**生成解决方案**。  
  
6. 部署解决方案。 右键单击解决方案，然后依次**部署解决方案**。  
  
## <a name="next-steps"></a>后续步骤  
 创建一个 WCF 自定义发送端口并将其配置为使用在此步骤中创建的地图中所述[步骤 2:若要使用 Oracle 数据库适配器的 BizTalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 2：在 Siebel 的 BizTalk 项目迁移](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)