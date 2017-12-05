---
title: "准则用于实现在多服务器 BizTalk 安装上的 Active Directory 权限 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 315e25c4-b21d-4b5f-a1d2-1e2777b57f9e
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ff7b45e560278053cec99208fd06917d079d6b8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="guidelines-for-implementing-active-directory-permissions-on-multi-server-biztalk-installations"></a>准则用于实现在多服务器 BizTalk 安装上的 Active Directory 权限
本主题介绍用于创建 Active Directory 组织单位的准则，Active Directory 组织单位由在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装中使用的用户帐户和组构成。  
  
 此处创建的这些帐户不需要在域中具有超出普通用户的权限。 域帐户可能需要在包括以下项的信任边界内的提升的权限：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]（在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务器上）  
  
-   Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]  
  
-   外部数据库 1  
  
-   外部数据库 2  
  
-   外部数据库*N*  
  
 例如，可能需要授予某个域帐户对作为外部数据库宿主的系统执行某些操作的权限。 在其他情况下，某个帐户可能需要将某一文件写入文件存放文件夹，因此要求对该文件夹具有写访问权限。  
  
 使用**Active Directory 用户和计算机**控制台来创建和管理域用户和组帐户。 单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。  
  
## <a name="biztalk-server-installation-and-configuration-account"></a>BizTalk Server 安装和配置帐户  
 在开发环境中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置向导要求使用对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 系统具有管理权限的帐户。 一旦设置和配置完成，可以立即吊销权限或禁用帐户。 帐户必须还属于若干 BizTalk 组，下面的几节中将对此予以介绍。  
  
> [!NOTE]
>  如果用于安装的帐户与服务器不属于同一 Active Directory 目录林，您将无法配置 SSO 组件。 如果你没有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序帐户，请将本地管理员帐户用于 SSO 配置。 此方法可能会在安装期间造成其他问题，例如，需要使用不同凭据登录到资源。  
  
## <a name="biztalk-server-development-accounts"></a>BizTalk Server 开发帐户  
 执行操作的个人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发需要访问的适配器、 接收和发送处理程序，并接收位置。 此访问需要的域开发人员组的成员**BizTalk Server Administrators**和**SSO Affiliate Administrators**组。  
  
> [!NOTE]
>  Active Directory 对可以包含外来域用户的组的类型具有限制，并且对可在其他组中包含的组类型具有限制。 下面创建的组和帐户在单个域上的多服务器环境中进行了测试。  
  
## <a name="biztalk-server-deployment-accounts"></a>BizTalk Server 部署帐户  
 部署的个人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序将需要为本地系统上的管理员，并且可能需要在环境中的其他权限。 本主题中为此目的而引用了 BizTalk Server 部署帐户。  
  
 此访问需要的成员的域部署组**BizTalk Server Administrators**和**SSO Affiliate Administrators**组。  
  
> [!NOTE]
>  如果用于安装的帐户与服务器不属于同一 Active Directory 目录林，您将无法配置 SSO 组件。 如果您不具有 BizTalk Server 部署帐户，则使用本地管理员帐户进行 SSO 配置。 此方法可能会在安装期间造成其他问题，例如，需要使用不同凭据登录到资源。  
  
## <a name="biztalk-server-support-accounts"></a>BizTalk Server 支持帐户  
 支持 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序的个体将需要是本地系统上的管理员。 本主题中为此目的而引用了 BizTalk 支持帐户。  
  
 此访问需要的域支持组的成员**BizTalk Server Administrators**组。  
  
## <a name="sql-server-service-accounts"></a>SQL Server 服务帐户  
 运行 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 实例的服务必须与安装、开发和部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件的帐户属于同一 Active Directory 域。  
  
-   使用**SQLAdmin**执行 （交互式登录） 的管理功能。  
  
-   使用**SQLService**管理服务 （没有交互式登录）。  
  
-   使用**SQLAccess**访问外部数据库。  
  
-   SQLAdmin 必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 系统上本地管理员组的成员。  
  
-   SQLService 必须是本地 Administrators 组的成员上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]系统和需要授予**作为服务登录**用户权限。  
  
-   SQLAccess 需要对远程数据库服务器具有适当的权限。  
  
 **SQL 帐户：**  
  
|**用户名**|**First Name**|**Last Name**|**全名**|  
|-------------------|--------------------|-------------------|-------------------|  
|SQLService|SQL|SQLService|SQL 服务帐户|  
|SQLAdmin|管理员|SQLService|SQL 管理员帐户|  
|SQLAccess|访问|SQLService|SQL 访问帐户|  
  
 根据公司标准设置帐户密码。  
  
