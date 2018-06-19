---
title: 步骤 1： 将 SAP 项目作为 WCF 服务发布 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service, generating a
- WCF Adapter Service Development Wizard , using the
- WCF Adapter Service Development Wizard
- SAP artifacts, publishing as a WCF service
ms.assetid: bd3087b0-e20f-4b75-beef-a913336d767b
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a83dd69e7c66c8ce8ff1af78662392dd0aa66ff2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967083"
---
# <a name="step-1-publish-the-sap-artifacts-as-a-wcf-service"></a>步骤 1： 发布的 SAP 项目作为一个 WCF 服务
![步骤 1 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 可以使用 WCF 适配器服务开发向导在如 Internet 信息服务 (IIS) 或 Windows 进程激活服务 (WAS) 宿主环境中生成可承载的 WCF 服务。 本主题演示如何使用向导来生成 WCF 服务文件。  
  
## <a name="prerequisites"></a>先决条件  
 运行向导之前，安装以下项：  
  
-   [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]使用**完成**选项或**自定义**选项 (选择**工具**中此选项)。 这将安装[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]WCF 适配器服务开发向导的模板。  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]从[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。  
  
-   所需的 SAP 客户端库。  
  
 有关这些先决条件的详细信息，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南。 安装指南通常安装在\<安装驱动器\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。  
  
### <a name="to-publish-the-sap-artifacts-as-a-wcf-service"></a>若要将 SAP 项目作为 WCF 服务发布  
  
1.  启动[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后创建一个项目。  
  
2.  在**新项目**对话框中，从**项目类型**窗格中，选择**Visual C#**。 从**模板**窗格中，选择**WCF 适配器服务**。  
  
     或者，从**项目类型**窗格中，展开**Visual C#**，然后选择**Web**。 从**模板**窗格中，选择**WCF 适配器服务**。  
  
    > [!NOTE]
    >  如果你安装[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]Web 开发组件后， **WCF 适配器服务**模板也会提供**新的网站**选项。  
  
3.  指定的名称和位置的解决方案，然后单击**确定**。 WCF 适配器服务开发向导将启动。  
  
4.  在欢迎页上，单击**下一步**。  
  
5.  在选择操作页上，指定要连接到 SAP 系统的连接字符串。 为此：  
  
    1.  在**选择的绑定**列表中，单击**sapBinding**，然后单击**配置**。  
  
    2.  在**配置适配器**对话框中，单击**安全**选项卡。  
  
    3.  在**客户端凭据类型**列表中，选择**用户名**，然后指定有效的 SAP 用户名和密码以连接到 SAP 系统。  
  
    4.  单击**URI 属性**选项卡上，然后指定连接参数的值。 有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
        > [!NOTE]
        >  如果连接参数包含任何保留的字符 （如 XML 特殊字符），则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。 但是，如果你指定直接在 URI**配置 URI**框和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。  
  
    5.  单击**绑定属性**选项卡上，如果你想要针对的操作所需任何操作，然后指定绑定属性的值。 在本教程中，调用 BAPI_SALESORDER_GETLIST RFC 若要获取特定客户的销售订单的列表。 销售订单信息可能还包含日期列。 当检索日期列的值，我们建议你设置**EnableSafeTyping**属性绑定到**True**在生成元数据。 如果设置此属性，以字符串的形式显示 SAP DAT 数据类型。  
  
         有关如何将 SAP 数据类型映射到等效的.NET 类型的详细信息，请参阅[基本 SAP 数据类型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)。  
  
         有关绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
    6.  单击**确定**，然后单击**连接**。 建立连接后，连接状态将显示为**已连接**。  
  
6.  在选择操作页面中**选择协定类型**列表中，单击**客户端 （出站操作）**。  
  
7.  在**选择类别**框中，展开一个 SAP 项目类型。 例如，展开**RFC**节点可查看包含你想要生成的 WCF 服务的 RFC 功能组。  
  
8.  在**可用类别和操作**框中，选择要为其生成 WCF 服务，然后单击的操作**添加**。 中列出了所选的操作**添加类别和操作**框。  
  
    > [!NOTE]
    >  你可以添加每个项目的多个操作。 你还可以添加不同的 SAP 项目的操作。 例如，你可以添加一个操作，RFC 和另一个用于 IDOC。 此外，你也可以通过在搜索表达式中指定通配符搜索特定操作。 有关受支持的特殊字符和从该处中，你可以搜索操作的节点级别的详细信息，请参阅[连接到 Visual Studio 使用添加适配器元数据在向导中的 SAP](../../adapters-and-accelerators/adapter-sap/connecting-to-sap-in-visual-studio-using-add-adapter-metadata-wizard.md)  
  
     对于本例，请添加了 SD_RFC_CUSTOMER_GET 和 BAPI_SALESORDER_GETLIST Rfc。  
  
    > [!NOTE]
    >  某些版本的 SAP 系统公开而不是 SD_RFC_CUSTOMER_GET RFC_CUSTOMER_GET RFC。  
  
     ![选择 SAP 项目](../../adapters-and-accelerators/adapter-sap/media/f944f9a0-7387-46cb-8eb6-337344d01d29.gif "f944f9a0-7387-46cb-8eb6-337344d01d29")  
  
9. 在选择操作页面上单击**下一步**。  
  
10. 在配置服务和终结点行为页上，指定值以配置的服务和终结点行为。  
  
    1.  在**服务行为配置**框中，指定以下设置的值：  
  
        |属性|指定的值|  
        |----------------------|-----------------------|  
        |EnableMetadataExchange|将其设置为**True**创建元数据交换终结点。 通过此选项设置为**True**，使服务元数据可使用标准的协议，如 WS 元数据交换 (MEX) 和 HTTP/GET 请求。<br /><br /> 默认值是**False**。|  
        |IncludeExceptionDetailsinFault|将其设置为**True**返回到客户端以便进行调试的 SOAP 错误的详细信息中包含托管的异常信息。 默认值是**False**。|  
        |Name|服务行为配置名称。|  
        |UseServiceCertificate|指定是否想要使用的 WCF 消息级别安全模式。 默认值是**True**。<br /><br /> 对于本教程，你必须将其设置**False**。|  
        |FindValue|一个字符串，指定要在 X.509 证书存储区中搜索的值。<br /><br /> **注意：** 为此属性仅当指定值**UseServiceCertificate**设置为**True**。|  
        |StoreLocation|一个值，指定服务可用于验证客户端的证书的证书存储区的位置。<br /><br /> **注意：** 为此属性仅当指定值**UseServiceCertificate**设置为**True**。|  
        |StoreName|若要打开的 X.509 证书存储区的名称。<br /><br /> **注意：** 为此属性仅当指定值**UseServiceCertificate**设置为**True**。|  
        |X509FindType|要执行的 X.509 搜索的类型。<br /><br /> **注意：** 为此属性仅当指定值**UseServiceCertificate**设置为**True**。|  
  
        > [!NOTE]
        >  有关证书和关联的属性的详细信息，请参阅"X509ClientCertificateCredentialsElement 属性"在[http://go.microsoft.com/fwlink/?LinkId=103771](http://go.microsoft.com/fwlink/?LinkId=103771)。  
  
    2.  在**终结点行为配置**框中，指定以下设置的值：  
  
        |属性|指定的值|  
        |----------------------|-----------------------|  
        |身份验证类型|-将此设置为**ClientCredentialUserNamePassword**以允许客户端使用 WCF 服务时指定的用户名和密码。<br /><br /> -将此设置为**HTTPUserNamePassword**以使客户端的 HTTP 标头的一部分指定用户名和密码。<br /><br /> -将此设置为**自动**首先允许客户端指定凭据通过**ClientCredential**接口。 如果此操作失败，客户端可以将凭据传递的 HTTP 标头的一部分。<br /><br /> 默认值是**自动**。对于 Microsoft Office SharePoint Server，可以使用的 WCF 服务，你应将其设置为**HTTPUserNamePassword**。|  
        |Name|指定终结点行为配置的名称。|  
        |UsernameHeader|用户名称标头的名称。 对于此示例中，指定**MyUserHeader**。 有关 HTTP 标头的详细信息，请参阅"支持的自定义 HTTP 和 SOAP 标头"在[http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)。<br /><br /> **注意：** 如果满足以下条件，则必须指定此属性的值**身份验证类型**设置为**HTTPUserNamePassword**。 如果**身份验证类型**设置为**自动**，此属性是可选的。|  
        |PasswordHeader|密码标头的名称。 对于此示例中，指定**MyPassHeader**。 有关 HTTP 标头的详细信息，请参阅"支持的自定义 HTTP 和 SOAP 标头"在[http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)。<br /><br /> **注意：** 如果满足以下条件，则必须指定此属性的值**身份验证类型**设置为**HTTPUserNamePassword**。 如果**身份验证类型**设置为**自动**，此属性是可选的。|  
  
     下图显示使用指定的值的配置服务和终结点行为页。  
  
     ![配置服务和终结点行为页](../../adapters-and-accelerators/adapter-sap/media/0a286b0c-7f0d-46c5-9b56-29bef3a1deea.gif "0a286b0c-7f0d-46c5-9b56-29bef3a1deea")  
  
11. 在配置服务和终结点行为页上，单击**下一步**。  
  
12. 在配置服务终结点绑定和地址页上，**选择协定配置**框中列出的 SAP 项目为其选择选择操作页面上的操作。  
  
     例如，如果你选择下 RFC 和 IDOC，项目**选择协定配置**列出 RFC 和 IDOC。 如果你选择仅 RFC，框将仅列出 RFC。  
  
13. **下所选的协定的操作**框将显示为选择操作页面上的每个项目选择的操作。  
  
14. 在**配置的地址和协定绑定**框中，指定以下设置的值：  
  
    |属性|指定的值|  
    |----------------------|-----------------------|  
    |绑定配置|该向导仅支持基本 HTTP 绑定。 因此，此绑定配置字段进行自动填充到*System.ServiceModel.Configuration.BasicHttpBindingElement*。<br /><br /> 单击省略号按钮 **（...）** 来更改 HTTP 绑定的属性。 若要使用的安全通信通道，必须始终设置**模式**属性**传输**。 向导会将设置的默认值为**模式**属性作为**传输**。<br /><br /> 有关其他公开的绑定的详细信息，请参阅"BasicHttpBindingElement 成员"网址[http://go.microsoft.com/fwlink/?LinkId=103773](http://go.microsoft.com/fwlink/?LinkId=103773)。|  
    |端点名称|指定协定的终结点名称。|  
  
     根据你在前面的页面中指定的值自动填充此页上的其他字段。  
  
     单击 **“应用”**。 执行此步骤下显示的所有协定**选择协定配置**框。  
  
    > [!NOTE]
    >  如果此页上未指定任何值，所有协定接受默认值。  
  
     下图显示的配置服务终结点绑定和地址页，用指定的值。  
  
     ![配置服务终结点绑定和地址](../../adapters-and-accelerators/adapter-sap/media/356e297c-9893-494c-a834-9d0b8b42da2e.gif "356e297c-9893-494c-a834-9d0b8b42da2e")  
  
15. 在配置服务终结点绑定和地址页上，单击**下一步**。  摘要页列出树状结构的 SAP 项目，并下，选择每个项目的操作。  
  
16. 查看摘要，并依次**完成**。  
  
17. 向导将创建一个 WCF 服务，并添加到以下文件[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目：  
  
    1.  .svc 文件。 这是 WCF 服务文件。 向导将生成每个协定的一个文件。  
  
    2.  Web.config 文件。  
  
    3.  服务代码 （.cs 文件）  
  
18. WCF 服务发布。  
  
    1.  请确保 Internet 信息服务 (IIS) 启用 SSL。 有关如何为 IIS 启用 SSL 的说明，请参阅[http://go.microsoft.com/fwlink/?LinkId=197170](http://go.microsoft.com/fwlink/?LinkId=197170)。  
  
    2.  右键单击解决方案资源管理器中的项目，然后单击**发布**。  
  
    3.  在**发布 Web**对话框中，指定 WCF 服务的 URL。 例如：  
  
        ```  
        https://<computer_name>/Customer_Order/  
        ```  
  
    4.  从**复制**框中，单击**所有项目文件**。  
  
    5.  单击“发布” 。  
  
19. 验证的 WCF 服务已成功发布。  
  
    1.  启动 IIS Microsoft 管理控制台。 单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
    2.  导航到在其中发布服务的节点。 有关**Customer_Order**服务中，导航到**Internet Information Services** > **\<计算机名称\>**  > **网站** > **Default Web Site** > **Customer_Order**。  
  
    3.  在右窗格中，右键单击 Rfc.svc 文件，然后单击**浏览**。  
  
    4.  网页出现时带有检索 WSDL 的 URL。 你可能想要测试元数据检索使用**svcutil**命令。 例如，若要检索 Customer_Order 服务的元数据的命令是：  
  
        ```  
        svcutil.exe https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
  
        ```  
  
## <a name="next-step"></a>下一步  
 若要创建的 SAP 项目的应用程序定义文件，使用业务数据目录定义编辑器。 请参阅[步骤 2： 为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)有关的说明。 应用程序定义文件标识存储 LOB 数据和在其中存储的格式。  
  
## <a name="see-also"></a>另请参阅  
 [教程 1：在 SharePoint 上提供来自 SAP 系统的数据](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)