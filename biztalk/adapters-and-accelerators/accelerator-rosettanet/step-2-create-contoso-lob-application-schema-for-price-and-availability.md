---
title: 步骤 2： 创建 Contoso LOB 应用程序架构为价格与可用性项目使用 BizTalk 编辑器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOB schemas
ms.assetid: 70e26dc9-4299-4d30-8f8b-5cc3469a2025
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f899a6614ea5d5d28c555be1b39e72b5880fe3ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999326"
---
# <a name="step-2-creating-the-contoso-lob-application-schemas-for-the-price-and-availability-project-using-biztalk-editor"></a>步骤 2： 创建 Contoso LOB 应用程序架构为价格与可用性项目使用 BizTalk 编辑器
在此步骤中，将生成用于查询 Contoso ERP 系统中特定产品的价格与可用性的架构。 通过使用 BizTalk server 的 Microsoft® SQL 适配器生成此架构。  

### <a name="to-update-the-sql-stored-procedure-for-schema-generation"></a>更新 SQL 存储过程以生成架构  

1.  单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  

2.  在 Microsoft SQL Server Management Studio 中，展开**数据库**，展开**Contoso**，展开**可编程性**，然后展开**存储过程**.  

3.  右键单击**dbo。SP_GetInventoryForProductID**，然后单击**修改**。  

4.  在查询窗口中，紧接在“for xml auto”后面插入逗号、空格和“xmldata”。 该代码行应为如下所示：  

    ```  
    for xml auto, xmldata  
    ```  

5.  单击**Execute**若要将所做的更改保存到存储过程。  

    > [!NOTE]
    >  保持 Microsoft SQL Server Management Studio 为打开状态，以执行下一个过程。  

### <a name="to-create-the-contoso-price-and-availability-schema"></a>创建 Contoso 价格与可用性架构  

1. 打开 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 中的 Contoso 解决方案。  

2. 在解决方案资源管理器中右键单击**ContosoPriceAndAvailability**项目，指向**添加**，然后单击**添加生成的项**。  

3. 在添加生成的项对话框中，使用**添加适配器元数据**处于选中状态的左窗格中，单击**添加适配器元数据**在右窗格中，然后单击**添加**。  

4. 上**添加适配器向导**页上，选择**SQL**从列表中的已注册的适配器，然后单击**下一步**。  

5. 上**数据库信息**页上，单击**设置**。  

6. 在数据链接属性对话框中，在**选择或输入服务器名称**框中，键入**localhost**。 选择**使用 Windows NT 集成安全性**。 有关**选择在服务器上的数据库**，选择**Contoso**数据库从数据库列表。 单击“确定” 。  

7. 上**数据库信息**页上，单击**下一步**。  

8. 上**架构信息**页上，执行以下操作：  


   |                使用此选项                 |              执行的操作              |
   |-----------------------------------------|--------------------------------------|
   |          **目标命名空间**           | 类型**<http://Contoso.com/Price>**。 |
   |        **选择端口类型**         |        选择**发送端口**。         |
   | **请求文档根元素名称**  |      类型**rootPriceRequest**。      |
   | **响应文档根元素名称** |     类型**rootPriceResponse**。      |


9. 单击“下一步” 。  

10. 上**语句类型信息**页上，选择**存储过程**，然后单击**下一步**。  

11. 上**语句的信息**页上，对于**\<选择一个存储的过程\>**，选择**SP_GetInventoryForProductID**从下拉列表。 单击**Generate**，然后单击**下一步**。  

12. 上**完成 SQL 传输架构生成向导**页上，单击**完成**将架构导入到 ContosoPriceAndAvailability BizTalk 项目。  

13. 在解决方案资源管理器，右键单击生成的架构 (SQLService_Price.xsd)，单击**重命名**，然后键入**ContosoPriceAndAvailability.xsd**作为架构的新名称。 单击 **“输入”**。  

14. 在 ContosoPriceAndAvailability 架构的属性窗口中，设置**类型名称**属性设置为**ContosoPriceSchema**。  

15. 默认情况下[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]创建名为 BizTalk 业务流程**BizTalk Orchestration.odx**。 右键单击此业务流程，然后依次**删除**因为不需要此业务流程。 在弹出窗口，该值指示将永久删除该业务流程中，单击**确定**。  

16. Microsoft SQL Server Management Studio 中删除`xmldata`谓词和逗号`SP_GetInventoryForProductID`存储过程，在上一步骤中，添加它，然后单击**Execute**。  

## <a name="see-also"></a>请参阅  
 [步骤 3：使用 BizTalk 映射器为价格和可用性项目创建 Contoso LOB 应用程序映射](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)