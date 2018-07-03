---
title: 连接到 SQL Server Visual Studio 中使用添加适配器元数据向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2169722d-beba-4d96-a54b-54986ece9bf8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6de95e2e6906a840e0e41d013f6c1e1e0a73a8d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981398"
---
# <a name="connect-to-sql-server-in-visual-studio-using-add-adapter-metadata-wizard"></a>连接到 SQL Server Visual Studio 中使用添加适配器元数据向导
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]还会显示为 BizTalk 适配器，因此，您可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]来为你想要使用的适配器的 SQL 服务器上执行的操作生成架构。  

## <a name="connecting-to-sql-server-using-add-adapter-metadata-wizard"></a>连接到 SQL Server 使用添加适配器元数据向导  
 执行以下步骤连接到 SQL Server 使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

#### <a name="to-connect-to-sql-server"></a>若要连接到 SQL Server  

1. 若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：  

   1. 创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  

   2. 右键单击解决方案资源管理器中的项目名称，指向**外**，然后单击**添加生成的项**。  

   3. 在中**添加生成的项**对话框框中，执行以下操作：  


      |    使用此选项    |           执行的操作            |
      |----------------|---------------------------------|
      | **类别** |     单击**将适配器添加**。      |
      | **模板**  | 单击**添加适配器元数据**。 |


   4. 单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  

   5. 在添加适配器向导中，选择**WCF-SQL**。 选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。  

      > [!IMPORTANT]
      >  如果已配置 BizTalk 中的 WCF SQL 端口，选择从端口**端口**列表。  

   6. 单击“下一步” 。  

2. 从**选择绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**。  

3. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表中，执行下列任一操作：  

   > [!NOTE]
   >  与你登录的 Windows 用户如果要连接到 SQL Server 使用 Windows 身份验证，必须为 SQL Server 中所述添加[连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   |  单击此选项  |                                                                                                                                                               执行的操作                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **无**   |                                                                                                                                         使用 Windows 身份验证连接到 SQL Server。                                                                                                                                         |
   | **Windows**  |                                                                                                                                         使用 Windows 身份验证连接到 SQL Server。                                                                                                                                         |
   | **用户名** | 通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。 请注意，用户名和密码区分大小写。 **注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。 |


4. 单击**URI 属性**选项卡，然后指定连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建的 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  

   > [!NOTE]
   >  如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  
   > 
   > [!NOTE]
   >  如果不在“URI 属性”选项卡中指定任何值，[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会将 URI 设置为 `mssql://.//`。 在此类情况下，适配器将连接至本地计算机上的默认数据库和默认数据库实例。  

5. 单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。 有关绑定属性，请参阅详细信息[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  

   > [!NOTE]
   >  如果您正在生成元数据中使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]并且选择了现有 WCF-SQL 发送端口，不需要指定绑定属性。 绑定属性是从发送端口配置中选取。 但是，您可以选择指定如果任何，则需要在设计时的绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定的发送端口配置中的绑定属性的值将适用。  

6. 单击“确定” 。  

7. 单击 **“连接”**。 建立连接后，连接状态显示为**已连接**。  

    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。 图形用户界面是适用于[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

    ![连接到 SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")  

    [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在 SQL Server 执行各种操作的不同节点。 例如，**过程**节点包含可用于连接到的数据库的所有过程。 同样，**表**节点包含在连接到数据库和可以对表执行的操作的所有表。 有关这些节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)。  

## <a name="see-also"></a>请参阅  
 [连接到 Visual Studio 中使用适配器服务外接程序使用的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)