---
title: 用于 Oracle E-business Suite 中配置单一登录凭据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 743ced51-706b-4788-b5a8-e0ed8ffb3b48
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08081cc1e59181f3cd6aad0dfa532b060287d2ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978942"
---
# <a name="configure-the-sign-in-credentials-for-the-oracle-e-business-suite"></a>用于 Oracle E-business Suite 中配置单一登录凭据
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求适配器客户端提供客户端凭据。 若要使用 Oracle E-business Suite 用户进行身份验证和建立连接，适配器将使用这些凭据。  

 适配器客户端可以提供的客户端凭据同时使用时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]以及何时使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 当使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，生成元数据所需的凭据。 当使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，则要求使用凭据来执行对 Oracle E-business Suite 的操作。  

> [!IMPORTANT]
>  用于 Oracle E-business Suite 或基础的 Oracle 数据库，可以指定的凭据。 若要连接，并生成元数据可以指定任何凭据。 但是，时正在执行的操作来调用 Oracle E-business Suite 项目，您必须指定 Oracle E-business Suite 凭据，因为它们需要设置你想要调用的 Oracle E-business Suite 应用程序的应用程序上下文。 有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

 本部分提供有关指定在客户端凭据的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

## <a name="specifying-credentials-from-visual-studio"></a>指定从 Visual Studio 的凭据  
 从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

#### <a name="to-specify-credentials-using-consume-adapter-service-add-in"></a>若要指定使用适配器服务外接程序使用的凭据  

1.  右键单击 BizTalk 项目中，然后依次**添加生成的项**。  

2.  在中**添加生成的项**对话框框中，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  

3.  若要启动**使用适配器服务**对话框中，单击**添加**。  

4.  在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleEBSBinding**，然后单击**配置**.  

5.  在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**列表中，选择**用户名**和指定的用户名和密码以连接到 Oracle E-business Suite。  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**若要使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
    |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**并**OraclePassword**绑定属性。|  
    |**如果将 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"对于**用户名**文本框中，保留**密码**文本框保留为空。|  
    |**如果将 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**并**密码**文本框。 您还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  

6.  单击“确定” 。  

#### <a name="to-specify-credentials-using-add-adapter-metadata-wizard"></a>若要指定凭据使用添加适配器元数据向导  

1. 右键单击您的 BizTalk 项目，指向**外**，然后单击**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |           执行的操作            |
   |----------------|---------------------------------|
   | **类别** |     单击**将适配器添加**。      |
   | **模板**  | 单击**添加适配器元数据**。 |


3. 单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  

4. 在中[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择**Wcf-oracleebs**。 选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。  

   > [!IMPORTANT]
   >  如果已配置 BizTalk 中的 WCF OracleEBS 端口，请从端口列表中选择的端口。  

5. 单击“下一步” 。  

6. 在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleEBSBinding**，然后单击**配置**.  

7. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**列表中，选择**用户名**和指定的用户名和密码以连接到 Oracle E-business Suite。  


   |                                         使用此选项                                          |                                                                                                                                               执行的操作                                                                                                                                                |
   |-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                     **若要使用 Oracle 数据库凭据进行连接**                      |                                                                          指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。                                                                          |
   |                 **若要使用 Oracle E-business Suite 凭据进行连接**                  | 指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**并**OraclePassword**绑定属性。 |
   | **如果将 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**  |                                                                                                         指定的"/"对于**用户名**文本框中，保留**密码**文本框保留为空。                                                                                                         |
   | **如果将 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接** |                                       指定用于 Oracle E-business Suite 凭据**用户名**并**密码**文本框。 您还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。                                       |


8. 单击“确定” 。  

## <a name="specifying-credentials-from-the-biztalk-server-administration-console"></a>指定 BizTalk Server 管理控制台中的凭据  
 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您必须指定凭据的 WCF 自定义或 WCF OracleEBS 端口配置的一部分。  

#### <a name="to-specify-credentials-for-the-wcf-custom-port"></a>若要指定凭据的 WCF 自定义端口  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

4. 在中**Wcf-custom 传输属性**对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**oracleEBSBinding**。  

5. 如果要创建的发送端口，请在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡，然后执行下列操作之一：  

   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Oracle E-business Suite。  

       |使用此选项|执行的操作|  
       |--------------|----------------|  
       |**若要使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
       |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**并**OraclePassword**绑定属性。|  
       |**如果将 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"对于**用户名**文本框中，保留**密码**文本框保留为空。|  
       |**如果将 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**并**密码**文本框。 您还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  

   -   选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。  

6. 如果要创建接收端口，请在**Wcf-custom 传输属性**对话框中，单击**其他**选项卡，然后执行下列操作之一：  

   -   选择**用户帐户**选项，然后指定用户名和密码以连接到 Oracle E-business Suite。  

       |使用此选项|执行的操作|  
       |--------------|----------------|  
       |**若要使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
       |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**并**OraclePassword**绑定属性。|  
       |**如果将 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"对于**用户名**文本框中，保留**密码**文本框保留为空。|  
       |**如果将 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**并**密码**文本框。 您还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  

   -   选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。  

7. 单击“确定” 。  

#### <a name="to-specify-credentials-for-the-wcf-oracleebs-port"></a>若要指定凭据的 WCF OracleEBS 端口  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 添加 WCF OracleEBS 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)。  

3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

4. 在端口属性对话框中，从**类型**下拉列表中，选择**Wcf-oracleebs**，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

5. 在端口属性对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**oracleEBSBinding**。  

6. 如果要创建的发送端口，在传输属性对话框中，单击**凭据**选项卡，然后执行下列操作之一：  

   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Oracle E-business Suite。  

       |使用此选项|执行的操作|  
       |--------------|----------------|  
       |**若要使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
       |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**并**OraclePassword**绑定属性。|  
       |**如果将 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"对于**用户名**文本框中，保留**密码**文本框保留为空。|  
       |**如果将 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**并**密码**文本框。 您还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  

   -   选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。  

7. 如果要创建接收端口，在传输属性对话框中，单击**其他**选项卡，然后执行下列操作之一：  

   -   选择**用户帐户**选项，然后指定用户名和密码以连接到 Oracle E-business Suite。  

       |使用此选项|执行的操作|  
       |--------------|----------------|  
       |**若要使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
       |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**并**OraclePassword**绑定属性。|  
       |**如果将 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"对于**用户名**文本框中，保留**密码**文本框保留为空。|  
       |**如果将 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**并**密码**文本框。 您还必须指定"/"作为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  

   -   选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。  

8. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [若要创建 Oracle E-business Suite 的应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)   
 [将连接到 Oracle E-business Suite 使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)