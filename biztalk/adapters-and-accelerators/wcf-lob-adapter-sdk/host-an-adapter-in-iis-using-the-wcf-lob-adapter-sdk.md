---
title: 在使用 WCF LOB 适配器 SDK 的 IIS 中适配器的宿主 |Microsoft Docs
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
ms.openlocfilehash: 51d6958bb740b3707748459281769077eb69d008
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363599"
---
# <a name="host-an-adapter-in-iis-using-the-wcf-lob-adapter-sdk"></a>在使用 WCF LOB 适配器 SDK 的 IIS 中适配器的宿主
本部分介绍如何使用生成的适配器宿主[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]在 Internet 信息服务 (IIS)。 有关其他托管选项的详细信息，请参阅[托管服务](https://msdn.microsoft.com/library/ms730158.aspx)。

## <a name="use-iis-and-aspnet"></a>使用 IIS 和 ASP.NET
 使用 ASP.NET 启用以发布使用 WCF LOB 适配器 SDK 创建的适配器，可以使用 IIS。 若要创建的适配器的宿主[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，为发布 WCF 服务配置 Internet 信息服务 (IIS)。 接下来，请考虑如何使用你的 WCF adapterwith ASP.NET。

 当承载在 IIS 中的 WCF 服务时，有两种可用的宿主模式： **-并行**和一个**SP.NET 兼容性模式**。 托管模式下的默认值为并行。 通过并行模式与托管解决方案的其他 WCF 的行为一致。 因此，在 IIS 中承载的 WCF 服务的行为与一个驻留在一个控制台应用程序中相同。 但是，这可能不需要由于 web 开发人员所预期的行为类似于 ASP.NET。 例如，在通过并行模式下，WCF 不符合任何基于 URL 的授权规则中指定`<system.web> <authorization>`web.config 的配置元素。  

 ASP.NET 兼容性模式允许 WCF 服务以使用 ASP.NET 中的所有功能和行为与 ASPX 页; 相同但是，必须采取其他步骤，创建您的 WCF 适配器以启用此功能时。 有关详细信息，请参阅： 

 [WCF 服务和 ASP.NET](https://msdn.microsoft.com/library/aa702682.aspx)

[在 Internet 信息服务中承载](https://msdn.microsoft.com/library/ms734710.aspx)

[托管服务的 WCF](https://msdn.microsoft.com/library/ms730158.aspx)

## <a name="use-the-wcf-adapter-service-development-wizard"></a>使用 WCF 适配器服务开发向导

使用[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]若要自动创建用于承载您的适配器在 Internet 信息服务 (IIS) 的 Web 项目。 然后可以通过使用 Windows Communication Framework (WCF) 或 Web 服务的客户端使用托管的适配器。  

### <a name="publish-an-adapter-as-a-wcf-service-hosted-in-iis"></a>将适配器作为 IIS 中承载的 WCF 服务发布  

1. 打开 [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]。 上**文件**菜单中，选择**新建**，然后选择**网站**。  

2. 在中**模板**，选择**Visual C#**，然后选择**WCF 适配器服务**。  

3. 请输入文件夹以保存该解决方案，然后选择**确定**。 **WCF 适配器服务开发向导**启动。  

4. 上**简介**页上，单击**下一步**。  

5. 上**选择操作**页上，指定要用于此托管服务的绑定、 协定和操作。  

   1.  在中**选择绑定**列表中，选择适配器绑定以使用，然后单击**配置**。 这将显示**配置适配器**对话框。 提供调用适配器以及检索操作的元数据所必需的值。  

   2.  上**安全**选项卡上，选择**客户端凭据类型**时将客户端凭据传递到适配器使用。  

       |凭据类型|Description|  
       |---------------------|-----------------|  
       |**无**|客户端不需要提供凭据。|  
       |**Windows**|客户端将使用 Windows 凭据。|  
       |**用户名**|客户端将提供的用户名和密码。|  
       |**证书**|客户端将使用 X.509 证书进行身份验证。 如果设置此值，请单击**浏览**中**客户端证书**区域中，并选择要使用的证书。|  

   3.  上**URI 属性**选项卡上，指定适配器所需的 URI 参数。 此选项卡中显示的条目中公开的属性因`ConnectionUri Properties`的适配器类。  

   4.  上**绑定属性**选项卡上，指定所需的适配器的绑定属性的值。 **常规**部分包含常用的设置，如超时值。 其他属性列出了根据自定义属性中公开你`AdapterBinding`类。  

6. 后指定配置值后，单击**Connect**。  

   1.  从**选择协定类型**列表中，选择要使用的协定。 这将填充**选择一个类别**树具有类别和通过此适配器执行的操作的列表控件。 如果适配器实现搜索功能通过`MetadataRetrievalClient`类，您可以输入搜索词**类别中的搜索**字段返回仅类别和包含搜索词的操作。  

       > [!NOTE]
       >  仅出站操作是可供选择。  

   2.  从**可用类别和操作**框中，选择要添加，并单击的项**添加**。 添加所需的项目后，单击**下一步**。  

7. 上**配置服务和终结点行为**页上，为此适配器设置所需的行为。  

   1.  **服务行为配置**部分包含控制服务行为的条目。 运行向导之后，可以通过编辑 web.config 文件来修改所选的服务行为。  

       |属性|Description|  
       |--------------|-----------------|  
       |**EnableMetadataExchange**|此值设置为 **，则返回 True** ，服务元数据发布到客户端请求。 此外可以通过修改设置这\< **serviceMetadata httpGetEnabled =""** \>在 web.config 中。默认值是**False**|  
       |**IncludeExceptionDetailsinFault**|此值设置为 **，则返回 True**结果中将托管的异常信息返回到 SOAP 错误中的客户端。 此外可以通过修改设置这\< **serviceDebug usingincludeExceptionDetailInFaults =""** \>在 web.config 中。默认值是**False**。|  
       |**名称**|服务行为配置名称。|  
       |**UseServiceCertificate**|此值确定服务是否将使用 X.509 证书向客户端进程验证自身身份。 默认值是 **，则返回 True**。|  
       |**FindValue**|此值用于搜索特定的 X.509 证书的证书存储中。 此外可以通过修改设置这\< **serviceCredentials findValue =""** \> web.config 中**注意：** 请为此属性仅当**UseServiceCertificate**设置为**True**。|  
       |**StoreLocation**|此值指定系统存储位置，搜索指定的证书。 此外可以通过修改设置这\< **serviceCredentials storeLocation =""** \>在 web.config 中。**注意：** 请为此属性仅当**UseServiceCertificate**设置为**True**。|  
       |**StoreName**|此值指定要搜索指定的证书的特定系统存储区。 此外可以通过修改设置这\< **serviceCredentials storeName =""** \> web.config 中**注意：** 请为此属性仅当**UseServiceCertificate**设置为**True**。|  
       |**X509FindType**|若要查找要使用的特定证书前面指定的搜索将与 FindValue 的类型。 此外可以通过修改设置这\< **serviceCredentials x509FindType =""** \> web.config 中**注意：** 请为此属性仅当**UseServiceCertificate**设置为**True**。|  

   2.  **终结点行为配置**部分控制终结点行为。  

       |属性|Description|  
       |--------------|-----------------|  
       |**名称**|终结点行为的名称|  
       |**AuthenticationType**|此值指示适配器获取客户端凭据的传入文档的位置。 若要启用客户端指定客户端证书向服务进行身份验证，请将此设置为**ClientCredentialUsernamePassword**。 若要启用客户端的 HTTP 标头的一部分指定的用户名和密码，请将此设置为**HTTPUsernamePassword**。 若要启用客户端指定客户端凭据接口通过凭据，请将此设置为**自动**。如果此操作失败，客户端可以将作为 HTTP 标头的一部分传递的凭据。<br /><br /> 此值还可以设置通过修改\< **endpointBehavior adapterSecurityBridgeType** \>在 web.config 中。默认值是**自动**。|  
       |**UsernameHeader**|指定将用于将用户名称传递给该服务的标头的名称。 有关 HTTP 标头的详细信息，请参阅"支持的自定义 HTTP 和 SOAP 标头"网址 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)<br /><br /> 此值还可以设置通过修改\< **endpointBehavior usernameHttpHeader** \>在 web.config 中。**注意：** 如果满足以下条件，则必须指定此属性的值**AuthenticationType**设置为**HTTPUserNamePassword**。  如果设置为**自动**，此为可选属性。|  
       |**PasswordHeader**|指定将用于将用户密码传递给该服务的标头的名称。 有关 HTTP 标头的详细信息，请参阅"支持的自定义 HTTP 和 SOAP 标头"网址 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)<br /><br /> 此外可以通过修改设置此值 <**endpointBehavior passwordHttpHeader**< web.config 中。**注意：** 如果满足以下条件，则必须指定此属性的值**AuthenticationType**设置为**HTTPUserNamePassword**。 如果设置为**自动**，此为可选属性。|  

   3.  设置后所需的行为，请单击**下一步**以继续。  

8. 上**配置服务终结点绑定和地址**页上，可以配置为协定的地址和绑定属性。 选择中的协定**选择用于配置的协定**列表，，然后输入所需的值以**配置地址和协定绑定**对话框。  

   1.  选择**BindingConfiguration**绑定属性下的条目。 该向导仅支持基本 HTTP 绑定，因此绑定配置字段将自动设置为**System.ServiceModel.Configuration.BasicHttpBindingElement**。 若要更改此绑定的配置属性，单击省略号 **...** 按钮。 若要使用的安全通信通道，必须始终设置**模式下**属性设置为**传输**。 这是默认值。  

   2.  选择**EndpointName**，然后输入所需的终结点的名称。  

   3.  若要将应用所做的更改，请单击**应用**。  

9. 若要继续，请单击 **“下一步”**。 摘要页列出了所选择的适配器操作的树状结构。  

10. 查看摘要，然后依次**完成**。  

11. 该向导创建 Web 项目并添加以下文件。  


    |    文件    |                                                Description                                                 |
    |------------|------------------------------------------------------------------------------------------------------------|
    |    .svc    |                               为 WCF 代理引用的服务文件。                               |
    |    .cs     |                                         实现 WCF 代理。                                          |
    | web.config | 包含\<**终结点**\, \<**绑定**\>，并\<**行为**\>元素\<**系统。ServiceModel**\> |


12. 发布 WCF 服务项目。  

    1.  右键单击解决方案资源管理器中的项目，然后单击**发布**。  

    2.  在中**发布网站**对话框中指定的 WCF 服务的目标 URL。  

    3.  选择**允许更新此预编译的站点**。  

    4.  选择**使用固定命名和单页程序集**。  

    5.  选择**启用强命名在预编译程序集**，然后指定要使用的签名密钥。  

13. 若要发布 Web 站点，请单击**确定**。  

14. 验证已成功发布服务。  

    1.  启动 IIS 管理控制台。  单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services**。  

    2.  导航到发布服务的节点。  如果该服务已作为 http://localhost/myservice ，导航到**Internet Information Services**> **计算机名称**> **网站**>  **Default Web Site**> **myservice**。  

    3.  在右窗格中，右键单击的.svc 文件，并单击**浏览**。 Web 页会显示有关该服务的信息。 你现在可以通过使用 WCF 或 Web 服务调用客户端应用程序使用此服务。 

## <a name="security"></a>安全性
当适配器的宿主服务中时，来自客户端应用程序调用使用适配器安全桥将客户端凭据传递给适配器。  

 当 WCF 客户端发送到 WCF 服务的身份验证时，通常服务使用的身份验证。 但是，对于适配器，旨在捕获与基础 LOB 系统配合使用的身份验证信息。 这是通过适配器安全桥接，呈现为终结点行为的实现。 作为适配器开发人员，则不执行任何需要实现才能利用此功能;但是，在部署适配器时，必须考虑如何在客户端将提供对服务的凭据。  

 如果使用消息级安全性，适配器安全桥可以检索 ClientCredentials 发送的任何绑定上的客户端应用程序。 如果使用基本 HTTP 绑定，则可以改为选择使用自定义标头来传递用户名和密码信息。 建议使用 WCF 提供的客户端凭据类来传递凭据，但是，许多 Web 服务客户端应用程序将需要使用自定义标头来传递凭据。  

 下面是一个示例配置适配器凭据在客户端应用程序提供了 Clientcredential 中查找的位置。 如果找不到，适配器，然后在指定的 HTTP 请求标头中查找。  

```  
<endpointBehaviors>  
   <behavior name="customEndpointBehavior">  
      <endpointBehavior usernameHttpHeader="UNHdr" passwordHttpHeader="PWHdr"  
         adapterSecurityBridgeType="Auto" />  
    </behavior>  
</endpointBehaviors>  
```      

## <a name="see-also"></a>请参阅  
 [开发活动](../../esb-toolkit/development-activities.md)