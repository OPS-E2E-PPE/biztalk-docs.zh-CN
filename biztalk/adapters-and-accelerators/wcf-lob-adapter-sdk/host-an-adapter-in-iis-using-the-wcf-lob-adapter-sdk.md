---
title: 承载在 IIS 使用 WCF LOB 适配器 SDK 中的适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 90b6cd97-01b3-4c98-a190-c6e0ccf24d2b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 326dc5f3102354c8f2aa6fa785b145b72014f3d3
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="host-an-adapter-in-iis-using-the-wcf-lob-adapter-sdk"></a>承载在 IIS 使用 WCF LOB 适配器 SDK 中的适配器
本部分包含有关承载使用生成的适配器的信息[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]在 Internet 信息服务 (IIS)。 有关其他宿主选项的详细信息，请参阅[托管服务](https://msdn.microsoft.com/library/ms730158.aspx)。
  
## <a name="use-iis-and-aspnet"></a>使用 IIS 和 ASP.NET
 IIS 可以使用 ASP.NET 启用以发布使用 WCF LOB 适配器 SDK 创建的适配器。 若要承载创建的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，为发布 WCF 服务配置 Internet 信息服务 (IIS)。 接下来，请考虑如何使用你 WCF adapterwith ASP.NET。
 
 当承载在 IIS 中的 WCF 服务时，有两种可用的宿主模式：**并排显示**和 A**SP.NET 兼容性模式**。 宿主模式默认值为并排显示。 与其他 WCF 承载解决方案由并行模式行为保持一致。 因此，在 IIS 中承载的 WCF 服务的行为与一个承载于控制台应用程序相同。 但是，这可能不希望因为 web 开发人员可能希望行为类似于 ASP.NET。 例如，在并排显示模式下，WCF 不符合指定的任何基于 URL 的授权规则中`<system.web> <authorization>`web.config 的配置元素。  
  
 ASP.NET 兼容模式允许 WCF 服务以使用 ASP.NET 的所有功能和 ASPX 页面; 相同的行为但是，你必须创建您的 WCF 适配器以启用此功能时执行其他步骤。 有关详细信息，请参阅： 
 
 [WCF 服务和 ASP.NET](https://msdn.microsoft.com/library/aa702682.aspx)
 
[在 Internet 信息服务中承载](https://msdn.microsoft.com/library/ms734710.aspx)

[承载服务的 WCF](https://msdn.microsoft.com/library/ms730158.aspx)

## <a name="use-the-wcf-adapter-service-development-wizard"></a>使用 WCF 适配器服务开发向导

使用[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]来自动执行创建用于托管你的适配器在 Internet 信息服务 (IIS) Web 项目。 通过使用 Windows Communication Framework (WCF) 或 Web 服务客户端也可以使用托管的适配器。  
  
### <a name="publish-an-adapter-as-a-wcf-service-hosted-in-iis"></a>将一个适配器作为 IIS 中承载的 WCF 服务发布  
  
1.  打开 [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]。 上**文件**菜单上，选择**新建**，然后选择**网站**。  
  
2.  在**模板**，选择**Visual C#**，然后选择**WCF 适配器服务**。  
  
3.  输入要保存该解决方案，，然后选择的文件夹**确定**。 **WCF 适配器服务开发向导**启动。  
  
4.  上**简介**页上，单击**下一步**。  
  
5.  上**选择操作**页上，指定要用于此托管服务的绑定、 协定和操作。  
  
    1.  在**选择的绑定**列表中，选择适配器绑定以使用，然后单击**配置**。 此时将显示**配置适配器**对话框。 提供调用该适配器以及检索操作元数据时需要的值。  
  
    2.  上**安全**选项卡上，选择**客户端凭据类型**时将客户端凭据传递给适配器使用。  
  
        |凭据类型|Description|  
        |---------------------|-----------------|  
        |**InclusionThresholdSetting**|客户端不需要提供凭据。|  
        |**Windows**|客户端将使用 Windows 凭据。|  
        |**用户名**|客户端将提供的用户名和密码。|  
        |**证书**|客户端将使用 X.509 证书进行身份验证。 如果设置此值，请单击**浏览**中**客户端证书**区域中，，然后选择要使用的证书。|  
  
    3.  上**URI 属性**选项卡上，指定适配器所需的 URI 参数。 此选项卡中显示的项而异中公开的属性`ConnectionUri Properties`的适配器的类。  
  
    4.  上**绑定属性**选项卡上，指定所需的适配器的绑定属性的值。 **常规**部分包含常用的设置，如超时值。 其他属性列出上在公开的自定义属性基于您`AdapterBinding`类。  
  
6.  后指定配置值后，单击**连接**。  
  
    1.  从**选择协定类型**列表中，选择要使用的协定。 这将填充**选择类别**树控件的类别和通过此适配器执行的操作的列表。 如果适配器实现搜索功能通过`MetadataRetrievalClient`类，你可以输入中的搜索词**类别中的搜索**字段以返回仅类别和包含的搜索词的操作。  
  
        > [!NOTE]
        >  仅出站操作是可供选择。  
  
    2.  从**可用类别和操作**框中，选择要添加，，然后单击的项**添加**。 一旦你已添加所需的项目，单击**下一步**。  
  
7.  上**配置服务和终结点行为**页上，为此适配器设置所需的行为。  
  
    1.  **服务行为配置**部分包含控制服务行为的条目。 运行向导之后，可以通过编辑 web.config 文件中修改所选的服务行为。  
  
        |属性|Description|  
        |--------------|-----------------|  
        |**EnableMetadataExchange**|此值设置为**True**启用服务元数据发布到客户端请求。 此外可以通过修改设置这\< **serviceMetadata httpGetEnabled =""** \>在 web.config 中。默认值是**False**|  
        |**IncludeExceptionDetailsinFault**|此值设置为**True**导致托管的异常信息返回到 SOAP 错误中客户端。 此外可以通过修改设置这\< **serviceDebug usingincludeExceptionDetailInFaults =""** \>在 web.config 中。默认值是**False**。|  
        |**名称**|服务行为配置名称。|  
        |**UseServiceCertificate**|此值确定服务是否将使用 X.509 证书来向客户端进程验证自身。 默认值是**True**。|  
        |**FindValue**|此值用于搜索特定的 X.509 证书的证书存储中。 此外可以通过修改设置这\< **serviceCredentials findValue =""** \>在 web.config 中**注意：**为此属性仅当指定值**UseServiceCertificate**设置为**True**。|  
        |**storeLocation**|此值指定要搜索指定的证书的系统存储位置。 此外可以通过修改设置这\< **serviceCredentials storeLocation =""** \>在 web.config 中。**注意：**为此属性仅当指定值**UseServiceCertificate**设置为**True**。|  
        |**storeName**|此值指定要搜索指定的证书的特定系统存储区。 此外可以通过修改设置这\< **serviceCredentials storeName =""** \>在 web.config 中**注意：**为此属性仅当指定值**UseServiceCertificate**设置为**True**。|  
        |**X509FindType**|为了查找要使用的特定证书的搜索将用于 FindValue 的类型指定更早版本。 此外可以通过修改设置这\< **serviceCredentials x509FindType =""** \>在 web.config 中**注意：**为此属性仅当指定值**UseServiceCertificate**设置为**True**。|  
  
    2.  **终结点行为配置**部分控制终结点行为。  
  
        |属性|Description|  
        |--------------|-----------------|  
        |**名称**|终结点行为的名称|  
        |**AuthenticationType**|此值指示适配器获取客户端的传入文档的凭据的位置。 若要启用客户端指定客户端证书向服务进行身份验证，请将此设置为**ClientCredentialUsernamePassword**。 若要启用客户端的 HTTP 标头的一部分指定的用户名和密码，将其设置为**HTTPUsernamePassword**。 若要启用客户端指定凭据通过 ClientCredential 界面，将其设置为**自动**。如果此操作失败，客户端可以将凭据传递的 HTTP 标头的一部分。<br /><br /> 此外可以通过修改设置此值\< **endpointBehavior adapterSecurityBridgeType** \>在 web.config 中。默认值是**自动**。|  
        |**UsernameHeader**|这指定将用于向服务传递用户名标头的名称。 有关 HTTP 标头的详细信息，请参阅"支持的自定义 HTTP 和 SOAP 标头"在 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)<br /><br /> 此外可以通过修改设置此值\< **endpointBehavior usernameHttpHeader** \>在 web.config 中。**注意：**如果满足以下条件，则必须指定此属性的值**AuthenticationType**设置为**HTTPUserNamePassword**。  如果设置为**自动**，此属性是可选的。|  
        |**PasswordHeader**|这指定将用于将用户密码传递给服务的标头的名称。 有关 HTTP 标头的详细信息，请参阅"支持的自定义 HTTP 和 SOAP 标头"在 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)<br /><br /> 此外可以通过修改设置此值 <**endpointBehavior passwordHttpHeader**< 在 web.config 中。**注意：**如果满足以下条件，则必须指定此属性的值**AuthenticationType**设置为**HTTPUserNamePassword**。 如果设置为**自动**，此属性是可选的。|  
  
    3.  在设置所需的行为后, 单击**下一步**以继续。  
  
8.  上**配置服务终结点绑定和地址**页上，你可以配置为协定的地址和绑定属性。 选择在该协定**选择协定配置**列表，，然后输入所需的值以**配置的地址和协定绑定**对话框。  
  
    1.  选择**BindingConfiguration**绑定属性下的条目。 该向导仅支持基本 HTTP 绑定，因此绑定配置字段将自动设置为**System.ServiceModel.Configuration.BasicHttpBindingElement**。 若要更改此绑定的配置属性，单击省略号**...** 按钮。 若要使用的安全通信通道，必须始终设置**模式**属性**传输**。 这是默认值。  
  
    2.  选择**EndpointName**，然后输入终结点所需的名称。  
  
    3.  若要将应用所做的更改，请单击**应用**。  
  
9. 若要继续，请单击 **“下一步”**。 摘要页列出已选择的适配器操作以树结构。  
  
10. 查看摘要，并依次**完成**。  
  
11. 该向导创建 Web 项目，并将以下文件。  
  
    |文件|Description|  
    |----------|-----------------|  
    |.svc|WCF 代理到引用的服务文件。|  
    |.cs|实现 WCF 代理。|  
    |web.config|包含\<**终结点**\, \<**绑定**\>，和\<**行为**\>元素\<**系统。ServiceModel**\>|  
  
12. 将 WCF 服务项目发布。  
  
    1.  右键单击解决方案资源管理器中的项目，然后单击**发布**。  
  
    2.  在**发布网站**对话框中，指定的 WCF 服务的目标 URL。  
  
    3.  选择**允许更新此预编译的站点**。  
  
    4.  选择**使用固定命名和单个页程序集**。  
  
    5.  选择**启用强命名在预编译的程序集**，然后指定要使用的签名密钥。  
  
13. 若要发布网站，请单击**确定**。  
  
14. 验证已成功发布服务。  
  
    1.  启动 IIS 管理控制台。  单击**启动**，指向**管理工具**，然后单击**Internet Information Services**。  
  
    2.  导航到在其中发布服务的节点。  如果服务作为发布http://localhost/myservice，导航到**Internet Information Services**> **计算机名称**> **网站**>  **Default Web Site**> **myservice**。  
  
    3.  在右窗格中，右键单击.svc 文件中，，然后单击**浏览**。 网页出现时带有有关服务的信息。 你现在可以通过使用从客户端应用程序的 WCF 或 Web 服务调用使用此服务。 

## <a name="security"></a>Security
当适配器承载服务中时，从客户端应用程序的调用使用适配器安全桥将客户端凭据传递给适配器。  
  
 当 WCF 客户端身份验证发送到 WCF 服务时，通常服务使用的身份验证。 但是，对于适配器思路是捕获与基础的 LOB 系统一起使用的身份验证信息。 这被实现通过适配器安全桥，该桥呈现为终结点行为。 作为适配器开发人员，没有任何需要可实现以充分利用此功能;但是，在部署时该适配器，你必须考虑如何客户端将提供给服务的凭据。  
  
 如果您使用消息级安全性，适配器安全桥可以检索由上任何绑定的客户端应用程序发送 ClientCredentials。 如果使用基本 HTTP 绑定，你可以改为选择使用自定义标头来传递用户名和密码信息。 建议使用 WCF 提供的 ClientCredential 类传递凭据，但是许多 Web 服务客户端应用程序将需要使用自定义标头传递凭据。  
  
 下面是一个示例配置适配器查找中 ClientCredentials 客户端应用程序提供的凭据。 如果找不到，适配器，然后在指定的 HTTP 请求标头中查找。  
  
```  
<endpointBehaviors>  
   <behavior name="customEndpointBehavior">  
      <endpointBehavior usernameHttpHeader="UNHdr" passwordHttpHeader="PWHdr"  
         adapterSecurityBridgeType="Auto" />  
    </behavior>  
</endpointBehaviors>  
```      
  
## <a name="see-also"></a>另请参阅  
 [开发活动](../../esb-toolkit/development-activities.md)