> [!IMPORTANT]
>  在运行 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的计算机上，修改 SQL Server 和 SQLServerAgent 服务的启动参数，以便使用 SQLService 帐户和凭据。  
  
> [!NOTE]
>  用户名字段是示例；您可能需要更改这些名称以避免与其他 Active Directory 帐户冲突。  
  
## <a name="windows-sharepoint-services-account"></a>Windows SharePoint Services 帐户  
 Windows SharePoint Services 帐户必须在安装 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 前创建。  
  
 建议和说明[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]帐户：  
  
-   使用 SharePoint 管理员帐户 (SPAdmin) 执行管理功能、SharePoint 定时服务和所有 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 访问。  
  
-   SPAdmin 是站点所有者并且将需要电子邮件别名。  
  
-   SPAdmin 必须是本地 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上的本地管理员组的成员（Windows SharePoint Services 安装程序执行此要求）。  
  
-   SPAdmin 必须在 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 计算机上具有安全管理员和数据库创建者角色（Windows SharePoint Services 安装程序执行此要求）。  
  
 **Sharepoint 帐户：**  
  
|**用户名**|**First Name**|**Last Name**|**全名**|  
|-------------------|--------------------|-------------------|-------------------|  
|SPAdmin|管理员|SPService|SharePoint 管理员帐户|  
  
 根据公司标准设置帐户密码，并且能够在配置过程中检索这些密码。 请参阅**密码**问题周围的本主题的部分生成密码。  
  
> [!NOTE]
>  此用户名字段是个示例；您可能需要更改此名称以保护其他 AD 帐户。  
  
> [!IMPORTANT]
>  在运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上安装 Windows SharePoint Services 后，请确认 SharePoint 定时服务的启动参数正在使用 SPAdmin 帐户和凭据。  
  
## <a name="biztalk-groups-and-users"></a>BizTalk 组和用户  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组和用户必须在运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置向导之前创建。 在单系统安装中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用配置期间创建的本地组和帐户。 但是，如果部署单独的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机或将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 安装在两个不同的计算机上，您必须使用域用户和组帐户。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置向导无法创建域帐户。  
  
 有关 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务和用户帐户的建议和说明：  
  
-   为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建组织单位 (OU)。 所有帐户和组都将属于此 OU。  
  
-   全名应该有描述性，下面列表中的名称应该使安装人员可以在配置期间选择正确的组/帐户/用户。  
  
-   名字和姓氏是可选的；包括它们只是为了一致性。  
  
-   区别**BTService**和**BTUser**是指服务帐户 (automatons) 和泛型/共享人类用户。  
  
-   创建域帐户并通过 ADSI 脚本填充它们，以便用于上游环境的用户和组帐户的创建。  
  
 **BizTalk 服务帐户**  
  
|**用户名**|**First Name**|**Last Name**|**全名**|  
|-------------------|--------------------|-------------------|-------------------|  
|BTService|BTS|BTService|BizTalk 服务帐户|  
|BTServiceHost|主机|BTService|BizTalk 主机实例帐户|  
|BTServiceHostIso|HostIso|BTService|BizTalk 独立主机实例帐户|  
|SSOService|SSO|BTService|企业单一登录服务|  
|BTServiceREU|REU|BTService|规则引擎更新服务|  
  
 根据公司和环境标准设置用户名（例如 devBTService、alphaBTService）。 根据公司标准设置帐户密码，并且能够为配置步骤检索这些密码。 请参阅**密码注意事项开发**问题周围的本主题的部分生成密码。  
  
 安装人员将注意到服务帐户具有很高的粒度，具有与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 所创建的服务的接近一对一的映射。 这一粒度允许公司 IT 安全人员根据需要跟踪或限制访问。 建议采用该粒度，但由系统设计人员和企业安全人员确定在企业环境中是否需要这一粒度。  
  
 前一组中的服务帐户旨在仅用于自动访问，而不是针对用户交互式登录。  
  
#### <a name="to-set-the-appropriate-account-options"></a>设置适当的帐户选项  
  
1.  在**Active Directory 用户和计算机**控制台，单击以展开域，，然后单击以展开**用户**容器。  
  
2.  右键单击的帐户，然后选择**属性**以显示**属性**对话框中的帐户。  
  
3.  单击**帐户**选项卡**属性**对话框。  
  
4.  单击以选中以下选项：  
  
    -   **用户不能更改密码**(企业安全将批处理更改的密码)。  
  
    -   **密码永不过期**  
  
5.  单击**日志到**按钮以显示**登录的工作站**对话框。  
  
6.  单击此选项以**以下计算机**，添加每台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，然后单击**确定**。  
  
