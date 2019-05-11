---
title: HTTPSSO （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- SSO, examples
- SSO, HTTP adapters
- examples, HTTP adapters
- HTTP adapters, SSO
- examples, SSO
ms.assetid: 322360df-81d2-4a73-9512-bda9382351a2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 061753526738bfc134fc89b459b7bef87a68f216
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382835"
---
# <a name="httpsso-biztalk-server-sample"></a>HTTPSSO （BizTalk Server 示例）
HTTPSSO 示例演示如何使用 Microsoft 企业单一登录 (SSO) 功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 适配器。  

> [!NOTE]
>  此示例不支持在 64 位操作系统上。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何使用 SSO 及 BizTalk HTTP 发送和接收适配器来模拟 SSO 如何允许用户在无需提供其他凭据即可登录到非 Microsoft Windows 系统 Windows 的身份验证之后的端到端方案。  

 该示例还使用 SSO 的管理和映射模块来创建关联应用程序和使用互操作客户端 DLL 的 SSO 的 SSO 映射。  

 此示例演示使用 SSO 通过实现端到端方案的以下方面：  

- 用户界面，由 Microsoft Internet 信息服务 (IIS) 虚拟目录配置为使用 Windows 集成身份验证。  

- 后端系统，由配置为使用基本身份验证的 IIS 虚拟目录。  

- 后端数据库，由 SQL 示例数据库 Northwind 表示。  

  此示例假定你已安装了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SSO。 必须具有管理员特权的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，IIS、 SSO 和 COM + on Windows XP Professional。 您必须是 SSO Administrators、 BizTalk Server Administrators 和 BizTalk Isolated 主机用户 Windows 组的成员。  

  有效地使用此示例假定您已充分了解 SSO 和 BizTalk HTTP 适配器。 例如，您应该知道哪些关联应用程序是 SSO 的上下文中。 有关这些主题的信息，请参阅[使用 SSO](../core/using-sso.md)。 另请参阅[HTTP 适配器](../core/http-adapter.md)。  

  完成配置后，此示例的工作方式如下：  

1. 当您单击**完成**在此示例的用户界面的向导应用程序，Internet Explorer 的实例启动并传递 BizTalk HTTP Receive DLL 的 URL。  

2. BizTalk Server 的 SSO，帮助有效 HTTP 将请求转发到已配置了基本身份验证的 IIS 虚拟目录中的 EmployeeData.aspx 文件。 此 ASPX 文件模拟非 Windows 后端系统的入口点。 使用 SSO，因为 HTTP 请求包括模拟模拟后端系统的登录帐户的凭据配置。  

3. ASPX 文件访问 SQL 示例数据库 Northwind 来检索与模拟的后端系统凭据相对应的员工数据的修改的版本。  

4. ASPX 文件返回 HTTP 响应中检索到的雇员数据。  

5. BizTalk Server 将路由到 Internet 资源管理器，它为用户显示返回的雇员数据的 HTTP 响应。  

   如果绕过 BizTalk Server 和 SSO，并直接浏览 EmployeeData.aspx 文件，Windows 对话框将提示您输入凭据。  

   有关演示如何使用命令行实用工具 ssomanage.exe 配置 SSO，例如创建关联应用程序和用户映射的示例，请参阅[管理 （BizTalk Server 示例）](../core/manage-biztalk-server-sample.md)。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\SSO\HTTPSSO\  

 下表显示了本示例中的文件及其用途说明：  

