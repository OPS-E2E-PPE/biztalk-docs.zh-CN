---
title: 配置 SAP 适配器的连接 URI |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, specifying at run time
- connection URI, specifying at design time
ms.assetid: 8df8e4a7-13f7-48c0-8af2-451253ced7e7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b614f3a300dbda213cd45ba7eaf9215802bc48c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218533"
---
# <a name="configure-the-connection-uri-for-the-sap-adapter"></a>配置 SAP 适配器的连接 URI
连接 URI 是用于连接到 SAP 系统的连接字符串。 它包含与某个 SAP 系统建立连接所需的各种参数。 在设计时，必须指定要连接到 SAP 系统生成的元数据的 URI。 在运行时，必须指定要连接到 SAP 系统以执行操作的 URI。  
  
## <a name="enter-the-connection-uri-at-design-time"></a>输入在设计时连接 URI  
 对于设计时，你可以指定连接 URI 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。  
  
### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a>输入连接使用适配器服务外接程序中使用的 URI  
  
1.  右键单击你的 BizTalk 项目，指向**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击**使用适配器服务**。|  
    |**模板**|单击**使用适配器服务**。|  
  
3.  若要启动**使用适配器服务**对话框中，单击**添加**。  
  
4.  在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sapBinding**，然后单击**配置**.  
  
5.  在**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 SAP 系统。  
  
6.  单击**URI 属性**选项卡上，并指定了不同参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
7.  单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。 例如，你必须指定的值**GenerateFlatFileCompatibleIDoc**之前用于从 SAP 系统接收 IDOC 生成架构的属性。 有关绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
8.  单击 **“确定”**。  
  
### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a>输入连接 URI 使用添加适配器元数据向导  
  
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
  
6.  在**使用适配器服务**对话框中，从**选择的绑定**下拉列表中，选择**sapBinding**，然后单击**配置**.  
  
7.  在**配置适配器**对话框中，单击**安全**选项卡。从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 SAP 系统。  
  
8.  单击**URI 属性**选项卡上，并指定了不同参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
9. 单击**绑定属性**选项卡上，并指定绑定值，如果有，这需要在生成架构之前指定。 例如，你必须指定的值**GenerateFlatFileCompatibleIDoc**之前用于从 SAP 系统接收 IDOC 生成架构的属性。 有关绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
    > [!NOTE]
    >  如果你选择现有 WCF SAP 发送端口，你不需要指定的绑定属性。 绑定属性是从发送端口配置中选取。 但是，你可以选择指定所需在设计时，如果任何绑定属性。 在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。 但是，在运行时指定中发送端口配置的绑定属性的值将适用。  
  
10. 单击 **“确定”**。  
  
## <a name="enter-the-connection-uri-at-run-time"></a>输入连接 URI 在运行时  
 对于运行时中，你可以指定 URI 中的 WCF 自定义或 WCF SAP 端口配置的一部分[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a>输入 WCF 自定义端口的连接 URI  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
3.  在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
4.  在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。  
  
5.  在**地址 (URI)** 文本框中，指定连接 URI 以连接到 SAP 系统。 有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
6.  在**WCF 自定义传输属性**对话框中，单击**绑定**选项卡。从**绑定类型**下拉列表中，选择**sapBinding**。  
  
7.  如果您创建发送端口，则在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，执行下列操作之一：  
  
    1.  选择**不使用单一登录**选项，并指定用户名和密码以连接到 SAP 系统。  
  
    2.  选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。  
  
8.  如果您创建接收端口，则在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，执行下列操作之一：  
  
    1.  选择**用户帐户**选项，并指定用户名和密码以连接到 SAP 系统。  
  
    2.  选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。  
  
9. 单击 **“确定”**。  
  
### <a name="enter-the-connection-uri-for-the-wcf-sap-port"></a>输入 WCF SAP 端口的连接 URI  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  添加到 WCF SAP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。  
  
3.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用程序**发送端口**或**接收端口**。 在右窗格中，你可以选择创建一个端口或选择现有的端口。  
  
4.  在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加的 WCF SAP 适配器，然后单击**配置**。  
  
    > [!NOTE]
    >  若要查看接收端口的位置属性对话框中，单击**接收位置**选项卡上的端口属性对话框中，左窗格中，然后单击**新建**。  
  
5.  在传输属性对话框中，单击**常规**选项卡。  
  
6.  单击**配置**按钮，然后提供的连接参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
7.  在传输属性对话框中，单击**绑定**选项卡上，并指定绑定属性的值。  
  
    > [!NOTE]
    >  绑定属性显示的配置发送端口或接收端口。 例如，绑定属性相关的入站操作不可用时配置发送端口，因为入站的操作需要接收端口配置。  
  
8.  如果您创建发送端口，则在传输属性对话框中，单击**凭据**选项卡，执行下列操作之一：  
  
    1.  选择**不使用单一登录**选项，并指定用户名和密码以连接到 SAP 系统。  
  
    2.  选择**使用单一登录**选项，并指定分支机构的企业单一登录 (SSO) 应用程序。  
  
9. 如果您创建接收端口，则在**WCF 自定义传输属性**对话框中，单击**其他**选项卡，执行下列操作之一：  
  
    1.  选择**用户帐户**选项，并指定用户名和密码以连接到 SAP 系统。  
  
    2.  选择**Get 凭据 affiliate 应用程序**选项，然后指定关联 SSO 应用程序。  
  
10. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
[若要创建的 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)