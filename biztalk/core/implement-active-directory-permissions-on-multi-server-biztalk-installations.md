---
title: 在多服务器 BizTalk 安装上实现 Active Directory 权限的指南 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 315e25c4-b21d-4b5f-a1d2-1e2777b57f9e
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dad79e7e3003f8ee66aab0838b10f44f8b519258
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332509"
---
# <a name="guidelines-for-implementing-active-directory-permissions-on-multi-server-biztalk-installations"></a>准则用于实现在多服务器 BizTalk 安装在 Active Directory 权限
本主题介绍有关创建 Active Directory 组织单位，其中包含的用户帐户和使用 Microsoft 中的组的准则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。  
  
 此处创建的帐户不需要在域中具有超出普通用户的权限。 域帐户可能需要包括的信任边界内提升的权限：  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] (在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]server)  
  
- Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]  
  
- 外部数据库 1  
  
- 外部数据库 2  
  
- 外部数据库*N*  
  
  例如，域帐户可能需要被授予权限来作为外部数据库宿主的系统上执行某些操作。 在另一种情况下，帐户可能需要将文件写入文件存放文件夹，需要对文件夹的写访问。  
  
  使用**Active Directory 用户和计算机**控制台来创建和管理域用户和组帐户。 单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。  
  
## <a name="biztalk-server-installation-and-configuration-account"></a>BizTalk Server 安装和配置帐户  
 在开发环境中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序并[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置向导要求使用具有管理权限的帐户上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]系统。 可以立即吊销权限或只要安装和配置不完整，将禁用该帐户。 该帐户必须还属于若干 BizTalk 组，在以下各节中介绍。  
  
> [!NOTE]
>  你将不能配置 SSO 组件，如果用于安装的帐户属于与服务器不同的 Active Directory 林中。 如果还没有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序帐户，请使用本地管理员帐户进行 SSO 配置。 在安装期间，例如，需要登录到使用不同的凭据的资源，此方法可能会造成其他问题。  
  
## <a name="biztalk-server-development-accounts"></a>BizTalk Server 开发帐户  
 执行操作的个人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发需要能够访问适配器、 接收和发送处理程序，并接收位置。 这一访问要求域开发人员组的成员**BizTalk Server Administrators**并**SSO Affiliate Administrators**组。  
  
> [!NOTE]
>  Active Directory 具有有关类型的组可以包含外来域用户和组可包含其他组中的类型的限制。 组和帐户下面创建单一域上的多服务器环境中测试。  
  
## <a name="biztalk-server-deployment-accounts"></a>BizTalk Server 部署帐户  
 部署的个人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序将需要是本地系统上的管理员，并且可能需要在环境中的其他权限。 本主题中情况下为此目的而引用了 BizTalk Server 部署帐户。  
  
 这一访问要求域部署组的成员**BizTalk Server Administrators**并**SSO Affiliate Administrators**组。  
  
> [!NOTE]
>  你将不能配置 SSO 组件，如果用于安装的帐户属于与服务器不同的 Active Directory 林中。 如果你没有 BizTalk Server 部署帐户，使用本地管理员帐户进行 SSO 配置。 在安装期间，例如，需要登录到使用不同的凭据的资源，此方法可能会造成其他问题。  
  
## <a name="biztalk-server-support-accounts"></a>BizTalk Server 支持帐户  
 支持的个人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序将需要是本地系统上的管理员。 本主题中情况下为此目的而引用了 BizTalk 支持帐户。  
  
 这一访问要求域支持组的成员**BizTalk Server Administrators**组。  
  
## <a name="sql-server-service-accounts"></a>SQL Server 服务帐户  
 服务正在运行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例必须属于与安装、 开发和部署的帐户相同的 Active Directory 域[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组件。  
  
- 使用**SQLAdmin**执行管理功能 （交互式登录）。  
  
- 使用**SQLService**管理服务 （无交互式登录）。  
  
- 使用**SQLAccess**访问外部数据库。  
  
- SQLAdmin 必须是本地 Administrators 组的成员上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]系统。  
  
- SQLService 必须是本地 Administrators 组的成员上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]系统，需要授予**作为服务登录**用户权限。  
  
- SQLAccess 需要对远程数据库服务器上的相应权限。  
  
  **SQL 帐户：**  
  
|**用户名**|**First Name**|**Last Name**|**全名**|  
|-------------------|--------------------|-------------------|-------------------|  
|SQLService|SQL|SQLService|SQL 服务帐户|  
|SQLAdmin|管理员|SQLService|SQL 管理员帐户|  
|SQLAccess|访问|SQLService|SQL 访问帐户|  
  
 将根据公司标准的帐户密码设置。  
  
