---
title: 配置 SQL 适配器的凭据登录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c20e177-0e64-4df3-a3dd-dca3fcf314db
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1644132db366e22e0c55fcd293bcfa82506a0c82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370017"
---
# <a name="configure-the-sign-in-credentials-for-the-sql-adapter"></a>配置 SQL 适配器的凭据登录
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]要求适配器客户端提供客户端凭据。 若要使用 SQL Server 用户进行身份验证和建立连接，适配器将使用这些凭据。  

 适配器客户端可以提供的客户端凭据同时使用时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]以及何时使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 当使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，生成元数据所需的凭据。 当使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，凭据所需 SQL 服务器上执行操作。  

 本部分提供有关指定在客户端凭据的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

## <a name="enter-credentials-from-visual-studio"></a>从 Visual Studio 中输入凭据  
 从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，可以指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

### <a name="using-consume-adapter-service-add-in"></a>使用使用适配器服务外接程序  

1.  右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。  

2.  在中**添加生成的项**对话框框中，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  

3.  若要启动**使用适配器服务**对话框中，单击**添加**。  

4.  在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sqlBinding**，然后单击**配置**。  

5.  在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**列表中，执行下列操作之一：  

    > [!NOTE]
    >  与你登录的 Windows 用户如果要连接到 SQL Server 使用 Windows 身份验证，必须为 SQL Server 中所述添加[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

    |单击此选项|执行的操作|  
    |----------------|----------------|  
    |**无**|使用 Windows 身份验证连接到 SQL Server。|  
    |**Windows**|使用 Windows 身份验证连接到 SQL Server。|  
    |**用户名**|指定的用户名和密码以连接到 SQL Server 通过指定 SQL Server 数据库中定义的用户的凭据。 请注意，用户名和密码是区分大小写。 **注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。|  

6.  单击“确定” 。  

### <a name="using-add-adapter-metadata-wizard"></a>使用添加适配器元数据向导  

1. 右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |           执行的操作            |
   |----------------|---------------------------------|
   | **类别** |     单击**将适配器添加**。      |
   | **模板**  | 单击**添加适配器元数据**。 |


3. 单击 **“添加”**。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]随即打开。  

4. 在添加适配器向导中，选择**WCF-SQL**。 选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。  

   > [!IMPORTANT]
   >  如果已配置 BizTalk 中的 WCF SQL 端口，选择从端口**端口**列表。  

5. 单击“下一步” 。  

6. 在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sqlBinding**，然后单击**配置**。  

7. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**列表中，执行下列操作之一：  

   > [!NOTE]
   >  与你登录的 Windows 用户如果要连接到 SQL Server 使用 Windows 身份验证，必须为 SQL Server 中所述添加[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   |  单击此选项  |                                                                                                                                                               执行的操作                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **无**   |                                                                                                                                         使用 Windows 身份验证连接到 SQL Server。                                                                                                                                         |
   | **Windows**  |                                                                                                                                         使用 Windows 身份验证连接到 SQL Server。                                                                                                                                         |
   | **用户名** | 指定的用户名和密码以连接到 SQL Server 通过指定 SQL Server 数据库中定义的用户的凭据。 请注意，用户名和密码是区分大小写。 **注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。 |


8. 单击“确定” 。  

## <a name="enter-credentials-from-the-biztalk-server-administration-console"></a>从 BizTalk Server 管理控制台中输入凭据  
 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，可以为 WCF 自定义或 WCF SQL 端口配置的一部分指定的凭据。  

### <a name="enter-credentials-for-the-wcf-custom-port"></a>WCF 自定义端口输入凭据  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

4. 如果要创建的发送端口，请在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡，然后执行下列操作之一：  

   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码是区分大小写。  

       > [!NOTE]
       >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   -   选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。  

5. 如果要创建接收端口，请在**Wcf-custom 传输属性**对话框中，单击**其他**选项卡，然后执行下列操作之一：  

   -   选择**用户帐户**选项，然后指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码是区分大小写。  

       > [!NOTE]
       >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   -   选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。  

6. 单击“确定” 。  

### <a name="enter-credentials-for-the-wcf-sql-port"></a>输入凭据的 WCF SQL 端口  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。  

3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

4. 在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加 WCF SQL 适配器，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

5. 如果要创建的发送端口，在传输属性对话框中，单击**凭据**选项卡，然后执行下列操作之一：  

   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码是区分大小写。  

       > [!NOTE]
       >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   -   选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。  

6. 如果要创建接收端口，在传输属性对话框中，单击**其他**选项卡，然后执行下列操作之一：  

   -   选择**用户帐户**选项，然后指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码是区分大小写。  

       > [!NOTE]
       >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   -   选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。  

7. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)