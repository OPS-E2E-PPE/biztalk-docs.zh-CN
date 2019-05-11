---
title: 在 BizTalk 中使用 WCF 自定义适配器和 SAP 适配器配置端口 |Microsoft Docs
description: 创建用于发送或接收来自 SAP 使用 mySAP 适配器的 BizTalk 适配器包 (BAP) 中的消息的 WCF 自定义端口
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3962456-e9ac-4575-8266-b35e892dd428
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 304fa647f0b50549c6f5779f2579d8d2f473c9ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373851"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sap-adapter"></a>使用 WCF 自定义适配器和 SAP 适配器配置端口
本主题说明了如何配置 WCF 自定义发送和接收端口，以执行对 SAP 系统使用的出站和入站操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="prerequisites"></a>先决条件  
是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组或 BizTalk Operators 组。 详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，并[最低安全用户权限](../../core/minimum-security-user-rights.md)。 
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a>部署适配器将消息发送到 SAP  
完成以下步骤以配置 WCF 自定义发送端口将消息发送到 SAP 系统使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 展开你想要部署的应用程序[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
4. 右键单击**发送端口**，依次指向**新建**，并指向你想要根据 BizTalk Server 和 SAP 系统之间的通信的模式配置的端口的类型。  
  
5. 在中**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。  
  
6. 从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
7. 在中**Wcf-custom 传输属性**对话框框中，执行以下操作：  
  
   1. 单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定为 SAP 系统的连接 URI。 有关连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
   2. 上**常规**选项卡上，在**操作**文字框中，键入操作的操作。 请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)有关每个操作的操作的列表。 例如，若要调用 RFC_CUSTOMER_GET 则操作将是：  
  
      ```  
      http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
      ```  
  
   3. 单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**sapBinding**。 您可以指定不同的绑定属性公开的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
   4. 单击**凭据**选项卡上，执行下列操作之一：  
  
      -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SAP 系统。  
  
      -   选择**使用单一登录**选项，并指定关联 SSO 应用程序。  
  
           有关与 BizTalk Server 相关的安全性的详细信息，请参阅[SAP 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。
  
           若要返回到**发送端口属性**对话框中，单击**确定**。  
  
8. 从**发送处理程序**下拉列表中，选择**BizTalkServerApplication**。  
  
9. 如果在步骤 4 中选择静态单向发送端口，指定发送管道。 从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
10. 如果选择了**静态要求响应端口**在步骤 4 中，指定发送和接收管道。  
  
    1.  从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
    2.  从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
11. 单击“确定” 。  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a>部署适配器从 SAP 接收消息
完成以下步骤以配置 WCF 自定义接收端口用于接收来自 SAP 系统使用消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 展开你想要部署的应用程序[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
4. 右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**或者**请求响应接收端口**具体取决于BizTalk Server 和 SAP 系统之间的通信模式。  
  
5. 在中**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。  
  
6. 上**接收位置**选项卡上，单击**新建**。 **接收位置属性**对话框随即出现。  
  
7. 在中**接收位置属性**对话框框中，执行以下操作：  
  
   1.  指定接收位置的名称。  
  
   2.  从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
8. 在中**Wcf-custom 传输属性**对话框框中，执行以下操作：  
  
   1.  单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定为 SAP 系统的连接 URI。 有关连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
   2.  单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**sapBinding**。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
   3.  单击**他人**选项卡，然后执行下列操作之一：  
  
       -   选择**用户帐户**，并指定用户名和密码以连接到 SAP 系统。  
  
       -   选择**从获取凭据的关联应用程序**选项，并指定关联应用程序。  
  
            有关与 BizTalk Server 相关的安全性的详细信息，请参阅[SAP 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。
  
            单击**确定**回到**接收位置属性**对话框。  
  
9. 从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。  
  
10. 如果选择了**单向接收端口**在步骤 4 中，指定接收管道。 从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
11. 如果选择了**请求响应接收端口**在步骤 4 中，指定发送和接收管道。  
  
    1.  从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
    2.  从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
12. 单击**确定 i**n**接收位置属性**对话框。  
  
13. 单击**确定**中**接收端口属性**对话框。  
  
## <a name="see-also"></a>请参阅  
[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)