---
title: 步骤 5 （本地）：生成插入消息用于向 SalesOrder 表的架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab0bc1a7-8bcd-4110-88e6-4eddf0b57068
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 594fef785d9de6b6fe1c2b750b4f17010d02ecbc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396074"
---
# <a name="step-5-on-premises-generate-the-schema-for-inserting-a-message-inito-salesorder-table"></a>步骤 5 （本地）：生成插入消息用于向 SalesOrder 表的架构
根据业务方案中，发送的 X12 销售订单消息从 Contoso 必须插入到 Northwind **SalesOrder**表，如果订购数量大于 100。 若要将消息插入**SalesOrder**表，则必须生成的架构**插入**表上的操作。 在本主题中，您将创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，并使用[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]生成用于执行架构**插入**上的操作**SalesOrder**表。  

### <a name="to-generate-the-schema-for-insert-operation-on-salesorder-table"></a>若要为 SalesOrder 表上插入操作生成架构  

1. 创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Visual Studio 项目。 从 Visual Studio**文件**菜单上，单击**新建**，然后单击**项目**。 在**新的项目**对话框中，从已安装模板列表中单击**BizTalk 项目**，然后选择**空[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目**。 对于项目名称输入`OrderProcessingDemo`，然后单击**确定**。  

2. 右键单击解决方案资源管理器中的项目名称，指向**外**，然后单击**添加生成的项**。  

3. 在中**添加生成的项**对话框中，选择**使用适配器服务**，然后单击**添加**。 [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]随即打开。  

4. 从**选择绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**。  

5. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表中，执行下列任一操作：  


   |  单击此选项  |                                                                                                                                                               执行的操作                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **无**   |                                                                                                                                          连接到 SQL Server 使用 Windows 身份验证。                                                                                                                                           |
   | **Windows**  |                                                                                                                                          连接到 SQL Server 使用 Windows 身份验证。                                                                                                                                           |
   | **用户名** | 指定的用户名和密码以连接到 SQL Server 通过指定 SQL Server 数据库中定义的用户的凭据。 请注意，用户名和密码是区分大小写。 **注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。 |


6. 单击**URI 属性**选项卡，然后指定连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，请参阅[SQL Server 连接 URI](http://msdn.microsoft.com/library/dd788089.aspx)。  

   > [!NOTE]
   >  如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  
   > 
   > [!NOTE]
   >  如果未指定任何值在 URI 的属性选项卡中，[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]会将 URI 设置为`mssql://.//`。 在这种情况下，适配器连接到的默认数据库和本地计算机上的默认数据库实例。  

7. 在中**配置适配器**对话框中，单击**确定**。 在中**使用适配器服务**对话框中，单击**Connect**。  

8. 从**选择一个类别**框中，展开**表**，然后单击**SalesOrder**表。  

9. 从**可用类别和操作**框中，选择**插入**，单击**添加**，然后单击**确定**。 新项添加到解决方案资源管理器。 架构文件 (**TableOperation.dbo.SalesOrder.xsd**) 是用于在执行插入操作生成的架构**SalesOrder**表。  

## <a name="see-also"></a>请参阅  
 [教程 4：创建混合应用程序使用 BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)