---
title: 配置 SAP 系统的凭据登录 |Microsoft 文档
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
ms.openlocfilehash: 2a6ace75f66bb7fdd4cfb3362f7d019ab99d73bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217805"
---
# <a name="configure-the-sign-in-credentials-for-the-sap-system"></a>配置 SAP 系统的凭据登录
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]需要适配器客户端提供客户端凭据。 适配器使用这些凭据进行身份验证与 SAP 系统用户并建立连接。  
  
 适配器客户端可以在设计时提供客户端凭据这两个或运行时间。 在设计时，需要使用凭据才能生成元数据。 在运行时，需要凭据在 SAP 系统上执行操作。 本部分提供有关在设计时和运行的时指定客户端凭据的信息。  
  
## <a name="enter-the-client-credentials-at-design-time"></a>在设计时输入的客户端凭据  
 对于设计时，你可以指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
### <a name="enter-credentials-using-consume-adapter-service-add-in"></a>输入使用适配器服务外接程序中使用的凭据  
  
1.  右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  
  
3.  若要启动**使用适配器服务**对话框中，单击**添加**。  
  
4.  在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sapBinding**，然后单击**配置**。  
  
5.  在**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 SAP 系统。  
  
6.  单击 **“确定”**。  
  
### <a name="enter-credentials-using-add-adapter-metadata-wizard"></a>输入凭据使用添加适配器元数据向导  
  
1.  右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**添加适配器**。|  
    |**模板**|单击**添加适配器元数据**。|  
  
3.  单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  
  
4.  在添加适配器向导中，选择**WCF SAP**。 选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。  
  
    > [!IMPORTANT]
    >  如果你已经在 BizTalk 中配置 WCF SAP 端口，选择从端口**端口**列表。  
  
5.  单击 **“下一步”**。  
  
6.  在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**sapBinding**，然后单击**配置**。  
  
7.  在**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 SAP 系统。  
  
8.  单击 **“确定”**。  
  
## <a name="enter-client-credentials-at-run-time"></a>在运行时输入客户端凭据  
 对于运行时中，你可以指定客户端凭据中的 WCF 自定义或 WCF SAP 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
### <a name="enter-credentials-for-the-wcf-custom-port"></a>输入 WCF 自定义端口的凭据  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
3.  在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
4.  为发送端口，在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，执行下列操作之一：  
  
    -   选择**不使用单一登录**选项，并指定用户名和密码以连接到 SAP 系统。  
  
    -   选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。  
  
5.  接收端口，在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，执行下列操作之一：  
  
    -   选择**用户帐户**选项，并指定用户名和密码以连接到 SAP 系统。  
  
    -   选择**Get 凭据 affiliate 应用程序**选项，然后指定关联应用程序。  
  
6.  单击 **“确定”**。  
  
### <a name="enter-credentials-for-the-wcf-sap-port"></a>输入 WCF SAP 端口的凭据  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  添加到 WCF SAP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。  
  
3.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
4.  在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加的 WCF SAP 适配器，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
5.  如果您创建发送端口，则在传输属性对话框中，单击**凭据**选项卡，执行下列操作之一：  
  
    1.  选择**不使用单一登录**选项，并指定用户名和密码以连接到 SAP 系统。  
  
    2.  选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。  
  
6.  如果您创建接收端口，则在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，执行下列操作之一：  
  
    1.  选择**用户帐户**选项，并指定用户名和密码以连接到 SAP 系统。  
  
    2.  选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。  
  
7.  单击 **“确定”**。  
  
> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]此外支持企业单一登录 (SSO) 系统。 SSO 是仅适用于 BizTalk 方案中，在其中[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]是感知的 SSO 关联应用程序。 有关与 BizTalk Server 安全性的详细信息，请参阅[安全性与 SAP 适配器和 BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。
  
## <a name="see-also"></a>另请参阅  
[若要创建的 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)