7.  单击**远程控制**选项卡**属性**对话框中，然后单击以清除选项**启用远程控制**。  
  
8.  单击**终端服务配置文件**选项卡**属性**对话框。  
  
9. 单击以检查选项**拒绝此用户的权限登录到任何终端服务器**。  
  
10. 单击**确定**关闭**属性**对话框中的帐户。  
  
11. 对每个服务帐户重复步骤 3 至 10。  
  
 **BizTalk 用户帐户**  
  
|**用户名**|**First Name**|**Last Name**|**全名**|  
|-------------------|--------------------|-------------------|-------------------|  
|BTUserAdmin|管理员|BTUser|BizTalk 管理用户帐户|  
|BTUserDeploy|部署|BTUser|BizTalk 部署用户帐户|  
|BTUserHostInstance|HostInstance|BTUser|BizTalk 主机实例帐户|  
|BTUserHostIsolated|IsolatedlHost|BTUser|BizTalk 独立主机实例帐户|  
|BTUserInstall|Install|BTUser|BizTalk 安装用户帐户|  
|BTUserSupport|支持|BTUser|BizTalk 支持访问帐户|  
  
#### <a name="to-set-the-appropriate-account-options-follow-these-steps"></a>若要设置适当的帐户选项，请执行以下步骤  
  
1.  在**Active Directory 用户和计算机**控制台单击以展开域，然后单击以展开**用户**容器。  
  
2.  右键单击的帐户，然后选择**属性**以显示**属性**对话框中的帐户。  
  
3.  单击**帐户**选项卡**属性**对话框。  
  
4.  单击以选中以下选项：  
  
    -   **用户不能更改密码**(企业安全将批处理更改的密码)。  
  
    -   **密码永不过期**  
  
5.  单击**日志到**按钮以显示**登录的工作站**对话框。  
  
6.  单击此选项以**以下计算机**，添加每台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，然后单击**确定**。  
  
7.  单击**远程控制**选项卡**属性**对话框中，然后单击要检查的选项**启用远程控制**。  
  
8.  单击**终端服务配置文件**选项卡**属性**对话框。  
  
9. 单击以清除选项**拒绝此用户的权限登录到任何终端服务器**。  
  
10. 单击**确定**关闭**属性**对话框中的帐户。  
  
11. 对每个用户帐户重复步骤 3 至 10。  
  
    > [!NOTE]
    >  如果要将提供给它们的角色分配给实际用户，则可以禁用上述任何帐户。 在版本 1 和版本 2 的初期阶段中，假定这些帐户用于开发、测试版测试和 beta 测试环境。  
  
 **BizTalk 组帐户**  
  
|**组名称**|**组类型**|**成员**|  
|--------------------|--------------------|-----------------|  
|BizTalk Application Users|全局或通用|-BTServiceHost<br />-BTUserHostInstance|  
|BizTalk 开发用户|全局或通用|（本地域帐户的开发用户）**注意：**作为最佳做法是，不要启用向上行环境中的 BizTalk 开发用户组。|  
|BizTalk 部署用户|全局或通用|（部署用户的本地域帐户）|  
|BizTalk 主机用户|全局或通用|BTUserHostInstance|  
|BizTalk Isolated Host Users|全局或通用|-BTServiceHostIso<br />-BTUserHostInstance|  
|BizTalk Server Administrators|全局或通用|-BTUserAdmin<br />-BTUserInstall<br />-BizTalk 开发用户<br />-BizTalk 部署用户|  
|BizTalk 支持用户|全局或通用|BTUserSupport（支持用户的本地域帐户）|  
|SSO Administrators|全局或通用|-SSOService<br />-BTUserInstall<br />本地管理员|  
|SSO Affiliate Administrators|全局或通用|-BizTalk 开发用户<br />-BizTalk 部署用户<br />-BTServiceHostIso<br />-   \<控制台用户\>|  
|Windows SharePoint Services 管理员|全局或通用|-SPAdmin<br />-BTUserInstall<br />-BTUserDeploy<br />-BizTalk 开发用户<br />-BizTalk 部署用户|  
  
 有关域组的建议和说明：  
  
-   在安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 前创建组和添加成员。  
  
-   域组可以为全局组或通用组。  
  
-   使用 *\<DomainName\>\\< 用户名\>*在配置向导中指定的域帐户信息时。  
  
-   组和用户/服务帐户必须属于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机所属于的域（配置向导将对此进行检查并且将不会显示包含来自其他域的帐户的帐户或组）。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 对于所有群集方案都要求使用域帐户。  
  
