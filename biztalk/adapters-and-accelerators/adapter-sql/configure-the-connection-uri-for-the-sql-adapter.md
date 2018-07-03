---
title: 配置 SQL 适配器的连接 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6460b22-48e4-4b7e-b82e-151e7dab1e09
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26abea9ca634a04d52e3f84c7be1b1e30a880e78
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969230"
---
# <a name="configure-the-connection-uri-for-the-sql-adapter"></a>配置 SQL 适配器的连接 URI
一个连接 URI 是一个包含参数才能连接到 SQL Server 的连接字符串。 使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须指定要连接到 SQL Server 生成元数据的 URI。 虽然配置发送或接收端口使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您必须指定要连接到 SQL Server 来执行操作的 URI。  

## <a name="enter-the-connection-uri-from-visual-studio"></a>从 Visual Studio 中输入连接 URI  
 从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，可以指定连接 URI 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

### <a name="use-the-consume-adapter-service-add-in"></a>使用使用适配器服务外接程序  

1. 右键单击您的 BizTalk 项目，指向**外**，然后单击**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |             执行的操作             |
   |----------------|------------------------------------|
   | **类别** | 单击**使用适配器服务**。 |
   | **模板**  | 单击**使用适配器服务**。 |


3. 若要启动**使用适配器服务**对话框中，单击**添加**。  

4. 在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sqlBinding**，然后单击**配置**。  

5. 在中**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**列表中，执行下列操作之一：  

   > [!NOTE]
   >  与你登录的 Windows 用户如果要连接到 SQL Server 使用 Windows 身份验证，必须为 SQL Server 中所述添加[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   |  单击此选项  |                                                                                                                                                               执行的操作                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **无**   |                                                                                                                                         使用 Windows 身份验证连接到 SQL Server。                                                                                                                                         |
   | **Windows**  |                                                                                                                                         使用 Windows 身份验证连接到 SQL Server。                                                                                                                                         |
   | **用户名** | 通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。 请注意，用户名和密码区分大小写。 **注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。 |


6. 单击**URI 属性**选项卡，并指定不同的参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  

7. 单击**绑定属性**选项卡，并为指定值的绑定属性，如果有，生成架构之前所需的。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  

8. 单击“确定” 。  

### <a name="use-the-add-adapter-metadata-wizard"></a>使用添加适配器元数据向导  

1. 右键单击 BizTalk 项目，指向**外**，然后单击**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |           执行的操作            |
   |----------------|---------------------------------|
   | **类别** |     单击**将适配器添加**。      |
   | **模板**  | 单击**添加适配器元数据**。 |


3. 单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  

4. 在添加适配器向导中，选择**WCF-SQL**。 选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。  

   > [!IMPORTANT]
   >  如果已配置 BizTalk 中的 WCF SQL 端口，选择从端口**端口**列表。  

5. 单击“下一步” 。  

6. 在中**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**.  

7. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，执行下列任一操作：  

   > [!NOTE]
   >  与你登录的 Windows 用户如果要连接到 SQL Server 使用 Windows 身份验证，必须为 SQL Server 中所述添加[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   |  单击此选项  |                                                                                                                                                               执行的操作                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **无**   |                                                                                                                                         使用 Windows 身份验证连接到 SQL Server。                                                                                                                                         |
   | **Windows**  |                                                                                                                                         使用 Windows 身份验证连接到 SQL Server。                                                                                                                                         |
   | **用户名** | 通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。 请注意，用户名和密码区分大小写。 **注意：** 如果将保留**用户名**并**密码**字段留为空白，适配器将连接到 SQL Server 使用 Windows 身份验证。 |


8. 单击**URI 属性**选项卡，然后指定连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  

9. 单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  

    > [!NOTE]
    >  如果选择现有 WCF-SQL 发送端口，则不需要指定绑定属性。 绑定属性是从发送端口配置中选取。 但是，您可以选择指定如果任何，则需要在设计时的绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定的发送端口配置中的绑定属性的值将适用。  

10. 单击“确定” 。  

## <a name="enter-the-connection-uri-from-the-biztalk-server-administration-console"></a>从 BizTalk Server 管理控制台中输入连接 URI  
 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您可以指定连接 URI 作为 WCF 自定义或 WCF SQL 端口配置的一部分。  

### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a>输入 WCF 自定义端口的连接 URI  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

4. 在中**Wcf-custom 传输属性**对话框中，单击**常规**选项卡。  

5. 在中**地址 (URI)** 文本框中，指定连接到 SQL Server 连接 URI。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  

6. 在中**Wcf-custom 传输属性**对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**sqlBinding**。  

7. 如果要创建的发送端口，请在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡，然后执行下列操作之一：  

   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  

       > [!NOTE]
       >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   -   选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。  

8. 如果要创建接收端口，请在**Wcf-custom 传输属性**对话框中，单击**其他**选项卡，然后执行下列操作之一：  

   -   选择**用户帐户**选项，然后指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  

       > [!NOTE]
       >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   -   选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。  

9. 单击“确定” 。  

### <a name="enter-the-connection-uri-for-the-wcf-sql-port"></a>输入 WCF SQL 端口的连接 URI  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。  

3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

4. 在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加 WCF SQL 适配器，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

5. 在传输属性对话框中，单击**常规**选项卡。  

6. 单击**配置**按钮，并提供连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  

7. 在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。  

   > [!NOTE]
   >  绑定属性将显示根据配置发送端口或接收端口。 例如，与通知相关的绑定属性不可用时配置的发送端口，因为通知的入站的操作并且需要进行接收端口配置。  

8. 如果要创建的发送端口，在传输属性对话框中，单击**凭据**选项卡，然后执行下列操作之一：  

   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  

       > [!NOTE]
       >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

   -   选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。  

9. 如果要创建接收端口，在传输属性对话框中，单击**其他**选项卡，然后执行下列操作之一：  

    -   选择**用户帐户**选项，然后指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  

        > [!NOTE]
        >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  

    -   选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。  

10. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)