---
title: 配置用于 Siebel 的登录凭据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, specify credentials for the Siebel system at run time
- credentials, specifying
- how to, specify credentials for the Siebel system at design time
ms.assetid: a9fef2ba-c38e-44f7-84a3-b6a95d4dc210
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca773a4e7cd5c1d600f82b3af7b471929cff212
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971854"
---
# <a name="configure-the-sign-in-credentials-for-the-siebel"></a>配置用于 Siebel 的登录凭据
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]要求适配器客户端提供客户端凭据。 适配器使用这些凭据与 Siebel 系统用户进行身份验证并建立连接。  

 适配器客户端可以提供客户端凭据在设计时或运行时。 在设计时，需要凭据以生成元数据。 在运行时，需要凭据以执行 Siebel 系统的操作。 本部分提供有关在设计时和运行的时指定客户端凭据的信息。  

## <a name="enter-the-client-credentials-at-design-time"></a>在设计时输入的客户端凭据  
 对于设计时，你必须指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

#### <a name="enter-client-credentials-using-consume-adapter-service-add-in"></a>输入使用适配器服务外接程序使用的客户端凭据  

1.  右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。  

2.  在中**添加生成的项**对话框框中，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  

3.  若要启动**使用适配器服务**对话框中，单击**添加**。  

4.  在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**siebelBinding**，然后单击**配置**。  

5.  在中**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Siebel 系统。  

6.  单击“确定” 。  

#### <a name="enter-client-credentials-using-add-adapter-metadata-wizard"></a>输入客户端凭据使用添加适配器元数据向导  

1. 右键单击您的 BizTalk 项目，指向**外**，然后选择**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |           执行的操作            |
   |----------------|---------------------------------|
   | **类别** |     单击**将适配器添加**。      |
   | **模板**  | 单击**添加适配器元数据**。 |


3. 单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  

4. 在添加适配器向导中，选择**Wcf-siebel**。 选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。  

   > [!IMPORTANT]
   >  如果已配置 BizTalk 中的 WCF Siebel 端口，选择从端口**端口**列表。  

5. 单击“下一步” 。  

6. 在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**siebelBinding**，然后单击**配置**。  

7. 在中**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Siebel 系统。  

8. 单击“确定” 。  

## <a name="enter-client-credentials-at-run-time"></a>在运行时输入客户端凭据  
 对于运行时中，你必须指定客户端凭据中的 WCF 自定义或 Wcf-siebel 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

#### <a name="enter-credentials-for-the-wcf-custom-port"></a>WCF 自定义端口输入凭据  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用程序**发送端口**. 在右窗格中，您可以选择创建一个端口或选择现有端口。  

3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  

4. 为发送端口，在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，执行下列操作之一：  

   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Siebel 系统。  

   -   选择**使用单一登录**选项，并指定关联 ESSO 应用程序。  

5. 单击“确定” 。  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 此外支持企业单一登录 (ESSO) 系统。 ESSO 是仅适用于 BizTalk 方案中，WCF 适配器是在其中了解的 ESSO 关联应用程序。 有关与 BizTalk Server 相关的安全性的详细信息，请参阅[Siebel 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)。

#### <a name="enter-credentials-for-the-wcf-siebel-port"></a>为 WCF Siebel 端口输入凭据  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 添加到 WCF 的 Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。  

3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用程序**发送端口**. 在右窗格中，您可以选择创建一个端口或选择现有端口。  

4. 在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加的 Wcf-siebel 端口，然后单击**配置**。  

5. 对于发送端口，在传输属性对话框中，单击**凭据**选项卡上，执行下列操作之一：  

   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Siebel 系统。  

   -   选择**使用单一登录**选项，并指定关联 ESSO 应用程序。  

6. 单击“确定” 。  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 此外支持企业单一登录 (ESSO) 系统。 ESSO 是仅适用于 BizTalk 方案中，WCF 适配器是在其中了解的 ESSO 关联应用程序。 有关与 BizTalk Server 相关的安全性的详细信息，请参阅[Siebel 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)。

## <a name="see-also"></a>请参阅  
[若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)