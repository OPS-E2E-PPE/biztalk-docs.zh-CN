---
title: 连接到 SQL Server Visual Studio 中使用添加适配器服务引用插件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fc3b824-d20b-4531-81f3-89b4a1ff3216
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cef87522e76a0997166f4c9415b48805361d0ba0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369935"
---
# <a name="connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference-plug-in"></a>连接到 SQL Server Visual Studio 中使用添加适配器服务引用插件
若要连接到 SQL Server 使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在.NET 编程解决方案中，必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 本主题说明了如何使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  

## <a name="connecting-to-sql-server-using-add-adapter-service-reference-plug-in"></a>连接到 SQL Server 使用添加适配器服务引用插件  
 执行以下步骤连接到 SQL Server 使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  

#### <a name="to-connect-to-sql-server"></a>若要连接到 SQL Server  

1. 若要使用连接[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]编程解决方案中：  

   1. 创建的项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  

   2. 右键单击解决方案资源管理器中的项目，然后单击**添加适配器服务引用**。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]随即打开。  

2. 从**选择绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**。  

3. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表中，执行下列任一操作：  

   > [!NOTE]
   >  与你登录的 Windows 用户如果要连接到 SQL Server 使用 Windows 身份验证，必须为 SQL Server 中所述添加[连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   |  单击此选项  |                                                                                                                                                               执行的操作                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **无**   |                                                                                                                                         使用 Windows 身份验证连接到 SQL Server。                                                                                                                                         |
   | **Windows**  |                                                                                                                                         使用 Windows 身份验证连接到 SQL Server。                                                                                                                                         |
   | **用户名** | 指定的用户名和密码以连接到 SQL Server 通过指定 SQL Server 数据库中定义的用户的凭据。 请注意，用户名和密码是区分大小写。 **注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。 |


4. 单击**URI 属性**选项卡，然后指定连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建的 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  

   > [!NOTE]
   >  如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  
   > 
   > [!NOTE]
   >  如果未指定任何值在 URI 的属性选项卡中，[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会将 URI 设置为`mssql://.//`。 在这种情况下，适配器连接到的默认数据库和本地计算机上的默认数据库实例。  

5. 单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。  

6. 单击“确定” 。  

7. 单击 **“连接”**。 建立连接后，连接状态显示为**已连接**。  

    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。 图形用户界面是适用于[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  

    ![连接到 SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")  

    [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]显示包含可以在 SQL Server 执行各种操作的不同节点。 例如，**过程**节点包含可用于连接到的数据库的所有过程。 同样，**表**节点包含在连接到数据库和可以对表执行的操作的所有表。 有关这些节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)。  

## <a name="see-also"></a>请参阅  
 [连接到 Visual Studio 中使用适配器服务外接程序使用的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)