|文件|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs SsoSample.csproj|项目和相关的文件，本 HTTP SSO 示例。|  
|SsoSample.cs|顶层 Microsoft VisualC#的 HTTP SSO 图形应用程序的重要组成部分本示例的源文件。 此文件包含一个名为类中的 SSO 配置代码**SsoConfigurator**最终是此示例的点。|  
|在 \Scripts 文件夹中：<br /><br /> EmployeeData.aspx|用于访问和查询后端数据库 （在本例中为 SQL Northwind 数据库） 时雇员发出请求以直接或通过使用 SSO 查看个人数据。|  
|在 \Scripts 文件夹中：<br /><br /> ValidateUser.aspx|简单的测试来验证用户和报表，如果该用户为有效，直接或通过使用 SSO。|  
|\UI 文件夹的位置：<br /><br /> AddApplication.cs、 AddApplication.resx、 AddMapping.cs、 AddMapping.resx、 App.ico、 BtsPage.cs、 BtsPage.resx、 ExecutePage.cs、 ExecutePage.resx、 FinishPage.cs、 FinishPage.resx、 IisPage.cs、 IisPage.resx、 InfoPage.cs、 InfoPage.resx、 PageBase.cs，PageBase.resx、 SsoPage.cs、 SsoPage.resx、 SsoSampleWizard.cs、 SsoSampleWizard.resx、 WelcomePage.cs、 WelcomePage.resx、 WorkPage.cs、 WorkPage.resx|辅助 VisualC#源代码文件和其关联的 XML 格式的资源文件，构成了很多此示例的 HTTP SSO 图形应用程序。|  

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  

#### <a name="to-build-and-initialize-the-httpsso-sample"></a>若要生成和初始化 HTTPSSO 示例  

1. 创建 Microsoft Internet 信息服务 (IIS) 可用于基本身份验证的本地 Windows 帐户。 SSO 将 Windows 域帐户映射到此本地 Windows 帐户。 例如，使用你的姓氏创建一个本地 Windows 帐户。  

   > [!NOTE]
   >  如果在域控制器上运行，可以创建域帐户，并将映射到此帐户的域帐户上的已登录。  

2. 使用 Microsoft SQL Server 企业管理器，打开**员工**表中 Northwind 示例数据库，以及如何将你刚刚创建，添加的各种示例数据的本地 Windows 帐户对应的行列。 您将添加到雇员表中的姓氏列的值必须是在步骤 1 中添加的本地 Windows 帐户的用户名相同。  

3. 确保 ASP.NET 帐户 (ASPNET) 具有读取到 Northwind 数据库的权限。  

4. 打开项目文件 SsoSample.csproj 使用 Visual Studio。  

5. 在“生成”  菜单上，单击“生成解决方案” 。  

   > [!NOTE]
   >  您可能需要生成可以继续操作之前保存解决方案文件。  

    如果您找不到以下 BizTalk 程序集引用该项目，将其删除、 重新将其添加从指示的位置，并重新生成：  

   - **Microsoft.BizTalk.ExplorerOM**. 默认情况下，Microsoft.BizTalk.ExplorerOM.dll 文件位于文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]开发人员工具\\。  

   - **Microsoft.BizTalk.SSOClient.Interop**. 默认情况下，Microsoft.BizTalk.Interop.SSOClient.dll 文件位于文件夹\< *ProgramFiles*\>上单一登录的 \Common Files\Enterprise\\。  

     这会生成可执行文件 SsoSample.exe 以下文件夹中：  

     \<*示例路径*\>\SSO\HTTPSSO\bin\Debug\  

## <a name="running-this-sample"></a>运行本示例  

> [!NOTE]
>  如果工作进程隔离模式在 IIS 6.0 上运行此示例，为这两个虚拟目录都创建应用程序池。 Windows 帐户 （你可以配置在 Internet 信息服务管理器标识） 中，必须手动配置这些两个应用程序池标识。  

#### <a name="to-run-the-httpsso-sample"></a>若要运行 HTTPSSO 示例  

1. 运行以下文件夹中找到的可执行文件 SsoSample.exe:  

    \<*示例路径*\>\SSO\HTTPSSO\bin\Debug\  

    此示例的向导应用程序将打开。  

2. 在欢迎页上，配置 IIS、 SSO 和 BizTalk 中，接受默认设置，然后单击**下一步**。  

3. 在 IIS 配置页上，接受以创建，然后单击所需的两个 IIS 虚拟目录的默认设置**下一步**。  

4. 在 SSO 配置页上，接受关联应用程序，这是可访问使用的默认设置**添加应用程序**按钮。  

5. 在 SSO 配置页上，接受用户映射的默认设置的大多数可使用**添加映射**按钮。 为基于时生成并初始化本示例添加的本地 Windows 帐户的以下两个设置提供值。  


   |        设置         |                         ReplTest1                         |
   |------------------------|-------------------------------------------------------|
   |   外部用户名称   |   将设置为添加的本地 Windows 用户帐户名称。   |
   | 外部用户密码 | 将设置为添加的本地 Windows 用户帐户密码。 |


