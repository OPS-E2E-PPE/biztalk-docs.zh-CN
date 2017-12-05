---
title: "HTTPSSO （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- SSO, examples
- SSO, HTTP adapters
- examples, HTTP adapters
- HTTP adapters, SSO
- examples, SSO
ms.assetid: 322360df-81d2-4a73-9512-bda9382351a2
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41956d9e10cba87e0e1a1f44d49dd8ec8b6039bc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="httpsso-biztalk-server-sample"></a>HTTPSSO （BizTalk Server 示例）
HTTPSSO 示例演示如何使用 Microsoft 的企业单一登录 (SSO) 功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 适配器。  
  
> [!NOTE]
>  本示例不支持 64 位操作系统。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例演示一个端到端的应用方案，该方案使用 SSO 及 BizTalk HTTP 发送和接收适配器来模拟 SSO 如何允许用户在通过 Windows 的身份验证之后无需提供其他凭据即可登录到非 Microsoft Windows 系统。  
  
 此外，本示例还使用 SSO 的管理和映射模块来创建使用 SSO 的互操作客户端 DLL 的关联应用程序和 SSO 映射。  
  
 示例通过实现端到端方案的以下几个方面演示了 SSO 的使用方法：  
  
-   用户界面，由配置为使用 Windows 集成身份验证的一个 Microsoft Internet 信息服务 (IIS) 虚拟目录表示。  
  
-   后端系统，由配置为使用基本身份验证的一个 IIS 虚拟目录表示。  
  
