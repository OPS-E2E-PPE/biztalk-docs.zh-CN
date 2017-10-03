---
title: "故障排除 BizTalk Server 管理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dfb56b0-352f-4012-b030-087bbcfe09d4
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d89f81bbaf15dfb0c87de91659888d70a2345a6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-biztalk-server-administration"></a>故障排除的 BizTalk Server 管理
本部分提供有关使用 BizTalk Server 管理控制台时遇到的常见问题的信息的一个集中的位置。  
  
 除了以下已知问题，[常见的问题和解决方法与 BizTalk Server 管理控制台](http://social.technet.microsoft.com/wiki/contents/articles/common-issues-and-resolutions-with-the-biztalk-server-administration-console.aspx)提供的其他信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="delay-in-entsso-service-prevents-biztalk-server-service-from-starting"></a>ENTSSO 服务中的延迟可防止 BizTalk Server 服务启动  
  
##### <a name="problem"></a>问题  
 与 DTC 不设置为自动启动重新启动计算机可能会阻止将 BizTalk Server 服务启动。  
  
##### <a name="cause"></a>原因  
 这是因为 ENTSSO 服务可能需要更多时间才能启动超过了允许按 BizTalk Server 服务超时持续时间。  
  
##### <a name="solution"></a>解决方案  
 若要解决此问题，请将 DTC 设置为自动。  
  
#### <a name="sql-resources-may-become-locked"></a>SQL 资源可能会变得锁定  
  
##### <a name="problem"></a>问题  
 可能会出现以下错误：  
  
 **事务（进程 ID 95）与另一进程在锁定资源上发生死锁，并且已被选为死锁牺牲品。请重新运行事务。**  
  
##### <a name="cause"></a>原因  
 这种情况很少见，一名用户执行的管理操作导致另一用户被锁定，而无法进行数据库管理。  
  
##### <a name="solution"></a>解决方案  
 该问题会在短时间内自我进行纠正。 请在几分钟后再次尝试该操作。  
  
#### <a name="sql-database-may-become-locked"></a>SQL 数据库可能会被锁定  
  
##### <a name="problem"></a>问题  
 用户可能被锁在 SQL 数据库之外。 可能会返回一些不同的错误消息。  
  
##### <a name="cause"></a>原因  
 在某些情况下，向数据库进行写入的一名用户会有效地将另一名用户锁在数据库之外。  
  
##### <a name="solution"></a>解决方案  
 该问题会在短时间内自我进行纠正。 请在几分钟后再次尝试该操作。  
  
#### <a name="termination-of-multiple-service-instances-in-a-multiple-messagebox-environment-fails-with-an-error"></a>终止多个 messagebox 环境中的多个服务实例失败并出现错误  
  
##### <a name="problem"></a>问题  
 尝试从 BizTalk Server 管理控制台终止多个服务实例失败，显示一个与以下所示内容类似的错误：  
  
 SQL Server 阻止访问组件“Agent XPs”的“sys.xp_sqlagent_enum_jobs”过程，因为此组件作为此服务器的安全配置的一部分而被关闭。  
  
> [!NOTE]
>  在 messagebox 环境中会出现此问题。  
  
##### <a name="cause"></a>原因  
 此问题可以出现在多个消息框环境中，如果 SQL 代理作业 Operations_OperateOnInstances_OnMaster_\<*dbName*> 不在辅助 messagebox 数据库上运行。 此作业必须正在运行，才能将信息从辅助 messagebox 数据库传播到主 messagebox 数据库。 如果该作业未启用或者如果发生登录故障，则此作业将无法运行。  
  
##### <a name="solution"></a>解决方案  
 如果你使用 BizTalk 管理控制台同时执行多个服务实例上的操作，且你的 BizTalk Server 环境配置的多个 messagebox 数据库，请验证 SQL Server 代理作业名为 Operations_OperateOnInstances_OnMaster_\<*dbName*> 所有辅助 (非 master) messagebox 数据库上启用。 此外，托管辅助 messagebox 数据库的 SQL Server 计算机上的 SQL Server 代理服务必须作为辅助 messagebox 数据库的 BTS_SQLAGENT_USER 数据库角色中包含的帐户运行。  
  
> [!NOTE]
>  \<*dbname*> 是 BizTalk messagebox 数据库的实际名称的占位符。  
  
 请按照以下步骤，将 SQL Server 代理服务帐户添加到辅助 messagebox 数据库的 BTS_SQLAGENT_USER 数据库角色  
  
 **SQL Server 2008 上**  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**。  
  
2.  出现提示时选择**服务器类型**的**数据库引擎**并输入或选择**服务器名称**承载辅助 messagebox 数据库。  
  
3.  单击以展开**数据库**，单击以展开辅助 messagebox 数据库，单击以展开**安全**，单击以展开**角色**，单击以展开**数据库角色**，然后双击 BTS_SQLAGENT_USER 数据库角色。  
  
4.  单击 **“添加”** 按钮。  
  
5.  单击**浏览**，选择 SQL Server 代理服务帐户是的成员的组，然后单击**确定**。  
  
> [!NOTE]
>  如果 SQL Server 代理服务帐户不是指定组的成员，则您需要将其添加到该组。  
  
#### <a name="changes-applied-in-one-instance-of-the-biztalk-administration-console-are-not-automatically-updated-in-other-instances-of-the-biztalk-administration-console"></a>应用 BizTalk 管理控制台的一个实例中的更改不会自动更新 BizTalk 管理控制台的其他实例中  
  
##### <a name="problem"></a>问题  
 如果 BizTalk 管理控制台的多个实例同时连接到相同的 BizTalk Server 组中，BizTalk 管理控制台的一个实例中所做的更改是不会自动反映在 BizTalk 到其他实例管理控制台。 当尝试修改的项目显示在 BizTalk 管理控制台的实例中，如果项目的状态与项目 BizTalk 管理数据库中存储的实际状态不匹配，这可能导致并发冲突错误。  
  
##### <a name="cause"></a>原因  
 在 BizTalk 管理控制台的每个实例维护其自己的 BizTalk 组配置的缓存，并仅反映在缓存中的更改。 刷新 BizTalk 管理控制台视图时，才会更新缓存。  
  
##### <a name="resolution"></a>解决方法  
 如果 BizTalk 管理控制台时出现并发冲突错误，请通过单击更新 BizTalk 管理控制台的实例的缓存**刷新**在 BizTalk 管理控制台上的按钮工具栏或通过按**F5**密钥。  
  
#### <a name="failed-to-execute-action-stop-error-occurs-when-you-attempt-to-stop-an-orchestration-with-the-biztalk-administration-console"></a>尝试通过 BizTalk 管理控制台停止业务流程时，出现无法执行“停止”操作的错误  
  
##### <a name="problem"></a>问题  
 当你尝试停止 BizTalk 管理控制台中的业务流程时，将生成类似于以下错误消息：  
  
```  
Failed to execute action 'Stop'.  
------------------------------  
ADDITIONAL INFORMATION:  
A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.) (Microsoft SQL Server, Error: 10054)  
```  
  
 如果以下条件为真，则可能会出现此问题：  
  
-   在 BizTalk 管理控制台中，打开。  
  
-   SQL Server 的群集实例上安装 BizTalk 管理数据库。  
  
-   SQL Server 的群集的实例故障转移。  
  
-   在故障转移完成后，你尝试停止正在运行的业务流程使用 BizTalk 管理控制台实例。  
  
##### <a name="cause"></a>原因  
 BizTalk 管理控制台维护到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理数据库的连接。 到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理数据库的连接在故障转移期间中断时，某些管理任务会返回“无法连接”或“无法执行”错误，直到 BizTalk 管理控制台关闭或重新打开。  
  
##### <a name="resolution"></a>解决方法  
 关闭并重新打开 BizTalk 管理控制台。 BizTalk 管理控制台重新打开后，将创建一个到指定的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理数据库的新连接。  
  
#### <a name="windows-group-names-that-were-previously-deleted-do-not-have-access-to-the-biztalk-server-databases"></a>以前删除的 Windows 组名不能与 BizTalk Server 数据库的访问  
  
##### <a name="problem"></a>问题  
 如果在重新安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，使用以前删除的 Windows 组名，该 Windows 组将不具有对 BizTalk Server 数据库的访问权。  
  
##### <a name="cause"></a>原因  
 删除 Windows 组，然后创建具有相同名称的 Windows 组生成一个新安全标识符 (SID)，它为 Windows 组。 但是旧 SID 是仍缓存，在 SQL Server，因此新的 Windows 组无法登录到 SQL Server。  
  
##### <a name="resolution"></a>解决方法  
 当你删除此 Windows 组时，则还必须删除的 Windows 组的 SQL Server 登录名。  
  
#### <a name="biztalk-administrator-cannot-start-the-biztalk-server-administration-console"></a>BizTalk 管理员不能启动 BizTalk Server 管理控制台  
  
##### <a name="problem"></a>问题  
 BizTalk 管理员 （BizTalk 管理员 Windows 组的成员） 可能不能打开 BizTalk Server 管理控制台，如果该用户不是本地计算机上的 Windows 管理员组的成员。  
  
##### <a name="cause"></a>原因  
 如果你有重新安装或重新配置 BizTalk Server，可能出现此问题。 这是因为 SQL Server 使用缓存的安全 Id。  
  
##### <a name="resolution"></a>解决方法  
 暂时将 BizTalk 管理员添加到本地计算机上的本地 Windows 管理员组。 在成功打开 BizTalk Server 管理控制台之后, 从本地计算机上的本地 Windows 管理员组中删除 BizTalk 管理员。  
  
#### <a name="cannot-start-a-host-instance-on-a-remote-computer"></a>无法在远程计算机上启动的主机实例  
  
##### <a name="problem"></a>问题  
 当远程计算机上创建了一个 BizTalk 主机实例时，启动 BizTalk 主机实例时，你可能会看到以下错误:"由于而无法启动登录失败。"  
  
##### <a name="cause"></a>原因  
 如果为运行 BizTalk 主机实例时使用的服务帐号输入了无效凭据，或者该服务帐号没有“以服务方式登录”权限，会出现此错误。  
  
##### <a name="resolution"></a>解决方法  
 启动 BizTalk 主机实例之前，为远程计算机中的服务帐户分配“以服务方式登录”权限。 这在本地计算机上，自动完成，但必须在远程计算机上手动完成。  
  
#### <a name="creating-or-configuring-a-host-instance-on-an-x64-computer-with-the-32-bit-only-option-selected-fails"></a>在选择了“仅限 32 位”选项的 X64 计算机上创建或配置主机实例失败  
  
##### <a name="problem"></a>问题  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，在选择了“仅限 32 位”选项（默认选项）的 X64 计算机上创建 BizTalk 主机实例可能会失败。  
  
 在 BizTalk Server 配置管理器中在 X64 计算机上配置 BizTalk Server 运行时时，在选择了“仅限 32 位”选项的情况下创建进程内或独立的主机实例可能导致服务无法启动。  
  
##### <a name="cause"></a>原因  
 Unknown  
  
##### <a name="resolution"></a>解决方法  
 此问题是间歇出现的。 尝试再次创建或配置主机，或者取消选中“仅限 32 位”选项。  
  
#### <a name="host-instance-deletion-does-not-clear-registry-information"></a>删除主机实例并不会清除注册表信息  
  
##### <a name="problem"></a>问题  
 如果你不是管理员在本地计算机上，删除进程内或独立的主机时，会出现访问被拒绝的错误消息。 你可以强制删除该主机。 但是，删除在这种方式中的主机不清除所有相关的注册表信息。  
  
##### <a name="cause"></a>原因  
 删除与一个主机实例相关的注册表信息需要管理员特权。  
  
##### <a name="resolution"></a>解决方法  
 在作为本地管理员帐户之前登录，以便在相关的注册表信息还移除删除主机。  
  
#### <a name="cannot-delete-a-messagebox-database"></a>无法删除 MessageBox 数据库  
  
##### <a name="problem"></a>问题  
 你不能删除 MessageBox 数据库。 如果删除失败，可能是负责以下问题之一：  
  
-   未过期的缓存刷新间隔。  
  
-   MessageBox 数据库包含不完整的实例。  
  
 如果缓存刷新间隔尚未过期，删除失败时显示的以下的错误消息:"由于那里无法将剩余的工作量在消息框中的，无法删除 MessageBox。 请确保在消息框中，没有其他未完成的实例，然后重试。"  
  
##### <a name="cause"></a>原因  
 缓存刷新间隔必须终止禁用 MessageBox 数据库中的新消息发布的时间和删除数据库的时间之间。 默认情况下，缓存刷新间隔是 60 秒。  
  
##### <a name="resolution"></a>解决方法  
 若要删除的 MessageBox 数据库，必须首先禁用该 MessageBox 数据库的新消息发布并缓存刷新间隔过期，然后删除 MessageBox 数据库，然后等待。  
  
 如果 MessageBox 数据库包含不完整的服务实例，出现以下错误消息:"MessageBox 无法删除，因为它仍然可能包含不完整的实例。 确保在消息框中，没有不完整实例，然后重试"。  
  
 您可以使用 BizTalk Server 管理控制台中的“组中心”页查看 MessageBox 数据库中不完整的服务实例。 有关组中心数据库页中查看的服务实例的状态的信息，请参阅[如何搜索跟踪服务实例](../core/how-to-search-for-tracked-service-instances.md)。  
  
## <a name="see-also"></a>另请参阅  
 [故障排除](../core/troubleshooting.md)