6. 在 SSO 配置页上，单击**下一步**。  

7. 在 BizTalk 配置页上，接受默认设置为发送和接收端口和等等，然后依次**下一步**。  

   > [!NOTE]
   >  你可以将默认发送端口设置从**EmployeeData.aspx**到**ValidateUser.aspx**如果你想要查看简单的用户验证，而不是从 Employee 表的示例数据提取Northwinds SQL 数据库。 进行此更改将更改在单击后显示在浏览器中的输出的性质**完成**步骤 9 中。  

8. 查看与正在执行的 IIS、 SSO 和 BizTalk 配置相对应的状态消息。 您可以找到在此阶段中运行的代码**IisConfigurator**， **SsoConfigurator**，并**BtsConfigurator**文件 SsoSample.cs 中定义的类。 配置完成后，单击**下一步**。  

9. 在向导应用程序的最后一页上，接受默认设置**启动浏览器显示在**(选中的复选框和文本框中的 url http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll? <message/>)，然后单击**完成**。  

     Internet Explorer 的实例将打开，并很快显示示例员工数据添加到 Northwinds SQL 数据库的 Employee 表。  

   为方便比较，可以绕过 BizTalk 和 SSO 和直接浏览到 ASPX 文件之一：  

- http://localhost/SsoSampleServerApplication/ValidateUser.aspx  

- http://localhost/SsoSampleServerApplication/EmployeeData.aspx  

  在这两种情况下，因为您绕过 BizTalk 和 SSO，系统会提示对身份验证信息由 IIS （使用以前创建的本地 Windows 帐户信息）。  

## <a name="comments"></a>注释  
 SsoSample.exe 向导应用程序配置两个 IIS 虚拟目录：  

- 第一个虚拟目录使用 Windows 集成身份验证配置，对应于 BizTalk HTTP 接收 ISAPI 扩展。 它必须与 BTSHTTPReceive.dll 位于以下文件夹中的.dll 文件相关联：  

   \<*Install Path*\>\HttpReceive  

- 第二个虚拟目录配置基本身份验证和模拟后端系统接受用户进行身份验证的用户 ID 和密码。 必须将其与一个关联或其他的 ASPX 文件、 ValidateUser.aspx 或 EmployeeData.aspx，位于以下文件夹中：  

   \<*示例路径*\>\SSO\HTTPSSO\Scripts  

  您可以使用 SsoSample.exe 向导应用程序配置一个或多个关联应用程序。 每个关联应用程序，可以创建一个或多个用户映射。 每个用户映射将 Windows 用户帐户映射到用于访问特定的后端系统的帐户。 在此示例中，该帐户是本地的 Windows 帐户，用于使用模拟正版的后端系统的第二个 IIS 虚拟目录进行身份验证。  

  若要重新运行此示例，可以选择多种方法：  

- 直接浏览到在 Internet Explorer 中的以下 URL:  

   http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?<message/>  

- 向导再次运行应用程序，但清除所有的第一页上的配置复选框。  

- 向导再次运行应用程序、 配置复选框选择在第一页上，但仔细适当地配置其他 BizTalk 项目、 关联应用程序中，依次类推，以便不会发生配置错误。  

  若要清理本示例中，使用以下过程。  

#### <a name="to-clean-up-from-this-sample"></a>若要清理本示例  

1.  根据需要，反向执行，如删除本地 Windows 帐户的手动配置。  

2.  删除 IIS 应用程序对应的虚拟目录，然后再删除此示例创建的 IIS 虚拟目录。  

3.  使用 BizTalk 管理控制台中，取消登记，然后再删除此示例与关联的发送端口。 然后，删除与此示例相关联的接收端口 （和其接收位置）。  

4.  使用 Ssomanage 应用程序 (位于 Files\Enterprise Single Sign-on \Program Files\Common\\) 若要删除此示例的 SSO 应用程序：  

    ```  
    Ssomanage –deleteapp SsoSampleApplication  
    ```  

## <a name="see-also"></a>请参阅  
 [SSO（BizTalk Server 示例文件夹）](../core/sso-biztalk-server-samples-folder.md)