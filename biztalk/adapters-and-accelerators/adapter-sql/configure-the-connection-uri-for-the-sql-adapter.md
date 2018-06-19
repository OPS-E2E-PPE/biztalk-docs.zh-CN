---
title: 配置 SQL 适配器的连接 URI |Microsoft 文档
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
ms.openlocfilehash: 9959a88f9799730cb60d2b05358f226b31d0f84c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226789"
---
# <a name="configure-the-connection-uri-for-the-sql-adapter"></a>配置 SQL 适配器的连接 URI
连接 URI 是包含连接到 SQL Server 所需的参数的连接字符串。 在使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须指定要连接到 SQL Server 生成的元数据的 URI。 虽然配置发送或接收端口使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你必须指定要连接到 SQL Server 以执行操作的 URI。  
  
## <a name="enter-the-connection-uri-from-visual-studio"></a>从 Visual Studio 中输入连接 URI  
 从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你可以指定连接 URI 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
### <a name="use-the-consume-adapter-service-add-in"></a>使用使用适配器服务外接程序  
  
1.  右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  
  
3.  若要启动**使用适配器服务**对话框中，单击**添加**。  
  
4.  在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sqlBinding**，然后单击**配置**。  
  
5.  在**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**列表中，执行下列操作之一：  
  
    > [!NOTE]
    >  中所述，如果你要连接到 SQL Server 使用 Windows 身份验证，必须到 SQL Server 中添加与你登录的 Windows 用户[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
    |单击此链接|执行的操作|  
    |----------------|----------------|  
    |**无**|使用 Windows 身份验证连接到 SQL Server。|  
    |**Windows**|使用 Windows 身份验证连接到 SQL Server。|  
    |**用户名**|通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。 请注意，用户名和密码区分大小写。 **注意：** 如果你离开**用户名**和**密码**为空白字段，该适配器将连接到 SQL Server 使用 Windows 身份验证。|  
  
6.  单击**URI 属性**选项卡，然后指定不同的参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  
  
7.  单击**绑定属性**选项卡，然后指定绑定属性的值如果有的话，生成架构之前所需的。 有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
8.  单击 **“确定”**。  
  
### <a name="use-the-add-adapter-metadata-wizard"></a>使用添加适配器元数据向导  
  
1.  右键单击 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**添加适配器**。|  
    |**模板**|单击**添加适配器元数据**。|  
  
3.  单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  
  
4.  在添加适配器向导中，选择**WCF SQL**。 选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。  
  
    > [!IMPORTANT]
    >  如果你已经在 BizTalk 中配置 WCF SQL 端口，选择从端口**端口**列表。  
  
5.  单击 **“下一步”**。  
  
6.  在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**.  
  
7.  在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，执行下列其中一项：  
  
    > [!NOTE]
    >  中所述，如果你要连接到 SQL Server 使用 Windows 身份验证，必须到 SQL Server 中添加与你登录的 Windows 用户[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
    |单击此链接|执行的操作|  
    |----------------|----------------|  
    |**无**|使用 Windows 身份验证连接到 SQL Server。|  
    |**Windows**|使用 Windows 身份验证连接到 SQL Server。|  
    |**用户名**|通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。 请注意，用户名和密码区分大小写。 **注意：** 如果你离开**用户名**和**密码**为空白字段，该适配器将连接到 SQL Server 使用 Windows 身份验证。|  
  
8.  单击**URI 属性**选项卡上，然后指定连接参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  
  
9. 单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。 有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
    > [!NOTE]
    >  如果你选择现有 WCF SQL 发送端口，你不需要指定的绑定属性。 绑定属性是从发送端口配置中选取。 但是，你可以选择指定所需在设计时，如果任何绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定中发送端口配置的绑定属性的值将适用。  
  
10. 单击 **“确定”**。  
  
## <a name="enter-the-connection-uri-from-the-biztalk-server-administration-console"></a>从 BizTalk Server 管理控制台中输入连接 URI  
 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你可以指定连接 URI 作为 WCF 自定义或 WCF SQL 端口配置的一部分。  
  
### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a>输入 WCF 自定义端口的连接 URI  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
3.  在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
4.  在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。  
  
5.  在**地址 (URI)** 文本框中，指定连接 URI 来连接到 SQL Server。 有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  
  
6.  在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**sqlBinding**。  
  
7.  如果您创建发送端口，则在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，然后执行下列操作之一：  
  
    -   选择**不使用单一登录**选项，并指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  
  
        > [!NOTE]
        >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
    -   选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。  
  
8.  如果您创建接收端口，则在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，然后执行下列操作之一：  
  
    -   选择**用户帐户**选项，并指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  
  
        > [!NOTE]
        >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
    -   选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。  
  
9. 单击 **“确定”**。  
  
### <a name="enter-the-connection-uri-for-the-wcf-sql-port"></a>输入 WCF SQL 端口的连接 URI  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。  
  
3.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
4.  在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加了 WCF SQL 适配器，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
5.  在传输属性对话框中，单击**常规**选项卡。  
  
6.  单击**配置**按钮，然后提供的连接参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  
  
7.  在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。  
  
    > [!NOTE]
    >  绑定属性显示的配置发送端口或接收端口。 例如，与通知相关的绑定属性不可用时配置发送端口，因为通知是入站的操作，需要接收端口配置。  
  
8.  如果您创建发送端口，则在传输属性对话框中，单击**凭据**选项卡，然后执行下列操作之一：  
  
    -   选择**不使用单一登录**选项，并指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  
  
        > [!NOTE]
        >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
    -   选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。  
  
9. 如果您创建接收端口，则在传输属性对话框中，单击**其他**选项卡，然后执行下列操作之一：  
  
    -   选择**用户帐户**选项，并指定用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  
  
        > [!NOTE]
        >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
    -   选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。  
  
10. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
[开发具有 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)