---
title: "连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d4fa2bd-ac9e-41b1-8fea-e6a41cbfd1a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69ccf497c9546f0695565e3e9f46ec2536b42ef8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in"></a>连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server
[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]安装时安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]加载在计算机上安装的所有 WCF 自定义绑定。 若要连接到 SQL Server 使用基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 BizTalk 项目，你必须使用**sqlbinding**。  
  
 本主题将说明了如何使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
## <a name="connecting-to-sql-server-using-consume-adapter-service-add-in"></a>连接到 SQL Server 使用使用适配器服务外接程序  
 执行以下步骤以连接到 SQL Server 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
#### <a name="to-connect-to-sql-server"></a>若要连接到 SQL Server  
  
1.  若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：  
  
    1.  创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
    2.  右键单击解决方案资源管理器中的项目名称，指向**添加**，然后单击**添加生成的项**。  
  
    3.  在**添加生成的项**对话框框中，执行以下操作：  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**类别**|单击**使用适配器服务**。|  
        |**模板**|单击**使用适配器服务**。|  
  
    4.  单击 **“添加”**。 此时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会打开。  
  
2.  从**选择的绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**。  
  
3.  在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表中，执行下列其中一项：  
  
    > [!NOTE]
    >  中所述，如果你要连接到 SQL Server 使用 Windows 身份验证，必须到 SQL Server 中添加与你登录的 Windows 用户[连接到 SQL Server 和 SQL 适配器一起使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
    |单击此链接|执行的操作|  
    |----------------|----------------|  
    |**无**|使用 Windows 身份验证连接到 SQL Server。|  
    |**Windows**|使用 Windows 身份验证连接到 SQL Server。|  
    |**用户名**|通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。 请注意，用户名和密码区分大小写。 **注意：**如果你离开**用户名**和**密码**为空白字段，该适配器将连接到 SQL Server 使用 Windows 身份验证。|  
  
4.  单击**URI 属性**选项卡上，然后指定连接参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  
  
    > [!NOTE]
    >  如果连接参数包含任何保留的字符，则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。 但是，如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。  
  
    > [!NOTE]
    >  如果不在“URI 属性”选项卡中指定任何值，[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会将 URI 设置为 `mssql://.//`。 在此类情况下，适配器将连接至本地计算机上的默认数据库和默认数据库实例。  
  
5.  单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。  
  
6.  单击 **“确定”**。  
  
7.  单击 **“连接”**。 建立连接后，连接状态将显示为**已连接**。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。  
  
     ![连接到 SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")  
  
     [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在 SQL Server 执行的各种操作的不同节点。 例如，**过程**节点包含可用于连接到的数据库的所有过程。 同样，**表**节点包含在连接到的数据库和可以对表执行的操作中的所有表。 有关这些节点的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)。  
  
## <a name="see-also"></a>另请参阅  
 [连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)