-   后端数据库，由 SQL 示例数据库 Northwind 表示。  
  
 此示例假定你已安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SSO。 你必须具有管理员特权[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，IIS、 SSO，和在 Windows XP 专业版上的 COM +。 此外，您还必须是 SSO Administrators、BizTalk Server Administrators 和 BizTalk Isolated Host Users Windows 组的成员。  
  
 若要有效利用本示例，您应当充分了解 SSO 和 BizTalk HTTP 适配器。 例如，您应当知道关联应用程序在 SSO 的上下文环境下的含义。 有关这些主题的信息，请参阅[使用 SSO](../core/using-sso.md)。 另请参阅[HTTP 适配器](../core/http-adapter.md)。  
  
 在完成配置之后，本示例的工作方式将如下所示：  
  
1.  当你单击**完成**向导应用程序，它包含此示例的用户界面，在 Internet Explorer 的实例启动，并将传递 BizTalk HTTP 接收 DLL 的 URL。  
  
2.  在 SSO 的帮助下，BizTalk Server 可有效地将 HTTP 请求转发到 IIS 虚拟目录中的 EmployeeData.aspx 文件，该目录已配置为使用基本身份验证。 此 ASPX 文件模拟一个进入非 Windows 后端系统的入口点。 由于您所使用的是 SSO，所以 HTTP 请求中已包含配置的凭据，这些凭据模拟了所模拟后端系统的登录帐户。  
  
3.  该 ASPX 文件访问 SQL 示例数据库 Northwind 的一个修改过的版本，检索与所模拟后端系统凭据相对应的雇员数据。  
  
4.  ASPX 文件在 HTTP 响应中返回检索到的雇员数据。  
  
5.  BizTalk Server 将该 HTTP 响应发送到 Internet Explorer，后者向用户显示返回的雇员数据。  
  
 如果绕过 BizTalk Server 和 SSO，并且直接浏览 EmployeeData.aspx 文件，会显示一个 Windows 对话框，提示您输入凭据。  
  
 有关演示如何使用命令行实用工具 ssomanage.exe 配置 SSO，如创建关联应用程序和用户映射的示例，请参阅[管理 （BizTalk Server 示例）](../core/manage-biztalk-server-sample.md)。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\SSO\HTTPSSO\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs，SsoSample.csproj|本 HTTP SSO 示例的项目文件和相关文件。|  
|SsoSample.cs|作为本示例重要组成部分的 HTTP SSO 图形应用程序的顶层 Microsoft Visual C# 源文件。 此文件包含一个名为类中的 SSO 配置代码**SsoConfigurator**最终是此示例的点。|  
|\Scripts 文件夹的内容：<br /><br /> EmployeeData.aspx|用于在雇员发出请求以查看个人数据（无论是直接浏览还是使用 SSO）时访问和查询后端数据库（在本例中，为 SQL Northwind 数据库）。|  
|\Scripts 文件夹的内容：<br /><br /> ValidateUser.aspx|用于验证用户并报告用户是否为有效用户的简单测试（无论是直接浏览还是使用 SSO）。|  
|\UI 文件夹的内容：<br /><br /> AddApplication.cs、AddApplication.resx、AddMapping.cs、AddMapping.resx、App.ico、BtsPage.cs、BtsPage.resx、ExecutePage.cs、ExecutePage.resx、FinishPage.cs、FinishPage.resx、IisPage.cs、IisPage.resx、InfoPage.cs、InfoPage.resx、PageBase.cs、PageBase.resx、SsoPage.cs、SsoPage.resx、SsoSampleWizard.cs、SsoSampleWizard.resx、WelcomePage.cs、WelcomePage.resx、WorkPage.cs、WorkPage.resx|辅助性的 Visual C# 源文件及其关联的 XML 格式的资源文件，这些文件用于构成了示例重要组成部分的 HTTP SSO 图形应用程序。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-httpsso-sample"></a>生成和初始化 HTTPSSO 示例  
  
1.  创建 Microsoft Internet 信息服务 (IIS) 可用于进行基本身份验证的一个本地 Windows 帐户。 SSO 将 Windows 域帐户映射到该本地 Windows 帐户。 例如，可使用您的名字创建一个本地 Windows 帐户。  
  
    > [!NOTE]
    >  如果您使用的计算机是一台域控制器，可以创建域帐户并将您所登录的域帐户映射到此帐户。  
  
2.  使用 Microsoft SQL Server 企业管理器，打开**员工**表在 Northwind 示例数据库中，并将与你刚刚创建，包括各种示例数据的本地 Windows 帐户相对应的行列。 您在 Employees 表的 LastName 列中添加的值必须与您在步骤 1 中添加的本地 Windows 帐户的用户名相同。  
  
3.  确保 ASP.NET 帐户 (ASPNET) 对 Northwind 数据库拥有读取权限。  
  
4.  打开项目文件 SsoSample.csproj 使用 Visual Studio。  
  
5.  在“生成”  菜单上，单击“生成解决方案” 。  
  
    > [!NOTE]
    >  可能要求你保存解决方案文件，然后生成才能继续。  
  
     如果项目，找不到以下 BizTalk 程序集引用，将其删除，重新将其添加从指定的位置，并再次生成：  
  
    -   **Microsoft.BizTalk.ExplorerOM**。 默认情况下，Microsoft.BizTalk.ExplorerOM.dll 文件位于文件夹中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]开发人员工具\\。  
  
    -   **Microsoft.BizTalk.SSOClient.Interop**。 默认情况下，Microsoft.BizTalk.Interop.SSOClient.dll 文件位于文件夹中\< *ProgramFiles*\>上单一登录的 \Common Files\Enterprise\\。  
  
     这将产生可执行文件的以下文件夹中的 SsoSample.exe:  
  
     \<*示例路径*\>\SSO\HTTPSSO\bin\Debug\  
  
## <a name="running-this-sample"></a>运行本示例  
  
> [!NOTE]
>  如果在 IIS 6.0 上以辅助进程隔离模式运行本示例，将为两个虚拟目录都创建应用程序池。 Windows 帐户 （你可以配置在 Internet 信息服务管理器标识） 中，你必须手动配置这些两个应用程序池标识。  
  
#### <a name="to-run-the-httpsso-sample"></a>若要运行 HTTPSSO 示例  
  
1.  运行在以下文件夹中找到的可执行文件 SsoSample.exe:  
  
     \<*示例路径*\>\SSO\HTTPSSO\bin\Debug\  
  
     此示例向导应用程序打开。  
  
2.  在欢迎页上，配置 IIS、 SSO 和 BizTalk，接受默认设置，然后单击**下一步**。  
  
3.  在 IIS 配置页上，接受两个你想要创建，，然后单击的 IIS 虚拟目录的默认设置**下一步**。  
  
4.  在 SSO 配置页上，接受默认设置为关联应用程序，这是可访问使用**添加应用程序**按钮。  
  
5.  在 SSO 配置页上，接受大多数用户映射中，默认设置可访问使用**添加映射**按钮。 提供基于时生成并初始化此示例添加的本地 Windows 帐户的以下两个设置的值。  
  
    |设置|值|  
    |-------------|-----------|  
    |外部用户名称|设置为添加的本地 Windows 用户帐户名称。|  
    |外部用户密码|将设置为添加的本地 Windows 用户帐户密码。|  
  
