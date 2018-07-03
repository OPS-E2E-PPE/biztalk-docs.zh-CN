---
title: 在 BizTalk 中使用 WCF-SAP 适配器配置端口 |Microsoft Docs
description: 创建用于发送或接收来自 SAP 使用 mySAP 适配器的 BizTalk 适配器包 (BAP) 中的消息的 WCF SAP 端口
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 420683f8-2516-4c65-895d-fe535824d450
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a80c778e34505755a147dccf48e50ea9ea3a18d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992670"
---
# <a name="configure-a-port-using-the-wcf-sap-adapter"></a>使用 WCF-SAP 适配器配置端口
本主题提供有关如何配置 WCF SAP 说明发送和接收端口执行 SAP 系统使用的出站和入站操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="prerequisites"></a>必要條件  
是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组或 BizTalk Operators 组。 详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，并[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a>部署适配器将消息发送到 SAP  
完成以下步骤以配置 WCF SAP 发送端口将消息发送到 SAP 系统使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。  
  
3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
4. 展开你想要部署的应用程序[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
5. 右键单击**发送端口**，依次指向**新建**，并指向你想要根据 BizTalk Server 和 SAP 系统之间的通信的模式配置的端口的类型。  
  
6. 在中**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。  
  
7. 从**类型**下拉列表中，选择你前面，添加的 WCF-SAP 适配器，然后单击**配置**。  
  
8. 在传输属性对话框中，请执行以下操作：  
  
   1. 单击**常规**选项卡上，单击**配置**按钮，并为连接参数提供值。 有关连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
   2. 上**常规**选项卡上，在**操作**文字框中，键入操作的操作。 请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)有关每个操作的操作的列表。 例如，若要调用 RFC_CUSTOMER_GET 则操作将是：  
  
      ```  
      http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
      ```  
  
   3. 单击**绑定**选项卡，指定的绑定公开的属性值[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
      > [!NOTE]
      >  绑定属性将显示根据配置发送端口或接收端口。 例如，绑定属性与入站操作不可用时配置的发送端口，因为的入站的操作需要接收端口配置。  
  
   4. 单击**凭据**选项卡上，执行下列操作之一：  
  
   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SAP 系统。  
  
   -   选择**使用单一登录**选项，并指定关联 SSO 应用程序。  
  
        有关与 BizTalk Server 相关的安全性的详细信息，请参阅[SAP 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。  
  
        若要返回到**发送端口属性**对话框中，单击**确定**。  
  
9. 从**发送处理程序**下拉列表中，选择**BizTalkServerApplication**。  
  
10. 如果您选择创建**静态单向发送端口**在步骤 5 中，指定发送管道。 从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
11. 如果您选择创建**静态要求响应端口**在步骤 5 中，指定发送和接收管道。  
  
    1.  从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
    2.  从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
12. 单击“确定” 。  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a>部署适配器从 SAP 接收消息  
完成以下步骤以配置 WCF SAP 接收端口用于接收来自 SAP 系统使用消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。  
  
3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
4. 展开你想要部署的应用程序[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
5. 右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**或者**请求响应接收端口**具体取决于BizTalk Server 和 SAP 系统之间的通信模式。  
  
6. 在中**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。  
  
7. 上**接收位置**选项卡上，单击**新建**。 **接收位置属性**对话框随即出现。  
  
8. 在中**接收位置属性**对话框框中，执行以下操作：  
  
   1.  指定接收位置的名称。  
  
   2.  从**类型**下拉列表中，选择你前面，添加的 WCF-SAP 适配器，然后单击**配置**。  
  
9. 在传输属性对话框中，请执行以下操作：  
  
   1. 单击**常规**选项卡上，单击**配置**按钮，并为连接参数提供值。 有关连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
   2. 单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**sapBinding**。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
      > [!NOTE]
      >  绑定属性将显示根据配置发送端口或接收端口。 例如，绑定属性与入站操作不可用时配置的发送端口，因为的入站的操作需要接收端口配置。  
  
   3. 单击**其他**选项卡，然后执行下列操作之一：  
  
   4. 选择**用户帐户**，并指定用户名和密码以连接到 SAP 系统。  
  
   5. 选择**从获取凭据的关联应用程序**选项，并指定关联应用程序。  
  
       有关与 BizTalk Server 相关的安全性的详细信息，请参阅[SAP 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。  
  
       单击**确定**回到**接收位置属性**对话框。  
  
10. 从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。  
  
11. 如果您选择创建**单向接收端口**在步骤 5 中，指定接收管道。 从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
12. 如果您选择创建**请求响应接收端口**在步骤 5 中，指定发送和接收管道。  
  
    1.  从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
    2.  从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
13. 单击**确定**中**接收位置属性**对话框。  
  
14. 单击**确定**中**接收端口属性**对话框。

## <a name="see-also"></a>另请参阅
[手动配置到 SAP 适配器的物理端口绑定](manually-configure-a-physical-port-binding-to-the-sap-adapter.md)