> [!IMPORTANT]
>  运行的计算机上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，修改要使用 SQLService 帐户和凭据的 SQL Server 和 SQLServerAgent 服务的启动参数。  
> 
> [!NOTE]
>  用户名字段是示例;您可能需要更改名称，以避免与其他 Active Directory 帐户冲突。  
  
## <a name="windows-sharepoint-services-account"></a>Windows SharePoint Services 帐户  
 在安装之前，必须在创建 Windows SharePoint Services 帐户[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]。  
  
 有关建议和说明[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]帐户：  
  
- SharePoint 管理员帐户 (SPAdmin) 用于管理功能、 SharePoint 定时服务和所有[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]访问。  
  
- SPAdmin 是站点所有者，并且将需要电子邮件别名。  
  
- SPAdmin 必须是本地上的本地管理员组的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机 （Windows SharePoint Services 安装程序执行此）。  
  
- SPAdmin 必须具有安全管理员和数据库创建者角色[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机 （Windows SharePoint Services 安装程序执行此）。  
  
  **Sharepoint 帐户：**  
  
|**用户名**|**First Name**|**Last Name**|**全名**|  
|-------------------|--------------------|-------------------|-------------------|  
|SPAdmin|管理员|SPService|SharePoint 管理员帐户|  
  
 根据公司标准设置帐户密码，并且能够在配置过程中检索这些密码。 请参阅**密码**围绕问题本主题的部分生成的密码。  
  
> [!NOTE]
>  此用户名字段是一个示例;您可能需要更改此名称以保护其他 AD 帐户。  
> 
> [!IMPORTANT]
>  之后运行的计算机上安装 Windows SharePoint Services [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，确认 SharePoint 定时服务的启动参数正在使用 SPAdmin 帐户和凭据。  
  
## <a name="biztalk-groups-and-users"></a>BizTalk 组和用户  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组和用户之前，必须创建运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置向导。 在单系统安装中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用本地组和配置期间创建的帐户。 但是，如果将单独[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署主机或如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]安装两台不同计算机上必须使用域用户和组帐户。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置向导无法创建域帐户。  
  
 有关建议和说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务和用户帐户：  
  
- 有关创建组织单位 (OU) [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 所有帐户和组将都属于此 OU。  
  
- 有描述性完整名称;以下列表中的名称应启用要在配置过程中选择适当的组/帐户/用户的安装程序。  
  
- 名字和姓氏是可选的;包含仅的一致性。  
  
- 不同之处**符 BTService**并**BTUser**指的是服务帐户 （自动） 和一般/共享人类用户。  
  
- 创建域帐户，并通过 ADSI 脚本为用户和组帐户创建为上游环境对它们进行填充。  
  
  **BizTalk 服务帐户**  
  
|**用户名**|**First Name**|**Last Name**|**全名**|  
|-------------------|--------------------|-------------------|-------------------|  
|BTService|BTS|BTService|BizTalk 服务帐户|  
|BTServiceHost|主机|BTService|BizTalk 主机实例帐户|  
|BTServiceHostIso|HostIso|BTService|BizTalk 独立主机实例帐户|  
|SSOService|SSO|BTService|企业单一登录服务|  
|BTServiceREU|REU|BTService|规则引擎更新服务|  
  
 设置用户名称，根据公司和环境标准 （例如 devBTService、 alphaBTService）。 根据公司标准设置帐户密码，并能够检索它们的配置步骤。 请参阅**开发的密码注意事项**围绕问题本主题的部分生成的密码。  
  
 安装程序会注意到的服务帐户是非常精细，接近一对一的映射到创建的服务都有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这一粒度允许公司 IT 安全人员跟踪或根据需要限制访问。 建议使用粒度，但若要确定是否需要在企业环境中的系统设计人员和企业安全人员之前。  
  
 上一组中的服务帐户旨在仅，用于自动访问不适用于用户交互式登录。  
  
#### <a name="to-set-the-appropriate-account-options"></a>若要设置适当的帐户选项  
  
1. 在中**Active Directory 用户和计算机**控制台，单击以展开域，然后单击以展开**用户**容器。  
  
2. 右键单击该帐户，然后选择**属性**以显示**属性**帐户对话框。  
  
3. 单击**帐户**选项卡**属性**对话框。  
  
4. 单击此项可检查以下选项：  
  
   -   **用户不能更改密码**(企业安全人员将成批更改密码)。  
  
   -   **密码永不过期**  
  
5. 单击**登录到**按钮以显示**登录工作站**对话框。  
  
6. 单击此选项以**以下计算机**，添加每台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，然后单击**确定**。  
  
7. 单击**遥控器**选项卡**属性**对话框的，然后单击以清除选项**启用远程控制**。  
  
8. 单击**终端服务配置文件**选项卡**属性**对话框。  
  
9. 单击以选中选项**拒绝此用户的权限登录到任何终端服务器上**。  
  
10. 单击**确定**以关闭**属性**帐户对话框。  
  
11. 每个服务帐户重复步骤 3 至 10。  
  
    **BizTalk 用户帐户**  
  
|**用户名**|**First Name**|**Last Name**|**全名**|  
|-------------------|--------------------|-------------------|-------------------|  
|BTUserAdmin|管理员|BTUser|BizTalk 管理用户帐户|  
|BTUserDeploy|部署|BTUser|BizTalk 部署用户帐户|  
|BTUserHostInstance|HostInstance|BTUser|BizTalk 主机实例帐户|  
|BTUserHostIsolated|IsolatedlHost|BTUser|BizTalk 独立主机实例帐户|  
|BTUserInstall|安装|BTUser|BizTalk 安装用户帐户|  
|BTUserSupport|支持|BTUser|BizTalk 支持访问帐户|  
  
#### <a name="to-set-the-appropriate-account-options-follow-these-steps"></a>若要设置适当的帐户选项，请执行以下步骤  
  
1. 在中**Active Directory 用户和计算机**控制台中，单击以展开域，然后单击以展开**用户**容器。  
  
2. 右键单击该帐户，然后选择**属性**以显示**属性**帐户对话框。  
  
3. 单击**帐户**选项卡**属性**对话框。  
  
4. 单击此项可检查以下选项：  
  
   -   **用户不能更改密码**(企业安全人员将成批更改密码)。  
  
   -   **密码永不过期**  
  
5. 单击**登录到**按钮以显示**登录工作站**对话框。  
  
6. 单击此选项以**以下计算机**，添加每台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，然后单击**确定**。  
  
7. 单击**遥控器**选项卡**属性**对话框中，然后单击以选中选项**启用远程控制**。  
  
8. 单击**终端服务配置文件**选项卡**属性**对话框。  
  
9. 单击以清除选项**拒绝此用户的权限登录到任何终端服务器上**。  
  
10. 单击**确定**以关闭**属性**帐户对话框。  
  
11. 每个用户帐户重复步骤 3 至 10。  
  
    > [!NOTE]
    >  它们提供的角色分配给实际用户时，可禁用任何这些帐户。 在版本 1 和版本 2 的早期阶段，假定这些帐户可在开发、 测试和 beta 版测试环境。  
  
    **BizTalk 组帐户**  
  
|**组名称**|**组类型**|**成员**|  
|--------------------|--------------------|-----------------|  
|BizTalk Application Users|全局或通用|-   BTServiceHost<br />-BTUserHostInstance|  
|BizTalk 开发用户|全局或通用|（开发用户的本地域帐户）**注意：** 最佳做法是，不要启用上游环境中的 BizTalk 开发用户组。|  
|BizTalk 部署用户|全局或通用|（部署用户的本地域帐户）|  
|BizTalk 主机用户|全局或通用|BTUserHostInstance|  
|BizTalk Isolated Host Users|全局或通用|-   BTServiceHostIso<br />-BTUserHostInstance|  
|BizTalk Server Administrators|全局或通用|-BTUserAdmin<br />-BTUserInstall<br />BizTalk 开发用户<br />BizTalk 部署用户|  
|BizTalk 支持用户|全局或通用|BTUserSupport （支持用户的本地域帐户）|  
|SSO Administrators|全局或通用|-   SSOService<br />-BTUserInstall<br />本地管理员|  
|SSO 关联管理员|全局或通用|BizTalk 开发用户<br />BizTalk 部署用户<br />-   BTServiceHostIso<br />-   \<控制台用户\>|  
|Windows SharePoint Services 管理员|全局或通用|-   SPAdmin<br />-BTUserInstall<br />-   BTUserDeploy<br />BizTalk 开发用户<br />BizTalk 部署用户|  
  
 建议和域组的说明：  
  
- 创建组并添加成员在安装之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- 域组可以是全局或通用组。  
  
- 使用 *\<DomainName\>\\< 用户名\>* 时配置向导中指定的域帐户信息。  
  
- 组和用户/服务帐户必须与在其中的域属于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机所属 （配置向导检查此并且不会显示帐户或组包含来自其他域帐户）。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 对于所有聚类分析方案要求使用域帐户。  
  
- 安装时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，控制台用户必须是以下组的成员：  
  
  - BizTalk Server Administrators  
  
  - SSO Administrators （仅当配置主密钥服务器）  
  
  - Windows 管理员  
  
  - [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 管理员  
  
  - OLAP 管理员  
  
    BTUserInstall 帐户应该用于安装和配置和完成配置后应禁用。  
  
- 若要允许消息事件和服务实例跟踪将业务流程附加到调试器，开发人员需要属于 BizTalk Server Administrators 组中，如上面的部分中所述**BizTalk 开发帐户**.  
  
## <a name="local-administrator-accounts"></a>本地管理员帐户  
 确认或到本地管理员组中添加以下帐户和组，在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机：  
  
- Domain\BTUserInstall （配置完成后禁用）  
  
- Domain\BTUserDeploy （在生产部署完成后禁用）  
  
- Domain\SPAdmin  
  
- Domain\SQLAdmin  
  
- Domain\SQLService  
  
- 域 \biztalk 开发用户 （在上游环境）  
  
- 域 \biztalk 部署用户 （在开发环境中省略）  
  
  确认或到本地管理员组中添加以下帐户和组，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机：  
  
- Domain\BTUserInstall （配置完成后禁用）  
  
- Domain\BTUserDeploy （在生产部署完成后禁用）  
  
- Domain\BTUserSupport  
  
- Domain\SPAdmin  
  
- 域 \biztalk 开发用户 （在上游环境中）  
  
- 域 \biztalk 部署用户 （在开发环境中省略）  
  
## <a name="sql-server-administrator-accounts"></a>SQL Server 管理员帐户  
 安装程序接受用户和组从安装程序，并将分配 SQL 角色的输入：  
  
- 期间[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]安装程序，SPAdmin 帐户安全管理员和数据库创建者权限授予在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。 如果 SPAdmin 帐户是本地管理员组的成员可以删除这些权限。  
  
## <a name="e-mail-account"></a>电子邮件帐户  
 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 将基于发送电子邮件某些系统事件。 安装程序将在配置过程中提示电子邮件地址。 实现此目的创建电子邮件别名，并且在安装和单元测试期间监控此别名。 在生产环境中，此帐户应是可由监控系统的系统管理员访问。  
  
 使用的电子邮件帐户[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]是**WSS 管理员电子邮件**帐户。  
  
## <a name="password-considerations-for-development"></a>有关开发的密码注意事项  
 对于开发和测试环境中，帐户密码可以按标准设置，并可分发。 安装程序的标准各异;本主题使用首字母大写，缩写加上 （服务或用户） 的帐户其余小写缩写词后跟的服务组件的模板。 对于服务帐户，本主题使用 Serv; 本主题使用用户的用户帐户。  
  
 例如：  
  
- Windows SharePoint Services (SharePoint) 服务和管理员帐户 (SPAdmin) 密码：SPServ。  
  
- BizTalk 服务帐户密码：BTServ。  
  
- BizTalk 用户帐户密码：BTUser。  
  
  某些 IT 环境要求密码包含非 alpha 和/或数字字符。 在此方案中，你可以替换美元符号 （$） 的"s"，并将 at 符号 (@) 为"a"。 符号是示例;开发一种模式，最适合您的共享具有半公共密码的帐户。  
  
  在开发环境中使用的示例可再发行组件密码是：  
  
- BT$erv99           BizTalk Service Accounts  
  
- BTU$er99          BizTalk User Accounts  
  
- SP 美元 erv99 WSS 服务帐户 (SPAdmin)  
  
- SQL$erv99         SQL Service/Access/Admin Account  
  
> [!NOTE]
>  这些建议适用于开发和仅限共享的环境并不会建议或不鼓励用于公司密码策略。 请参阅有关密码要求网络管理员联系。  
  
> [!NOTE]
>  如果公司密码策略包括生成的密码，需要注意某些符号和符号组合是特殊用途的 XML 字符。 不恰当地使用这些字符将导致配置 XML 文件，在配置过程中无法打开。 这些符号包括"&"、"\<"，"\>"、 和双单引号，并且可能包括其他人。 测试之前执行基于文件的配置的配置 XML 文件。 你可以测试此可靠地保证正确的 XML 格式，通过在 Internet Explorer （或 XML 编辑器） 中打开该文档与其中嵌入了生成的密码。  
  
 有关部署上游环境中保证密码安全的详细信息 (包括要测试的方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置文件)，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。  
  
## <a name="see-also"></a>请参阅  
 [故障排除的 BizTalk Server 权限](../core/troubleshooting-biztalk-server-permissions.md)