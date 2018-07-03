---
title: 配置 Oracle 数据库适配器的连接 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, specifying at design time
- connection URI, specifying at run time
ms.assetid: 9f302b67-0bcc-44d1-9517-10d402873540
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 849adf16faa96726fb3d182930be8f4965eb180d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007201"
---
# <a name="configure-the-connection-uri-for-the-oracle-database-adapter"></a>配置 Oracle 数据库适配器的连接 URI
一个连接 URI 是一个包含参数才能连接到 Oracle 数据库的连接字符串。 使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须指定要连接到 Oracle 数据库生成元数据的 URI。 在配置业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您必须指定要连接到 Oracle 数据库来执行操作的 URI。  

## <a name="specifying-the-connection-uri-from-visual-studio"></a>指定连接 URI 从 Visual Studio  
 必须从 Visual Studio 中，指定使用的凭据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  

#### <a name="to-specify-the-connection-uri-using-consume-adapter-service-add-in"></a>若要指定使用适配器服务外接程序使用的连接 URI  

1. 右键单击 BizTalk 项目中，然后依次**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |             执行的操作             |
   |----------------|------------------------------------|
   | **类别** | 单击**使用适配器服务**。 |
   | **模板**  | 单击**使用适配器服务**。 |


3. 若要启动**使用适配器服务**对话框中，单击**添加**。  

4. 在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleDBBinding**，然后单击**配置**。  

5. 在中**配置适配器**对话框中，单击**安全**选项卡并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Oracle 数据库：  

   -   若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。  

   -   若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。  

6. 单击**URI 属性**选项卡，并指定不同的参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  

7. 单击**绑定属性**选项卡，并指定的绑定值，如果有，生成架构之前所需的。 有关绑定属性的详细信息，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。  

8. 单击“确定” 。  

#### <a name="to-specify-the-connection-uri-using-add-adapter-metadata-wizard"></a>若要指定连接 URI，使用添加适配器元数据向导  

1. 右键单击您的 BizTalk 项目，指向**外**，然后单击**添加生成的项**。  

2. 在中**添加生成的项**对话框框中，执行以下操作：  


   |    使用此选项    |           执行的操作            |
   |----------------|---------------------------------|
   | **类别** |     单击**将适配器添加**。      |
   | **模板**  | 单击**添加适配器元数据**。 |


3. 单击 **“添加”**。 此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。  

4. 在中[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择**Wcf-oracledb**。 选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。  

   > [!IMPORTANT]
   >  如果已在 BizTalk 中配置的 Wcf-oracledb 端口，选择从端口**端口**列表。  

5. 单击“下一步” 。  

6. 在中**使用适配器服务**对话框中，从**选择的绑定**列表中，选择**oracleDBBinding**，然后单击**配置**.  

7. 在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**列表中，选择**用户名**和指定的用户名和密码以连接到 Oracle 数据库：  

   -   若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。  

   -   若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。  

8. 单击**URI 属性**选项卡，并指定不同的参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  

9. 单击**绑定属性**选项卡，并指定的绑定值，如果有，生成架构之前所需的。 有关绑定属性的详细信息，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。  

10. 单击“确定” 。  

## <a name="specifying-the-connection-uri-from-the-biztalk-server-administration-console"></a>指定连接 URI 从 BizTalk Server 管理控制台  
 从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您必须指定凭据的 WCF 自定义或 Wcf-oracledb 端口配置的一部分。  

#### <a name="to-specify-the-connection-uri-for-the-wcf-custom-port"></a>若要指定 WCF 自定义端口的连接 URI  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

3. 在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  

4. 为发送端口，在**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，执行下列操作之一：  

   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Oracle 数据库。  

       -   若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。  

       -   若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。  

   -   选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。  

5. 为接收端口，在**Wcf-custom 传输属性**对话框中，单击**其他**选项卡上，执行下列操作之一：  

   -   选择**用户帐户**选项，然后指定用户名和密码以连接到 Oracle 数据库。  

       -   若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。  

       -   若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。  

   -   选择**从获取凭据的关联应用程序**选项，并指定关联应用程序。  

6. 单击“确定” 。  

#### <a name="to-specify-the-connection-uri-for-the-wcf-oracledb-port"></a>若要指定 Wcf-oracledb 端口的连接 URI  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 添加 Wcf-oracledb 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。  

3. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，并单击应用程序**发送端口**或**接收端口**。 在右窗格中，您可以选择创建一个端口或选择现有端口。  

4. 在端口属性对话框中，从**类型**下拉列表中，选择**Wcf-oracledb**，然后单击**配置**。  

   > [!NOTE]
   >  若要查看接收端口的位置属性对话框，请单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  

5. 在端口属性对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**oracleDBBinding**。  

6. 如果要创建的发送端口，在传输属性对话框中，单击**凭据**选项卡，然后执行下列操作之一：  

   -   选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Oracle 数据库。  

       -   若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。  

       -   若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。  

   -   选择**使用单一登录**选项，并指定附属机构企业单一登录 (SSO) 应用程序。  

7. 如果要创建接收端口，在传输属性对话框中，单击**其他**选项卡，然后执行下列操作之一：  

   -   选择**用户帐户**选项，然后指定用户名和密码以连接到 Oracle 数据库。  

       -   若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。  

       -   若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。  

   -   选择**从获取凭据的关联应用程序**选项，并指定关联 SSO 应用程序。  

8. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
[若要开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)   
 [连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)