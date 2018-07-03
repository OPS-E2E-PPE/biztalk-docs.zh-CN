---
title: 步骤 5 （本地）： 生成插入消息用于向 SalesOrder 表的架构 |Microsoft Docs
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
ms.openlocfilehash: afdca03f5ad8639705ac40171e4142a12c07d757
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973470"
---
# <a name="step-5-on-premises-generate-the-schema-for-inserting-a-message-inito-salesorder-table"></a>步骤 5 （本地）： 生成插入消息用于向 SalesOrder 表的架构
根据业务方案中，发送的 X12 销售订单消息从 Contoso 必须插入到 Northwind **SalesOrder**表，如果订购数量大于 100。 若要将消息插入**SalesOrder**表，则必须生成的架构**插入**表上的操作。 在本主题中，您将创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，并使用[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]生成用于执行架构**插入**上的操作**SalesOrder**表。  

### <a name="to-generate-the-schema-for-insert-operation-on-salesorder-table"></a>生成用于在 SalesOrder 表中执行插入操作的架构  

1. 创建一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Visual Studio 项目。 从 Visual Studio**文件**菜单上，单击**新建**，然后单击**项目**。 在**新的项目**对话框中，从已安装模板列表中单击**BizTalk 项目**，然后选择**空[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目**。 对于项目名称输入`OrderProcessingDemo`，然后单击**确定**。  

2. 右键单击解决方案资源管理器中的项目名称，指向**外**，然后单击**添加生成的项**。  

3. 在中**添加生成的项**对话框中，选择**使用适配器服务**，然后单击**添加**。 此时[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]会打开。  

4. 从**选择绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**。  

5. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表中，执行下列任一操作：  


   |  单击此选项  |                                                                                                                                                               执行的操作                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **无**   |                                                                                                                                          使用 Windows 身份验证连接至 SQL Server。                                                                                                                                           |
   | **Windows**  |                                                                                                                                          使用 Windows 身份验证连接至 SQL Server。                                                                                                                                           |
   | **用户名** | 通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。 请注意，用户名和密码区分大小写。 **注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。 |


6. 单击**URI 属性**选项卡，然后指定连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，请参阅[SQL Server 连接 URI](http://msdn.microsoft.com/library/dd788089.aspx)。  

   > [!NOTE]
   >  如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  
   > 
   > [!NOTE]
   >  如果不在“URI 属性”选项卡中指定任何值，[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]会将 URI 设置为 `mssql://.//`。 在此类情况下，适配器将连接至本地计算机上的默认数据库和默认数据库实例。  

7. 在中**配置适配器**对话框中，单击**确定**。 在中**使用适配器服务**对话框中，单击**Connect**。  

8. 从**选择一个类别**框中，展开**表**，然后单击**SalesOrder**表。  

9. 从**可用类别和操作**框中，选择**插入**，单击**添加**，然后单击**确定**。 新项将添加至解决方案资源管理器中。 架构文件 (**TableOperation.dbo.SalesOrder.xsd**) 是用于在执行插入操作生成的架构**SalesOrder**表。  

## <a name="see-also"></a>请参阅  
 [教程 4： 创建混合应用程序使用 BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)