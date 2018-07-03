---
title: 使用 WCF 自定义适配器和 Oracle 数据库适配器配置端口 |Microsoft Docs
description: 创建 WCF 自定义发送和接收端口，以在 BizTalk Server 中使用 Oracle DB 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c99ff526-ad97-4095-812f-0ce88b071e7f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 513d848d9bf95e75b8b6b983dde7019ce24ecf46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006478"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter"></a>使用 WCF 自定义适配器和 Oracle 数据库适配器配置端口
如何配置 WCF 自定义发送和接收端口，以执行对 Oracle 数据库使用的出站和入站操作[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。  
  
## <a name="prerequisites"></a>必要條件  
是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组或 BizTalk Operators 组。 请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，并[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)有关权限的指南。
  
## <a name="deploy-adapters-for-sending-messages-to-an-oracle-database"></a>部署用于将消息发送到 Oracle 数据库适配器  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 展开你想要部署的应用程序[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
4. 右键单击**发送端口**，依次指向**新建**，并指向你想要根据之间的通信的模式配置的端口类型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 Oracle 数据库。  
  
5. 在中**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。  
  
6. 从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
7. 在中**Wcf-custom 传输属性**对话框框中，执行以下操作：  
  
   1. 单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定 Oracle 数据库的连接 URI。 有关连接 URI 的详细信息，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  
  
   2. 上**常规**选项卡上，在**操作**文字框中，键入操作的操作。 请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)有关每个操作的操作的列表。 例如，要调用在 Oracle 数据库中的 HR 架构下的雇员表的插入操作的操作是：  
  
      ```  
      http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEE/Select  
      ```  
  
   3. 单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**oracleDBBinding**。 您可以指定不同的绑定属性公开的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  
  
   4. 单击**凭据**选项卡上，执行下列操作之一：  
  
      - 选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Oracle 数据库。  
  
        -   若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。  
  
        -   若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。  
  
      - 选择**使用单一登录**选项，并指定关联 SSO 应用程序。  
  
        有关与 BizTalk Server 相关的安全性的详细信息，请参阅[Oracle 数据库适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)。  
  
        若要返回到**发送端口属性**对话框中，单击**确定**。  
  
8. 从**发送处理程序**下拉列表中，选择**BizTalkServerApplication**。  
  
9. 如果选择了**静态单向发送端口**在步骤 4 中，指定发送管道。 从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
10. 如果选择了**静态要求响应端口**在步骤 4 中，指定发送和接收管道。  
  
    1.  从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
    2.  从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
11. 单击“确定” 。  
  
## <a name="deploy-adapters-for-receiving-messages-from-an-oracle-database"></a>部署用于从 Oracle 数据库接收消息的适配器  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 展开你想要部署的应用程序[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
4. 右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**或者**请求响应接收端口**，具体取决于BizTalk Server 和 Oracle 数据库之间的通信模式。  
  
5. 在中**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。  
  
6. 上**接收位置**选项卡上，单击**新建**。 **接收位置属性**对话框随即出现。  
  
7. 在中**接收位置属性**对话框框中，执行以下操作：  
  
   1.  指定接收位置的名称。  
  
   2.  从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
8. 在中**Wcf-custom 传输属性**对话框框中，执行以下操作：  
  
   1. 单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定 Oracle 数据库的连接 URI。 有关连接 URI 的详细信息，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  
  
   2. 单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**oracleDBBinding**。 您可以指定不同的绑定属性公开的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  
  
   3. 单击**他人**选项卡，然后执行下列操作之一：  
  
      - 选择**用户帐户**，并指定用户名和密码以连接到 Oracle 数据库。  
  
        -   若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。  
  
        -   若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。  
  
      - 选择**从获取凭据的关联应用程序**选项，并指定关联应用程序。  
  
        有关与 BizTalk Server 相关的安全性的详细信息，请参阅[Oracle 数据库适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)。
  
        若要返回到**接收位置属性**对话框中，单击**确定**。  
  
9. 从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。  
  
10. 如果选择了**单向接收端口**在步骤 4 中，指定接收管道。 从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
11. 如果选择了**请求响应接收端口**在步骤 4 中，指定发送和接收管道。  
  
    1.  从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
    2.  从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
12. 在中**接收位置属性**对话框中，单击**确定**。  
  
13. 在中**接收端口属性**对话框中，单击**确定**。  
  
## <a name="see-also"></a>请参阅  
[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)   
 [连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)