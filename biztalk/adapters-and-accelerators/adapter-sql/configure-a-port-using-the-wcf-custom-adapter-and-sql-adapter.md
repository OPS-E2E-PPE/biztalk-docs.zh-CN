---
title: 配置端口使用 BizTalk 中的 WCF 自定义适配器和 SQL 适配器 |Microsoft 文档
description: 创建 WCF 自定义发送和接收要在 BizTalk Server 中使用 SQL Server 适配器的端口
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d44d9932-0a5e-4072-a480-2f8dc544ca79
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c2a47cf267bd3316600ad68a241a204090f3da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226029"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter"></a>配置使用 WCF 自定义适配器和 SQL 适配器的端口
配置 WCF 自定义发送和接收端口到执行 SQL Server 使用的出站和入站操作步骤[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="prerequisites"></a>先决条件  
使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员或 BizTalk 操作员组。 有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。 
  
## <a name="deploy-adapters-to-send-messages-to-sql-server"></a>部署适配器，以将消息发送到 SQL Server  
 执行以下步骤以配置 WCF 自定义发送端口将消息发送到 SQL Server 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。    
 
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  展开你想要部署的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
4.  右键单击**发送端口**，指向**新建**，然后指向你想要根据之间的通信模式配置的端口的类型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 SQL Server。  
  
5.  在**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。  
  
6.  从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
7.  在**WCF 自定义传输属性**对话框框中，执行以下操作：  
  
    1.  单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定 SQL Server 连接 URI。 有关连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  
  
    2.  上**常规**选项卡上，在**操作**文本框中，键入操作的操作。 请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)有关每个操作的操作的列表。 例如，要调用的 SQL Server 数据库中的表上的插入操作的操作是：  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
        > [!NOTE]
        >  员工是 SQL Server 数据库中表的名称。  
  
    3.  单击**绑定**选项卡上，并从**绑定类型**列表中，选择**sqlBinding**。 你可以指定不同的绑定属性公开的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
    4.  单击**凭据**选项卡，，然后执行下列操作之一：  
  
        -   选择**不使用单一登录**选项，以及指定的用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  
  
            > [!NOTE]
            >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 和 SQL 适配器一起使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
        -   选择**使用单一登录**选项，，然后指定关联企业单一登录 (SSO) 应用程序。  
  
             有关与 BizTalk Server 安全性的详细信息，请参阅[SQL 适配器与 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。  
  
    5.  若要返回到**发送端口属性**对话框中，单击**确定**。  
  
8.  从**发送处理程序**列表中，选择**BizTalkServerApplication**。  
  
9. 如果你选择了**静态单向发送端口**在步骤 4 中，指定发送管道。 从**发送管道**列表中，选择对应于 XMLTransmit 管道。  
  
10. 如果你选择了**静态请求-响应端口**在步骤 4 中，指定发送和接收管道。  
  
    1.  从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
    2.  从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
11. 单击 **“确定”**。  
  
## <a name="deploy-adapters-to-receive-messages-from-sql-server"></a>部署适配器从 SQL Server 接收消息
 执行以下步骤来配置 WCF 自定义接收端口来接收消息从 SQL Server 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  展开你想要部署的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
4.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**或**请求响应接收端口**，具体取决于模式之间的通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 SQL Server。  
  
5.  在**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。  
  
6.  上**接收位置**选项卡上，单击**新建**。 **接收位置属性**对话框随即出现。  
  
7.  在**接收位置属性**对话框框中，执行以下操作：  
  
    1.  指定接收位置的名称。  
  
    2.  从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
8.  在**WCF 自定义传输属性**对话框框中，执行以下操作：  
  
    1.  单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定 SQL Server 连接 URI。 有关连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  
  
    2.  单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**sqlBinding**。 你可以指定不同的绑定属性公开的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
    3.  单击**行为**选项卡以设置事务的隔离级别。 有关设置事务隔离级别的详细信息，请参阅[配置事务隔离级别和与 SQL 的事务超时](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)。  
  
    4.  单击**其他**选项卡，然后执行下列操作之一：  
  
        -   选择**用户帐户**，并指定的用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  
  
            > [!NOTE]
            >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。 中所述执行此操作之前，必须将与你登录 Windows 用户添加到 SQL Server[连接到 SQL Server 和 SQL 适配器一起使用 Windows 身份验证](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
        -   选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。  
  
             有关实施与安全性的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[SQL 适配器与 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。  
  
    5.  若要返回到**接收位置属性**对话框中，单击**确定**。  
  
9. 从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。  
  
10. 如果你选择了**单向接收端口**在步骤 4 中，指定接收管道。 从**接收管道**列表中，选择对应于 XMLReceive 管道。  
  
11. 如果你选择了**请求响应接收端口**在步骤 4 中，指定发送和接收管道。  
  
    1.  从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
    2.  从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
12. 在**接收位置属性**对话框中，单击**确定**。  
  
13. 在**接收端口属性**对话框中，单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)