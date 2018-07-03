---
title: 步骤 1： 修改 vPrev BizTalk 项目中 Oracle 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e3e22ac-126b-46ec-a6dc-3421ad721392
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5d55a5535d1f3f2234198d08393a314b1a304e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010566"
---
# <a name="step-1-modify-the-vprev-biztalk-project-in-oracle-database"></a>步骤 1： 修改 vPrev BizTalk 项目中 Oracle 数据库
![3 的第 1 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 到现有 vPrev BizTalk 项目，在此步骤中，进行以下更改：  
  
- 生成 SCOTT 上的插入操作的元数据。使用基于 WCF 的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
- 执行插入操作执行 Insert 操作使用基于 WCF 的使用 vPrev Oracle 数据库适配器为请求消息的请求消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
- 使用基于 WCF 的接收响应消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到 vPrev Oracle 数据库适配器的响应消息。  
  
## <a name="prerequisites"></a>必要條件  
  
-   必须具有 vPrev BizTalk 项目，以执行插入操作 SCOTT。Oracle 数据库中的 CUSTOMER 表。  
  
## <a name="modify-the-vprev-biztalk-project"></a>修改 vPrev BizTalk 项目  
  
1. 生成 SCOTT 上的插入操作的元数据。使用基于 WCF 的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成元数据。  
  
    有关如何生成元数据的说明，请参阅[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)。 生成架构后，具有类似名称的文件*OracleDBBindingSchema.xsd*添加到 BizTalk 项目。 此文件包含发送消息来执行插入操作 SCOTT 的架构。使用基于 WCF 的 Oracle 数据库中的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
2. 生成插入操作的元数据还会创建端口绑定文件。 在下一步中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 Oracle 数据库。 该操作的 SOAP 操作也设置为其生成元数据的操作。 例如，如果生成插入操作的元数据，请在发送端口上的 SOAP 操作中的操作名称将"Insert"。 但是，该操作命名时创建的业务流程的一部分可能会有所不同，例如，在逻辑发送端口上"Operation_1"。 因此时将消息发送到 Oracle 数据库使用的发送端口，, 则会出错。 若要防止此情况，请确保发送端口在业务流程中的为其生成元数据的操作名称相同的操作名称上的逻辑。  
  
    因此，对于本教程中，由于生成插入操作的元数据，更改到"插入"的逻辑发送端口操作名称。  
  
3. 请求消息映射使用 vPrev Oracle 数据库适配器添加到使用基于 WCF 的生成的架构生成的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
   1. 将 BizTalk 映射器添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**外**，然后单击**新项**。  
  
       在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定映射的名称，如**RequestMap.btm**。 单击 **“添加”**。  
  
   2. 在源架构窗格中，单击**打开源架构**。  
  
   3. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev Oracle 数据库适配器的请求消息的架构。 对于本教程中，选择*Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*。 单击“确定” 。  
  
   4. 在中**源架构的根节点**对话框中，选择*插入*然后单击**确定**。  
  
   5. 从目标架构窗格中，单击**打开目标架构**。  
  
   6. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的请求消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 对于本教程中，选择*Oracle_Migration.OracleDBBindingSchema*。 单击“确定” 。  
  
   7. 在中**目标架构的根节点**对话框中，选择*插入*然后单击**确定**。  
  
   8. 下图中所示映射这两个架构中的相应元素。  
  
       ![将映射到 Oracle 数据库发送的请求](../../adapters-and-accelerators/adapter-oracle-database/media/4cb59338-40d1-4eb1-bd89-b5a3183959e1.gif "4cb59338-40d1-4eb1-bd89-b5a3183959e1")  
  
   9. 保存映射。  
  
4. 响应消息中，将映射生成使用 vPrev Oracle 数据库适配器添加到使用基于 WCF 的生成的架构的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
   1. 将 BizTalk 映射器添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**外**，然后单击**新项**。  
  
       在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定映射的名称，如**ResponseMap.btm**。 单击 **“添加”**。  
  
   2. 在源架构窗格中，单击**打开源架构**。  
  
   3. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的响应消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 对于本教程中，选择*Oracle_Migration.OracleDBBindingSchema*。 单击“确定” 。  
  
   4. 在中**源架构的根节点**对话框中，选择*InsertResponse*然后单击**确定**。  
  
   5. 从目标架构窗格中，单击**打开目标架构**。  
  
   6. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev Oracle 数据库适配器的响应消息的架构。 对于本教程中，选择*Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*。 单击“确定” 。  
  
   7. 在中**目标架构的根节点**对话框中，选择*InsertResponse*，然后单击**确定**。  
  
   8. 您将注意到，与基于 WCF 的响应消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]包含额外*InsertResult*元素。 你必须从架构和映射中删除这*InsertResponse*这两个架构中的元素。  
  
       为此，请从**工具箱**，拖动**字符串左侧空格裁剪**functoid 并将其放在映射器网格。 连接**InsertResponse**至该 functoid 将源架构中的元素。 同样，连接**InsertResponse** functoid 到目标架构中的元素。 下图说明了如何通过提取 functoid 映射的两个元素。  
  
       ![将映射从 Oracle 数据库接收的响应](../../adapters-and-accelerators/adapter-oracle-database/media/7fe18f5b-100f-4fe2-ac92-c111629d7fe9.gif "7fe18f5b-100f-4fe2-ac92-c111629d7fe9")  
  
      > [!NOTE]
      >  有关详细信息，请参阅**字符串左剪裁 Functoid** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。
  
   9. 保存映射。  
  
5. 保存并生成 BizTalk 解决方案。 右键单击解决方案，然后依次**生成解决方案**。  
  
6. 部署该解决方案。 右键单击解决方案，然后依次**部署解决方案**。  
  
## <a name="next-steps"></a>后续步骤  
 创建一个 WCF 自定义发送端口并将其配置为使用在此步骤中创建的地图中所述[步骤 2： 使用 SQL 适配器的 Biztalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程： 迁移 BizTalk 项目](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)