6.  在 SSO 配置页面上单击**下一步**。  
  
7.  在 BizTalk 配置页上，接受默认设置为发送和接收端口，以此类推，，然后单击**下一步**。  
  
    > [!NOTE]
    >  你可以更改默认发送端口设置从**EmployeeData.aspx**到**ValidateUser.aspx**如果你想要查看简单的用户验证，而不是示例数据源自的员工表罗斯文 SQL 数据库。 进行此更改更改后单击浏览器中显示的输出的性质**完成**在步骤 9。  
  
8.  查看对应于正在执行的 IIS、 SSO 和 BizTalk 配置的状态消息。 你可以找到在此阶段运行的代码**IisConfigurator**， **SsoConfigurator**，和**BtsConfigurator** SsoSample.cs 文件中定义的类。 已完成配置后，单击**下一步**。  
  
9. 在向导应用程序的最后一页，接受默认设置**启动浏览器显示在**(选中的复选框和文本框中使用 URL http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?<message/>)，然后单击**完成**。  
  
     Internet Explorer 的实例将打开，并且很快显示添加到罗斯文 SQL 数据库的员工表的示例员工数据。  
  
 为了进行比较，可以跳过 BizTalk 和 SSO，并浏览直接到 ASPX 文件之一：  
  
-   http://localhost/SsoSampleServerApplication/ValidateUser.aspx  
  
-   http://localhost/SsoSampleServerApplication/EmployeeData.aspx  
  
 在这两种情况下，由于你绕过 BizTalk 和 SSO，会提示你对身份验证信息 （使用你之前创建的本地 Windows 帐户信息） 的 iis。  
  
## <a name="comments"></a>注释  
 SsoSample.exe 向导应用程序配置两个 IIS 虚拟目录：  
  
-   第一个虚拟目录使用 Windows 集成身份验证配置，并且对应于 BizTalk HTTP 接收 ISAPI 扩展插件。 它必须与 BTSHTTPReceive.dll 位于以下文件夹中的.dll 文件相关联：  
  
     \<*安装路径*\>\HttpReceive  
  
-   第二个虚拟目录配置使用基本身份验证和模拟接受要对用户进行身份验证的用户 ID 和密码的后端系统。 必须将其与一个关联或 ValidateUser.aspx 或 EmployeeData.aspx，ASPX 文件的其他位于以下文件夹中：  
  
     \<*示例路径*\>\SSO\HTTPSSO\Scripts  
  
 你可以使用 SsoSample.exe 向导应用程序配置一个或多个关联应用程序。 其中每项的关联应用程序，你可以创建一个或多个用户映射。 这些用户映射的每个映射到用来访问特定的后端系统帐户的 Windows 用户帐户。 在此示例中，该帐户是本地的 Windows 帐户的使用进行身份验证模拟真实的后端系统的第二个 IIS 虚拟目录。  
  
 若要重新运行此示例，你有若干种选择：  
  
-   浏览直接到 Internet 资源管理器中的以下 URL:  
  
     http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?<message/>  
  
-   向导再次运行应用程序，但清除所有的第一页上的配置复选框。  
  
-   运行一次向导应用程序、 配置复选框选择在第一页，但仔细适当地配置其他 BizTalk 项、 affiliate 应用程序和等等，以便不发生配置错误。  
  
 若要清理与此示例，请使用以下过程。  
  
#### <a name="to-clean-up-from-this-sample"></a>若要清理与此示例  
  
1.  根据具体情况，反向执行，删除本地 Windows 帐户等的手动配置。  
  
2.  删除与虚拟目录对应的 IIS 应用程序，然后删除本示例创建的 IIS 虚拟目录。  
  
3.  使用 BizTalk 管理控制台，取消登记与本示例关联的发送端口，然后删除该发送端口。 然后，删除与此示例关联的接收端口（及其接收位置）。  
  
4.  使用 Ssomanage 应用程序 (位于 \program Files\Enterprise 单一登录\\) 若要删除此示例的 SSO 应用程序：  
  
    ```  
    Ssomanage –deleteapp SsoSampleApplication  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [SSO（BizTalk Server 示例文件夹）](../core/sso-biztalk-server-samples-folder.md)