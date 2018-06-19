---
title: 为 Oracle E-business Suite 配置登录凭据 |Microsoft 文档
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
ms.openlocfilehash: acbfc92f962982292b8db73ff225dbe6699a16f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22219069"
---
# <a name="configure-the-sign-in-credentials-for-the-oracle-e-business-suite"></a>为 Oracle E-business Suite 配置登录凭据
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]需要适配器客户端提供客户端凭据。 适配器使用这些凭据进行身份验证与 Oracle E-business Suite 用户并建立连接。  
  
 适配器客户端可以提供在使用时的客户端凭据同时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]以及何时使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 使用时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，需要使用凭据才能生成元数据。 使用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，所需的凭据在 Oracle E-business Suite 上执行操作。  
  
> [!IMPORTANT]
>  你可以为 Oracle E-business Suite 或基础的 Oracle 数据库中指定的凭据。 若要连接并生成元数据可以指定任何凭据。 但是，在执行一个操作以调用 Oracle E-business Suite 项目时，你必须指定 Oracle E-business Suite 凭据，因为需要它们来设置要调用的 Oracle E-business Suite 应用程序的应用程序上下文。 有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
 本部分提供有关指定在客户端凭据的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="specifying-credentials-from-visual-studio"></a>指定从 Visual Studio 的凭据  
 从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
#### <a name="to-specify-credentials-using-consume-adapter-service-add-in"></a>若要指定使用适配器服务外接程序中使用的凭据  
  
1.  右键单击你的 BizTalk 项目，然后选择**添加生成的项**。  
  
2.  在**添加生成的项**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  
  
3.  若要启动**使用适配器服务**对话框中，单击**添加**。  
  
4.  在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleEBSBinding**，然后单击**配置**.  
  
5.  在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**列表中，选择**用户名**和指定的用户名和密码以连接到 Oracle E-business Suite。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
    |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
    |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
    |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
6.  单击 **“确定”**。  
  
#### <a name="to-specify-credentials-using-add-adapter-metadata-wizard"></a>若要使用添加适配器元数据向导指定凭据  
  
1.  右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**添加适配器**。|  
    |**模板**|单击**添加适配器元数据**。|  
  
3.  单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  
  
4.  在[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择**WCF OracleEBS**。 选择在其安装 BizTalk Server 的计算机和 BizTalk 数据库的名称。  
  
    > [!IMPORTANT]
    >  如果你已有在 BizTalk 中配置 WCF OracleEBS 端口，请从端口列表中选择端口。  
  
5.  单击 **“下一步”**。  
  
6.  在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleEBSBinding**，然后单击**配置**.  
  
7.  在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**列表中，选择**用户名**和指定的用户名和密码以连接到 Oracle E-business Suite。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
    |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
    |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
    |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
8.  单击 **“确定”**。  
  
## <a name="specifying-credentials-from-the-biztalk-server-administration-console"></a>指定从 BizTalk Server 管理控制台的凭据  
 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你必须作为 WCF 自定义或 WCF OracleEBS 端口配置的一部分指定的凭据。  
  
#### <a name="to-specify-credentials-for-the-wcf-custom-port"></a>若要指定凭据，以便 WCF 自定义端口  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
3.  在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
4.  在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**oracleEBSBinding**。  
  
5.  如果您创建发送端口，则在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，然后执行下列操作之一：  
  
    -   选择**不使用单一登录**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
        |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
        |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
        |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
    -   选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。  
  
6.  如果您创建接收端口，则在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，然后执行下列操作之一：  
  
    -   选择**用户帐户**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
        |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
        |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
        |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
    -   选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。  
  
7.  单击 **“确定”**。  
  
#### <a name="to-specify-credentials-for-the-wcf-oracleebs-port"></a>若要指定凭据，以便 WCF OracleEBS 端口  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  添加到 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)。  
  
3.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
4.  在端口属性对话框中，从**类型**下拉列表中，选择**WCF OracleEBS**，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
5.  在端口属性对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**oracleEBSBinding**。  
  
6.  如果您创建发送端口，则在传输属性对话框中，单击**凭据**选项卡，然后执行下列操作之一：  
  
    -   选择**不使用单一登录**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
        |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
        |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
        |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
    -   选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。  
  
7.  如果您创建接收端口，则在传输属性对话框中，单击**其他**选项卡，然后执行下列操作之一：  
  
    -   选择**用户帐户**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
        |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
        |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
        |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
    -   选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。  
  
8.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)   
 [将连接到 Oracle E-business Suite 使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)