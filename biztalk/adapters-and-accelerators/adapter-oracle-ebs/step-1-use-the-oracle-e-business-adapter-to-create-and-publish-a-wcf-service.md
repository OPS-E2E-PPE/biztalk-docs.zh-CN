---
title: 第 1 步：使用 Oracle E-business 适配器创建和发布 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cd76f6f-600f-4eb5-8eee-8f3604d0fef4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88b8ae60cd9b2daa15c9d33888eeaa6c6b703408
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374559"
---
# <a name="step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service"></a>第 1 步：使用 Oracle E-business 适配器创建和发布 WCF 服务
![步骤 1，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **若要完成的时间：** 15 分钟  
  
 **目标：** 可以使用[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]从可以如 Internet 信息服务 (IIS) 或 Windows 进程激活服务 (WAS) 宿主环境中托管的 Oracle E-business Suite 项目生成 WCF 服务。 本主题演示如何使用向导生成的 WCF 服务文件。  
  
## <a name="prerequisites"></a>先决条件  
 运行向导之前，安装以下组件：  
  
- [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] 使用**完成**选项或**自定义**选项 (，然后选择**工具**中此选项)。 这将安装[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]模板[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]。  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] 从[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。  
  
  有关这些先决条件的详细信息，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南。 安装指南通常安装在\<安装驱动器\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。  
  
> [!NOTE]
>  您还必须运行 Microsoft Office SharePoint Server 示例来创建与提供的 create_apps_artifacts.sql 脚本**MS_SAMPLE_EMPLOYEE**中的接口表**应用程序对象库**应用程序。 在本教程中使用此接口表。  
  

  
##  <a name="Create_Service"></a> 创建 Oracle 电子商务项目上的操作的 WCF 服务  
 本部分提供创建 MS_SAMPLE 员工接口表上的选择操作的 WCF 服务的步骤。  
  
#### <a name="to-create-a-wcf-service-for-the-select-operation-on-the-mssample-employee-interface-table"></a>若要创建 MS_SAMPLE 员工接口表上的选择操作的 WCF 服务  
  
1. 启动[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后创建一个项目。  
  
2. 在中**新的项目**对话框中，从**项目类型**窗格中，选择**Visual C#**。 从**模板**窗格中，选择**WCF 适配器服务**。  
  
    或者，从**项目类型**窗格中，展开**Visual C#**，然后选择**Web**。 从**模板**窗格中，选择**WCF 适配器服务**。  
  
    ![新建项目对话框](../../adapters-and-accelerators/adapter-oracle-ebs/media/01-new-project.gif "01_New_Project")  
  
   > [!NOTE]
   >  如果您安装了[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]与 Web 开发的组件**WCF 适配器服务**模板也会提供**新的 Web 站点**选项 (**文件** > **新** > **网站**)。  
   > 
   >  但是，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]仅支持在文件系统创建的网站。 因此，在创建网站时在新建网站对话框中，必须单击文件系统位置列表中。  
  
3. 指定的名称和位置的解决方案，然后单击**确定**。 WCF[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]启动。  
  
4. 在欢迎页上，单击**下一步**。  
  
5. 在选择操作页上指定要连接到 Oracle E-business Suite 的连接字符串。 为此，请执行以下操作：  
  
   1. 在中**选择绑定**列表中，单击**oracleEBSBinding**，然后单击**配置**。  
  
   2. 在中**配置适配器**对话框中，单击**绑定属性**选项卡。  
  
      1.  下**常规**类别中，对于**ClientCredentialType**绑定属性中，选择**EBusiness**。  
  
      2.  下**OracleEBS**类别中，指定相应的值**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。 在这种情况下，你需要提供数据库凭据**OracleUserName**并**OraclePassword**绑定属性。  
  
      3.  下**元数据**类别中，对于**EnableSafeTyping**绑定属性中，选择**True**。 如果要检索的日期列的值，我们建议您设置**EnableSafeTyping**属性绑定到**True**生成元数据时。  
  
   3. 单击**URI 属性**选项卡，然后指定连接参数的值。 有关详细信息的连接 URI 对于[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)。  
  
   4. 单击**安全**选项卡上，然后在**客户端凭据类型**列表中，选择**用户名**。 指定有效的 Oracle E-business Suite 的用户名和密码以连接到 Oracle E-business Suite。  
  
   5. 单击**确定**以关闭配置适配器对话框中，然后单击**Connect**。 Visual Studio 已成功建立与 Oracle E-business Suite 的连接后，连接状态显示为**已连接**。 此外可以查看显示在选择操作页面上的 Oracle E-business Suite 元数据。  
  
6. 在选择操作页中**选择协定类型**列表中，单击**客户端 （出站操作）**。  
  
7. 在中**选择一个类别**框中，浏览到应用程序对象库应用程序中的 MS_SAMPLE_EMPLOYEE 接口表。 浏览到该适配器中的项目有关的信息，请参阅[浏览、 搜索和检索用于 Oracle E-business 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
8. 在中**可用类别和操作**框中，选择**选择**操作，并单击**添加**。 选择操作添加到**添加的类别和操作**框。  
  
    ![添加选择操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/02-msb-gui.gif "02_MSB_GUI")  
  
   > [!NOTE]
   >  您可以添加多个操作的每个项目。 此外可以添加用于 Oracle E-business Suite 的不同项目的操作。 例如，可以添加一个操作，可接口表，另一个用于并发程序。 此外，您也可以通过搜索表达式中指定通配符搜索特定的操作。 有关受支持的特殊字符和的中，您可以搜索 operations 节点级别的详细信息，请参阅[用于 Oracle E-business Suite 操作的搜索](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md)。  
  
9. 在选择操作页上单击**下一步**。  
  
10. 在配置服务和终结点行为页上，指定值以配置的服务和终结点行为。  
  
    1. 在中**服务行为配置**框中，指定以下设置的值：  
  
       |属性|指定的值|  
       |----------------------|-----------------------|  
       |EnableMetadataExchange|将此设置为 **，则返回 True**创建元数据交换终结点。 通过此选项设置为 **，则返回 True**，使服务元数据可使用标准的协议，如 WS-元数据交换 (MEX) 和 HTTP/GET 请求。 默认值是**False**。|  
       |IncludeExceptionDetailsinFault|将此设置为 **，则返回 True**返回到客户端以便进行调试的 SOAP 错误的详细信息中包含托管的异常信息。 默认值是**False**。|  
       |“属性”|服务行为配置名称。 对于本教程中，键入**customServiceBehavior**。|  
       |UseServiceCertificate|指定是否想要使用的 WCF 消息级别安全模式。 默认值是 **，则返回 True**。 对于本教程，必须将其设置**False**。|  
  
       > [!NOTE]
       >  因为我们不在本教程使用服务证书，不需要提供相应的值**FindValue**， **StoreLocation**， **StoreName**，以及**X509FindType**属性。 有关证书和关联的属性的详细信息，请参阅"X509ClientCertificateCredentialsElement 属性"处[ http://go.microsoft.com/fwlink/?LinkId=103771 ](http://go.microsoft.com/fwlink/?LinkId=103771)。  
  
    2. 在中**终结点行为配置**框中，指定以下设置的值：  
  
       |属性|指定的值|  
       |----------------------|-----------------------|  
       |身份验证类型|对于 Microsoft Office SharePoint Server 使用 WCF 服务，应设置为**HTTPUserNamePassword**。 这允许客户端的 HTTP 标头的一部分指定用户名和密码。|  
       |“属性”|指定的终结点行为配置名称。 对于本教程中，键入**customEndpointBehavior**。|  
       |UsernameHeader|用户名称标头的名称。 对于此示例中，指定**MyUserHeader**。 有关 HTTP 标头的详细信息，请参阅"支持的自定义 HTTP 和 SOAP 标头"网址[ http://go.microsoft.com/fwlink/?LinkId=106692 ](http://go.microsoft.com/fwlink/?LinkId=106692)。 **注意：** 如果满足以下条件，则必须指定此属性的值**身份验证类型**设置为**HTTPUserNamePassword**。 如果**身份验证类型**设置为**自动**，此为可选属性。|  
       |PasswordHeader|密码标头的名称。 对于此示例中，指定**MyPassHeader**。 有关 HTTP 标头的详细信息，请参阅"支持的自定义 HTTP 和 SOAP 标头"网址[ http://go.microsoft.com/fwlink/?LinkId=106692 ](http://go.microsoft.com/fwlink/?LinkId=106692)。 **注意：** 如果满足以下条件，则必须指定此属性的值**身份验证类型**设置为**HTTPUserNamePassword**。 如果**身份验证类型**设置为**自动**，此为可选属性。|  
  
       下图显示了具有指定值的配置服务和终结点行为页。  
  
       ![配置服务和终结点行为页](../../adapters-and-accelerators/adapter-oracle-ebs/media/03-service-and-endpoint-behavior.gif "03_Service_and_EndPoint_Behavior")  
  
11. 在配置服务和终结点行为页上单击**下一步**。  
  
12. 在配置服务终结点绑定和地址页上**选择用于配置的协定**显示你配置的项目 (MS_SAMPLE_EMPLOYEE)。 **下的所选的协定的操作**框将显示**选择**用于在选择操作页面上的项目的所选的操作。  
  
13. 在中**配置的地址和协定绑定**框中，指定以下设置的值：  
  
    |属性|指定的值|  
    |----------------------|-----------------------|  
    |绑定配置|该向导仅支持基本 HTTP 绑定。 因此，绑定配置字段自动填充到*System.ServiceModel.Configuration.BasicHttpBindingElement*。<br /><br /> 单击省略号按钮 **（...）** 来更改 HTTP 绑定的属性。 若要使用的安全通信通道，必须始终设置**模式下**属性设置为**传输**。 该向导设置的默认值为**模式下**属性作为**传输**。<br /><br /> 有关公开其他绑定的详细信息，请参阅"BasicHttpBindingElement 成员"网址[ http://go.microsoft.com/fwlink/?LinkId=103773 ](http://go.microsoft.com/fwlink/?LinkId=103773)。|  
    |端点名称|指定协定的终结点名称。|  
  
     此页上的其他字段已根据前面的页面中指定的值自动填充。  
  
     单击 **“应用”**。  
  
    > [!NOTE]
    >  如果不指定任何值在此页上，为所有协定接受默认值。  
  
     下图显示了配置服务终结点绑定和地址页上，使用指定的值。  
  
     ![配置服务终结点绑定和地址](../../adapters-and-accelerators/adapter-oracle-ebs/media/04-service-endpoint-binding.gif "04_Service_Endpoint_Binding")  
  
14. 在配置服务终结点绑定和地址页上单击**下一步**。  摘要页列出了树结构的 Oracle E-business Suite 项目与所选的项目的操作。  
  
15. 查看摘要，然后依次**完成**。  
  
16. 该向导创建 WCF 服务并添加到以下文件[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目：  
  
    1.  .svc 文件。 这是 WCF 服务文件。 向导将生成每个协定的一个文件。  
  
    2.  Web.config 文件。  
  
    3.  服务代码 （.cs 文件）  
  
##  <a name="cs"></a> 修改的.cs 文件  
 当创建超出 Oracle E-business Suite 项目使用的服务[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]并且想要从业务数据列表 Web 部件在 Microsoft Office SharePoint Server 中，使用它，并且希望提供完整筛选子句开头的 WHERE 子句. 例如，如果你想要搜索的名称为"John"的员工，需要提供业务数据列表 Web 部件中的以下筛选器子句：  
  
```  
where NAME like ‘JOHN’  
```  
  
 但是，如果您希望用户仅提供的名称作为输入的筛选器子句，而实际上从未提及整个筛选器子句，您可以将代码添加在.cs 文件中修改来自业务数据列表 Web 部件在 Microsoft Office 中的筛选器子句 将 SharePoint 服务器中的 WHERE 子句格式将其传递到 Oracle E-business。  
  
 例如，对于本教程中，如果希望用户在 Microsoft Office SharePoint Server 中的业务数据列表 Web 部件中输入一个雇员的姓名和检索记录的该员工，您可以添加以下代码在.cs 文件中：  
  
```  
SelectResponse InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.Select(SelectRequest request)   
{  
     request.FILTER = "where NAME like '" + request.FILTER + "'"; // The code to avoid the users from specifying the WHERE clause in the filter from Business Data List Web Part.  
     return base.Channel.Select(request);  
}  
```  
  
##  <a name="Publish"></a> 发布 WCF 服务  
 请确保为 IIS 启用 SSL。 有关如何为 IIS 启用 SSL 的说明，请参阅[ http://go.microsoft.com/fwlink/?LinkId=197170 ](http://go.microsoft.com/fwlink/?LinkId=197170)。  
  
 若要发布的 WCF 服务：  
  
1.  右键单击解决方案资源管理器中的项目，然后单击**发布**。  
  
2.  在中**发布 Web**对话框框中，指定 WCF 服务的 URL。 例如：  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/  
    ```  
  
    > [!NOTE]
    >  必须将 WCF 服务发布到已启用 SSL 的位置。 换而言之中的值**目标位置**框必须以"https://"开头。 HTTP 标头中传递用户凭据，因为该向导将自动配置适配器的绑定行为，以作为安全模式，这意味着 SSL 加密中使用"传输"。 您当然可以返回，并编辑 web.config 文件以更改的值**\<安全模式\>** 参数，但使用 SSL 时，始终是更好的选择已准备好以明文形式传输的敏感信息HTTP 标头中的文本。  
  
3.  从**副本**框中，单击**所有项目文件**。  
  
4.  单击“发布” 。  
  
5.  验证已成功发布 WCF 服务。  
  
    1.  启动 IIS Microsoft 管理控制台。 单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
    2.  导航到发布服务的节点。 有关**MS_SAMPLE_EMPLOYEE**服务，请导航到**Internet Information Services** > **\<计算机名称\>**  > **网站** > **默认网站** > **MS_SAMPLE_EMPLOYEE**。  
  
    3.  在右窗格中，右键单击 InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc 文件，然后单击**浏览**。  
  
    4.  Web 页会显示用于检索 WSDL 的 url。 要测试元数据检索使用**svcutil**命令。 例如，若要检索 MS_SAMPLE_EMPLOYEE 服务的元数据的命令是：  
  
        ```  
        svcutil.exe https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc?wsdl  
  
        ```  
  
## <a name="next-step"></a>下一步  
 若要创建 Oracle E-business Suite 项目应用程序定义文件，请使用 Business Data Catalog Definition Editor。 有关说明，请参阅[步骤 2:为 Oracle E-business Suite 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)。 应用程序定义文件来确定存储 LOB 数据和在其中存储的格式。  
  
## <a name="see-also"></a>请参阅  
 [教程：从 SharePoint 站点上的 Oracle E-business Suite 中显示数据](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)