---
title: 第 1 步：修改 vPrev BizTalk 项目使用 SQL 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25ad959b-2818-47b8-9a09-3681abb75887
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b54953af2bf3e1a3783dd05f8a98b4ac6bfd32a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367843"
---
# <a name="step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter"></a>第 1 步：修改 vPrev BizTalk 项目使用 SQL 适配器
![3 的第 1 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **若要完成的时间：** 10 分钟。  
  
 **目标：** 在此步骤中，向现有 vPrev BizTalk 项目进行以下更改：  
  
- 生成上使用基于 WCF 的 Customer 表的插入操作的元数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
- 执行插入操作执行 Insert 操作使用基于 WCF 的使用 vPrev SQL 适配器添加到请求消息的请求消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
- 使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到使用 vPrev SQL 适配器接收响应消息。  
  
## <a name="prerequisites"></a>先决条件  
 必须具有 SQL Server 数据库中执行插入操作的客户表上的 vPrev BizTalk 项目。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>若要修改 vPrev BizTalk 项目  
  
1. 生成上使用基于 WCF 的 Customer 表的插入操作的元数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成元数据。  
  
    有关如何生成元数据的说明，请参阅[获取元数据用于在 Visual Studio 中使用 SQL 适配器的 SQL Server 操作](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。 生成架构后，具有类似名称的文件*TableOperation.dbo.Customer.xsd*添加到 BizTalk 项目。 此文件包含发送消息来使用基于 WCF 的在 SQL Server 数据库中执行插入操作在 Customer 表的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
2. 生成插入操作的元数据还会创建端口绑定文件。 在下一步中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 SQL Server 数据库。 该操作的 SOAP 操作也设置为其生成元数据的操作。 例如，如果生成插入操作的元数据，请在发送端口上的 SOAP 操作中的操作名称将"Insert"。 但是，该操作命名时创建的业务流程的一部分可能会有所不同，例如，在逻辑发送端口上"Operation_1"。 因此时将消息发送到 SQL Server 数据库使用的发送端口，, 则会出错。 若要防止此情况，请确保发送端口在业务流程中的为其生成元数据的操作名称相同的操作名称上的逻辑。  
  
    因此，对于本教程中，由于生成插入操作的元数据，更改到"插入"的逻辑发送端口操作名称。  
  
3. 请求消息映射使用 vPrev SQL 数据库适配器添加到使用基于 WCF 的生成的架构生成的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
   1. 将 BizTalk 映射器添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**外**，然后单击**新项**。  
  
       在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定映射的名称，如**RequestMap.btm**。 单击 **“添加”**。  
  
   2. 在源架构窗格中，单击**打开源架构**。  
  
   3. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择用于 vPrev SQL 适配器的请求消息架构。 对于本教程中，选择*New_Migration.InsertCustomerService*，然后单击**确定**。  
  
   4. 在中**源架构的根节点**对话框中，选择*插入*，然后单击**确定**。  
  
   5. 从目标架构窗格中，单击**打开目标架构**。  
  
   6. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择用于基于 WCF 的请求消息架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 对于本教程中，选择*New_Migration.TableOperation.dbo.Customer*，然后单击**确定**。  
  
   7. 在中**目标架构的根节点**对话框中，选择*插入*，然后单击**确定**。  
  
   8. 下图中所示映射这两个架构中的相应元素。  
  
       ![映射请求架构](../../adapters-and-accelerators/adapter-sql/media/850bbf52-fc3e-42c5-b879-51c6e39a502d.gif "850bbf52-fc3e-42c5-b879-51c6e39a502d")  
  
   9. 保存该映射。  
  
4. 响应消息中，将映射生成使用 vPrev SQL 适配器添加到使用基于 WCF 的生成的架构的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
   1. 将 BizTalk 映射器添加到 BizTalk 项目。 右键单击 BizTalk 项目，指向**外**，然后单击**新项**。  
  
       在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。 从右窗格中，选择**映射**。 指定映射的名称，如**ResponseMap.btm**，然后单击**添加**。  
  
   2. 在源架构窗格中，单击**打开源架构**。  
  
   3. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择用于基于 WCF 的响应消息架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 对于本教程中，选择*New_Migration.TableOperation.dbo.Customer*，然后单击**确定**。  
  
   4. 在中**源架构的根节点**对话框中，选择*InsertResponse*，然后单击**确定**。  
  
   5. 从目标架构窗格中，单击**打开目标架构**。  
  
   6. 在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择用于 vPrev 的响应消息架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 对于本教程中，选择*New_Migration.InsertCustomerService*，然后单击**确定**。  
  
   7. 在中**目标架构的根节点**对话框中，选择*InsertResponse*，然后单击**确定**。  
  
   8. 您会注意到一些差别的响应架构生成的两个适配器。 可以按如下所示解释这些差异：  
  
      - 使用基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，如果插入的记录到表中包含主键 （并且也是标识字段） 的响应为插入操作将返回插入的行的标识字段的值。 因此，与基于 WCF 的响应消息的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]包含额外*InsertResult*元素。 此元素包含一个数组，其中又包含用于插入的行的标识字段。  
  
      - 使用 vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，如果表中插入一条记录，适配器仅返回空"成功"元素作为响应消息的一部分。  
  
        因此，架构映射的方式，从基于 WCF 的响应[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]包含标识字段的值"复制"为"成功"元素，它是来自 vPrev 的响应消息的一部分的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 可以使用批量复制 functoid 将从一个架构的元素复制到另一个。  
  
        若要从使用批量复制 functoid**工具箱**、 批量复制 functoid 拖放映射器网格。 连接**InsertResult**至该 functoid 将源架构中的元素。 同样，连接**成功**functoid 到目标架构中的元素。 下图说明了如何通过提取 functoid 映射的两个元素。  
  
        ![映射响应架构](../../adapters-and-accelerators/adapter-sql/media/c4a347ae-8d2d-4357-b18d-37f36bef17c7.gif "c4a347ae-8d2d-4357-b18d-37f36bef17c7")  
  
      > [!NOTE]
      >  有关批量复制 functoid 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=119749 ](http://go.microsoft.com/fwlink/?LinkId=119749)。  
  
   9. 保存该映射。  
  
5. 保存并生成 BizTalk 解决方案。 右键单击解决方案，然后依次**生成解决方案**。  
  
6. 部署解决方案。 右键单击解决方案，然后依次**部署解决方案**。  
  
## <a name="next-steps"></a>后续步骤  
 创建 WCF 自定义发送端口，并将其配置为使用在此步骤中创建的地图中所述[步骤 2:在使用 SQL 适配器的 BizTalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 1:将 BizTalk 项目迁移到 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)