-   在安装时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，控制台用户必须是以下组的成员：  
  
    -   BizTalk Server Administrators  
  
    -   SSO Administrators（只在配置主密钥服务器时）  
  
    -   Windows 管理员  
  
    -   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理员  
  
    -   OLAP 管理员  
  
     BTUserInstall 帐户应该用于安装和配置，并且在完成配置后应被禁用。  
  
-   若要允许消息事件和服务实例跟踪以附加到调试器的业务流程，开发人员需要属于 BizTalk Server Administrators 组中，上面概括的部分中**BizTalk 开发帐户**.  
  
## <a name="local-administrator-accounts"></a>本地管理员帐户  
 确认或将以下帐户和帐户组添加到 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 计算机上的本地管理员组：  
  
-   Domain\BTUserInstall（在完成配置后禁用）  
  
-   Domain\BTUserDeploy（在完成部署后在生产中禁用）  
  
-   Domain\SPAdmin  
  
-   Domain\SQLAdmin  
  
-   Domain\SQLService  
  
-   Domain\BizTalk 开发用户 （在中省略了行的环境）  
  
-   域\BizTalk 部署用户（在开发环境中忽略）  
  
 确认或将以下帐户和帐户组添加到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上的本地管理员组：  
  
-   Domain\BTUserInstall（在完成配置后禁用）  
  
-   Domain\BTUserDeploy（在完成部署后在生产中禁用）  
  
-   Domain\BTUserSupport  
  
-   Domain\SPAdmin  
  
-   域\BizTalk 开发用户（在上游环境中忽略）  
  
-   域\BizTalk 部署用户（在开发环境中忽略）  
  
## <a name="sql-server-administrator-accounts"></a>SQL Server 管理员帐户  
 安装程序接受来自安装人员的输入，并将 SQL 角色分配给用户和组：  
  
-   在 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 安装期间，向 SPAdmin 帐户授予 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 计算机上的安全管理员和数据库创建者权限。 如果 SPAdmin 帐户是本地管理员组的成员，则可以删除这些权限。  
  
## <a name="e-mail-account"></a>电子邮件帐户  
 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 将基于某些系统事件发送电子邮件。 安装程序将在配置过程中提示电子邮件地址。 为此目的创建电子邮件别名，并且在安装和单元测试期间监控此别名。 在生产环境中，此帐户应该可由监控系统的系统管理员访问。  
  
 使用的电子邮件帐户[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]是**WSS 管理员电子邮件**帐户。  
  
## <a name="password-considerations-for-development"></a>有关开发的密码注意事项  
 对于开发和测试环境，可按标准设置帐户密码并且帐户密码可分发。 安装人员的标准各异；本主题采用一个名字单元，它由服务组件的首字母大写缩写加上后随的帐户其余部分（服务或用户）的小写字母缩写组成。 对于服务帐户，本主题使用“Serv”；对于用户帐户，本主题使用“User”。  
  
 例如：  
  
-   Windows SharePoint Services (SharePoint) 服务和管理员帐户 (SPAdmin) 密码: SPServ。  
  
-   BizTalk 服务帐户密码: BTServ。  
  
-   BizTalk 用户帐户密码: BTUser。  
  
 某些 IT 环境要求密码包含非 alpha 和/或数字字符。 在此环境下，您可以将美元符号 ($) 替换为“s”，将“at”符号 (@) 替换为“a”。 这些符号只是示例；开发最适合于您的用于具有半公共密码的共享帐户的模式。  
  
 在开发环境中使用的可重复分发的密码示例是：  
  
-   BT$erv99           BizTalk 服务帐户  
  
-   BTU$er99          BizTalk 用户帐户  
  
-   SP$erv99           WSS 服务帐户 (SPAdmin)  
  
-   SQL$erv99         SQL 服务/访问/管理员帐户  
  
> [!NOTE]
>  这些建议只针对开发和共享环境，不建议或不鼓励用于公司密码策略。 有关密码要求，请向您的网络管理员咨询。  
  
> [!NOTE]
>  如果公司密码策略包括生成的密码，您需要注意的是，某些符号和符号组合是对于 XML 有特殊用途的字符。 不恰当地使用这些字符将导致配置 XML 文件在配置过程中无法打开。 这些符号包括"&"、"\<"，"\>"、 和双-单引号，并且可能包括其他人。 请在执行基于文件的配置前测试配置 XML 文件。 您可以通过在 Internet Explorer（或某一 XML 编辑器）中打开嵌入了生成的密码的文档，测试文件是否可靠地用于适当的 XML 格式。  
  
 有关部署的最多行环境中保证密码安全的详细信息 (包括要测试的方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置文件)，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 权限的疑难解答](../core/troubleshooting-biztalk-server-permissions.md)