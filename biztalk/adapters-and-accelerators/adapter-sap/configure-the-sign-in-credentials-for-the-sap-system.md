---
title: 配置 SAP 系统的凭据登录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb41106b-b673-4fcf-a56e-6208e3113469
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c788bf8c98fc06511ce692c84600f040443dd993
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989166"
---
# <a name="configure-the-sign-in-credentials-for-the-sap-system"></a>配置 SAP 系统的凭据登录
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要求适配器客户端提供客户端凭据。 SAP 系统与用户进行身份验证和建立连接，适配器将使用这些凭据。  

 适配器客户端可以在设计时提供客户端凭据这两个或运行时。 在设计时，需要凭据以生成元数据。 在运行时，需要凭据来执行 SAP 系统的操作。 本部分提供有关在设计时和运行的时指定客户端凭据的信息。  

## <a name="enter-the-client-credentials-at-design-time"></a>在设计时输入的客户端凭据  
 对于设计时，你可以指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

### <a name="enter-credentials-using-consume-adapter-service-add-in"></a>输入使用适配器服务外接程序使用的凭据  

1.  右键单击您的 BizTalk 项目，指向**外**，然后单击**添加生成的项**。  

2.  在中**添加生成的项**对话框框中，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  

3.  若要启动**使用适配器服务**对话框中，单击**添加**。  

4.  在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sapBinding**，然后单击**配置**。  

5.  在中**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 SAP 系统。  

6.  单击“确定” 。  

### <a name="enter-credentials-using-add-adapter-metadata-wizard"></a>输入凭据使用添加适配器元数据向导  

1. 右键单击您的 BizTalk 项目，指向**外**，然后单击**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |           执行的操作            |
   |----------------|---------------------------------|
   | **类别** |     单击**将适配器添加**。      |
   | **模板**  | 单击**添加适配器元数据**。 |


3. 单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  

4. 在添加适配器向导中，选择**WCF-SAP**。 选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。  

   > [!IMPORTANT]
   >  如果已配置 BizTalk 中的 WCF SAP 端口，选择从端口**端口**列表。  

5. 单击“下一步” 。  

6. 在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sapBinding**，然后单击**配置**。  

7. 在中**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 SAP 系统。  

8. 单击“确定” 。  

## <a name="enter-client-credentials-at-run-time"></a>在运行时输入客户端凭据  
 对于运行时中，你可以指定客户端凭据中的 WCF 自定义或 WCF SAP 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

### <a name="enter-credentials-for-the-wcf-custom-port"></a>WCF 自定义端口输入凭据  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

4. 为发送端口，在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，执行下列操作之一：  

   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SAP 系统。  

   -   选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。  

5. 为接收端口，在**Wcf-custom 传输属性**对话框中，单击**其他**选项卡上，执行下列操作之一：  

   -   选择**用户帐户**选项，然后指定用户名和密码以连接到 SAP 系统。  

   -   选择**从获取凭据的关联应用程序**选项，并指定关联应用程序。  

6. 单击“确定” 。  

### <a name="enter-credentials-for-the-wcf-sap-port"></a>为 WCF SAP 端口输入凭据  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。  

3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

4. 在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加的 WCF-SAP 适配器，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

5. 如果要创建的发送端口，在传输属性对话框中，单击**凭据**选项卡上，执行下列操作之一：  

   1.  选择**不使用单一登录**选项，然后指定用户名和密码以连接到 SAP 系统。  

   2.  选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。  

6. 如果要创建接收端口，请在**Wcf-custom 传输属性**对话框中，单击**其他**选项卡上，执行下列操作之一：  

   1.  选择**用户帐户**选项，然后指定用户名和密码以连接到 SAP 系统。  

   2.  选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。  

7. 单击“确定” 。  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 此外支持企业单一登录 (SSO) 系统。 SSO 选项仅适用于 BizTalk 方案中，在其中[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]可识别的 SSO 关联应用程序。 有关与 BizTalk Server 相关的安全性的详细信息，请参阅[SAP 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。

## <a name="see-also"></a>请参阅  
[生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)