---
title: 配置 Oracle E-business Suite 连接 URI |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2bb02b4-4ad6-4b07-b48a-8f9a47967ffc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cf8f0e81c7330b469070efb7457f22d1fed790d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22219237"
---
# <a name="configure-the-connection-uri-for-oracle-e-business-suite"></a>配置 Oracle E-business Suite 连接 URI
连接 URI 是包含参数才能连接到 Oracle E-business Suite 的连接字符串。 在使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须指定要连接到 Oracle E-business Suite 生成的元数据的 URI。 配置业务流程使用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你必须指定要连接到 Oracle E-business Suite 执行操作的 URI。  
  
## <a name="specifying-the-connection-uri-from-visual-studio"></a>指定连接 URI 从 Visual Studio  
 从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你必须指定连接 URI 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
#### <a name="to-specify-the-connection-uri-using-consume-adapter-service-add-in"></a>若要指定连接 URI 使用适配器服务外接程序中使用  
  
1.  右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  
  
3.  若要启动**使用适配器服务**对话框中，单击**添加**。  
  
4.  在**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleEBSBinding**，然后单击**配置**.  
  
5.  在**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**列表中，选择**用户名**和指定的用户名和密码以连接到 Oracle E-business Suite。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
    |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
    |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
    |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
6.  单击**URI 属性**选项卡，然后指定不同的参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[配置 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)。  
  
7.  单击**绑定属性**选项卡，然后指定的绑定值中，如果有的话，生成架构之前所需的。 有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
8.  单击 **“确定”**。  
  
#### <a name="to-specify-the-connection-uri-using-add-adapter-metadata-wizard"></a>若要指定连接 URI 使用添加适配器元数据向导  
  
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
  
7.  在**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**列表中，选择**用户名**和指定的用户名和密码以连接到 Oracle E-business Suite。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
    |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
    |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
    |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
8.  单击**URI 属性**选项卡，然后指定不同的参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[配置 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)。  
  
9. 单击**绑定属性**选项卡，然后指定的绑定值中，如果有的话，生成架构之前所需的。 有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
    > [!NOTE]
    >  如果你选择的现有 WCF OracleEBS 发送端口，你需要指定的绑定属性。 绑定属性是从发送端口配置中选取。 但是，你可以选择指定所需在设计时，如果任何绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定中发送端口配置的绑定属性的值将适用。  
  
10. 单击 **“确定”**。  
  
## <a name="specifying-the-connection-uri-from-the-biztalk-server-administration-console"></a>指定连接 URI 从 BizTalk Server 管理控制台  
 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你必须指定连接 URI 作为 WCF 自定义或 WCF OracleEBS 端口配置的一部分。  
  
#### <a name="to-specify-the-connection-uri-for-the-wcf-custom-port"></a>若要指定的 WCF 自定义端口的连接 URI  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
3.  在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
4.  在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。  
  
5.  在**地址 (URI)** 文本框中，指定连接 URI 以连接到 Oracle E-business Suite。 有关连接 URI 的详细信息为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[配置 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)。  
  
6.  在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**oracleEBSBinding**。  
  
7.  如果您创建发送端口，则在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，然后执行下列操作之一：  
  
    -   选择**不使用单一登录**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
        |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
        |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
        |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
    -   选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。  
  
8.  如果您创建接收端口，则在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，然后执行下列操作之一：  
  
    -   选择**用户帐户**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
        |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
        |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
        |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
    -   选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。  
  
9. 单击 **“确定”**。  
  
#### <a name="to-specify-the-connection-uri-for-the-wcf-oracleebs-port"></a>若要指定 WCF OracleEBS 端口的连接 URI  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  添加到 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)。  
  
3.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
4.  在端口属性对话框中，从**类型**下拉列表中，选择 WCF OracleEBS 适配器更早版本，添加，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
5.  在传输属性对话框中，单击**常规**选项卡。  
  
6.  单击**配置**按钮，然后提供的连接参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[配置 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)。  
  
7.  在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。  
  
    > [!NOTE]
    >  绑定属性显示的配置发送端口或接收端口。 例如，与通知相关的绑定属性不可用时配置发送端口，因为通知是入站的操作，需要接收端口配置。  
  
8.  如果您创建发送端口，则在传输属性对话框中，单击**凭据**选项卡，然后执行下列操作之一：  
  
    -   选择**不使用单一登录**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
        |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
        |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
        |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
    -   选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。  
  
9. 如果您创建接收端口，则在传输属性对话框中，单击**其他**选项卡，然后执行下列操作之一：  
  
    -   选择**用户帐户**选项，并指定的用户名和密码以连接到 Oracle E-business Suite。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**使用 Oracle 数据库凭据进行连接**|指定**ClientCredentialType**属性绑定到**数据库**并指定数据库的凭据**用户名**和**密码**文本框。|  
        |**若要使用 Oracle E-business Suite 凭据进行连接**|指定**ClientCredentialType**属性绑定到**EBusiness**并指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 在这种情况下，还必须指定用于 Oracle 数据库凭据**OracleUserName**和**OraclePassword**绑定属性。|  
        |**如果 ClientCredentialType 设置为"数据库"使用 Windows 身份验证进行连接**|指定的"/"为**用户名**文本框和离开**密码**文本框保留为空白。|  
        |**如果 ClientCredentialType 设置为"EBusiness"使用 Windows 身份验证进行连接**|指定用于 Oracle E-business Suite 凭据**用户名**和**密码**文本框。 你还必须指定"/"为**OracleUserName**绑定属性和离开**OraclePassword**绑定属性保留为空。|  
  
    -   选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。  
  
10. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)   
 [将连接到 Oracle E-business Suite 使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)