---
title: 连接到 Visual Studio 使用添加适配器元数据向导中的 Oracle 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 726b3f82-887c-407a-bb9f-dcb9443155b0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbf023a306e7caabeb3e207f90831167f46e8009
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214829"
---
# <a name="connect-to-oracle-database-in-visual-studio-using-add-adapter-metadata-wizard"></a>连接到 Oracle 数据库在 Visual Studio 中使用添加适配器元数据向导
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]名称还公开为 BizTalk 适配器，因此，你可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要为你想要使用该适配器对 Oracle 数据库执行的操作生成架构。  
  
 本主题将说明了如何使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
## <a name="connecting-to-an-oracle-database-using-the-add-adapter-metadata-wizard"></a>连接到 Oracle 数据库使用添加适配器元数据向导  
 执行以下步骤以连接到 Oracle 数据库使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
#### <a name="to-connect-to-an-oracle-database"></a>若要连接到 Oracle 数据库  
  
1.  若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：  
  
    1.  右键单击解决方案资源管理器中的项目，指向**添加**，然后单击**添加生成的项**。  
  
    2.  在**添加生成的项**对话框框中，执行以下操作：  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**类别**|单击**添加适配器**。|  
        |**模板**|单击**添加适配器元数据**。|  
  
    3.  单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  
  
    4.  在添加适配器元数据向导中，选择**WCF OracleDB**。 选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。  
  
        > [!IMPORTANT]
        >  如果你已经在 BizTalk 中配置 WCF OracleDB 端口，选择从端口**端口**列表。  
  
    5.  单击 **“下一步”**。  
  
2.  从**选择的绑定**下拉列表中，选择**oracleDBBinding**单击**配置**。  
  
3.  在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Oracle 数据库。  
  
    1.  若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。 请确保指定的用户名和密码以连接到 Oracle 数据库时遵循以下注意事项：  
  
        -   **用户名称**。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。 对 Oracle 数据库的用户名称是区分大小写。 您应该确保你提供到的 Oracle 用户名[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在 Oracle 数据库所需的情况下。 通常，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写形式:"SCOTT"。  
  
        -   **密码**。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]保留在打开对 Oracle 数据库的连接时输入的密码的值的大小写。 对于发行版 10g 和更早版本，Oracle 系统上的密码是不区分大小写。  
  
    2.  若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。  
  
4.  单击**URI 属性**选项卡，然后指定连接参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  
  
5.  单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。 例如，如果你想要针对 POLLINGSTMT 操作，则必须设置**PollingStatement**绑定属性。 有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。
  
    > [!NOTE]
    >  如果您正在生成元数据中使用添加适配器元数据向导并且你选择现有的 WCF OracleDB 发送端口，你需要指定的绑定属性。 绑定属性是从发送端口配置中选取。 但是，你可以选择指定所需在设计时，如果任何绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定中发送端口配置的绑定属性的值将适用。  
  
6.  单击 **“确定”**。  
  
7.  单击 **“连接”**。 建立连接后，连接状态将显示为**已连接**。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。  
  
     ![使用适配器服务连接的对话框](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")  
  
## <a name="see-also"></a>另请参阅  
 [连接到 Oracle 数据库在 Visual Studio 中使用添加适配器服务引用](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md)   
 [连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)