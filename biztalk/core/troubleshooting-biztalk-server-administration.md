---
title: BizTalk Server 管理疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 11/30/2018
ms.prod: biztalk-server
ms.reviewer: niklase
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dfb56b0-352f-4012-b030-087bbcfe09d4
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87ecae986df0ee34ee697257a99097a00d525db2
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826461"
---
# <a name="troubleshooting-biztalk-server-administration"></a>故障排除的 BizTalk Server 管理
本部分提供有关使用 BizTalk Server 管理控制台时遇到的常见问题的信息的一个集中的位置。  
  
 除了以下已知问题[常见问题和解决方法与 BizTalk Server 管理控制台](http://social.technet.microsoft.com/wiki/contents/articles/common-issues-and-resolutions-with-the-biztalk-server-administration-console.aspx)提供的其他信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="delay-in-entsso-service-prevents-biztalk-server-service-from-starting"></a>ENTSSO 服务中的延迟会阻止 BizTalk Server 服务启动  
  
##### <a name="problem"></a>问题  
 使用 DTC 未设置为自动启动时重新启动您的计算机可能会阻止 BizTalk Server 服务启动。  
  
##### <a name="cause"></a>原因  
 这是因为 ENTSSO 服务可能需要更多时间来启动超过了允许按 BizTalk Server 服务超时持续时间。  
  
##### <a name="solution"></a>解决方案  
 若要解决此问题，请将 DTC 设置为自动。 如果群集化 DTC 之后，它应设置为手动启动时这是因为群集服务管理的开始和停止群集服务。 
  
#### <a name="sql-resources-may-become-locked"></a>SQL 资源可能会被锁定  
  
##### <a name="problem"></a>问题  
 可能会出现以下错误：  
  
 **事务（进程 ID 95）与另一进程在锁定资源上发生死锁，并且已被选为死锁牺牲品。重新运行事务。**  
  
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
 此问题可能在多个 messagebox 环境中，如果 SQL 代理作业 Operations_OperateOnInstances_OnMaster_\<*dbName*\>辅助 messagebox 数据库上未运行。 此作业必须正在运行，才能将信息从辅助 messagebox 数据库传播到主 messagebox 数据库。 如果该作业未启用或者如果发生登录故障，则此作业将无法运行。  
  
##### <a name="solution"></a>解决方案  
 如果使用 BizTalk 管理控制台中同时执行多个服务实例上的操作和 BizTalk Server 环境配置了多个 messagebox 数据库，请验证 SQL Server 代理作业名为 Operations_OperateOnInstances_OnMaster_\<*dbName*\>在所有辅助 （非主） messagebox 数据库上启用。 此外，托管辅助 messagebox 数据库的 SQL Server 计算机上的 SQL Server 代理服务必须作为辅助 messagebox 数据库的 BTS_SQLAGENT_USER 数据库角色中包含的帐户运行。  
  
> [!NOTE]
>  \<*dbname* \>是 BizTalk messagebox 数据库的实际名称的占位符。  
  
 请按照以下步骤，将 SQL Server 代理服务帐户添加到辅助 messagebox 数据库的 BTS_SQLAGENT_USER 数据库角色  
  
 **SQL Server 2008 上**  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**。  
  
2.  出现提示时选择**服务器类型**的**数据库引擎**并输入或选择**服务器名称**托管辅助 messagebox 数据库。  
  
3.  单击此项可展开**数据库**，单击以展开辅助 messagebox 数据库，单击以展开**安全**，单击此项可展开**角色**，单击此项可展开**数据库角色**，然后双击 BTS_SQLAGENT_USER 数据库角色。  
  
4.  单击 **“添加”** 按钮。  
  
5.  单击**浏览**，选择 SQL Server 代理服务帐户是的成员的组，然后单击**确定**。  
  
> [!NOTE]
>  如果 SQL Server 代理服务帐户不是指定组的成员，则您需要将其添加到该组。  
  
#### <a name="changes-applied-in-one-instance-of-the-biztalk-administration-console-are-not-automatically-updated-in-other-instances-of-the-biztalk-administration-console"></a>BizTalk 管理控制台中的一个实例中应用的更改不会自动更新在其他情况下的 BizTalk 管理控制台  
  
##### <a name="problem"></a>问题  
 如果 BizTalk 管理控制台中的多个实例同时连接到相同的 BizTalk Server 组中，BizTalk 管理控制台中的一个实例中所做的更改将不会自动反映在另一个实例的 BizTalk管理控制台。 尝试修改项目显示在 BizTalk 管理控制台中的一个实例，如果项目的状态与项目存储在 BizTalk 管理数据库中的实际状态不匹配时，这会导致并发冲突错误。  
  
##### <a name="cause"></a>原因  
 在 BizTalk 管理控制台的每个实例维护其自己的 BizTalk 组配置的缓存，并仅反映在缓存中的更改。 刷新 BizTalk 管理控制台视图时，才会更新缓存。  
  
##### <a name="resolution"></a>解决方法  
 如果在 BizTalk 管理控制台中收到并发冲突错误，通过单击更新 BizTalk 管理控制台中的实例的缓存**刷新**在 BizTalk 管理控制台上的按钮工具栏或通过按**F5**密钥。  
  
#### <a name="failed-to-execute-action-stop-error-occurs-when-you-attempt-to-stop-an-orchestration-with-the-biztalk-administration-console"></a>尝试通过 BizTalk 管理控制台停止业务流程时，出现无法执行“停止”操作的错误  
  
##### <a name="problem"></a>问题  
 当你尝试停止业务流程的 BizTalk 管理控制台中时，生成类似以下的错误消息：  
  
```  
Failed to execute action 'Stop'.  
------------------------------  
ADDITIONAL INFORMATION:  
A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.) (Microsoft SQL Server, Error: 10054)  
```  
  
 如果满足以下条件，则可能会出现此问题：  
  
-   在 BizTalk 管理控制台已打开。  
  
-   SQL Server 的群集实例上安装了 BizTalk 管理数据库。  
  
-   SQL Server 的群集的实例故障转移。  
  
-   在故障转移完成后，你尝试停止正在运行的业务流程使用 BizTalk 管理控制台实例。  
  
##### <a name="cause"></a>原因  
 BizTalk 管理控制台维护到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理数据库的连接。 到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理数据库的连接在故障转移期间中断时，某些管理任务会返回“无法连接”或“无法执行”错误，直到 BizTalk 管理控制台关闭或重新打开。  
  
##### <a name="resolution"></a>解决方法  
 关闭并重新打开 BizTalk 管理控制台。 BizTalk 管理控制台重新打开后，将创建一个到指定的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理数据库的新连接。  
  
#### <a name="windows-group-names-that-were-previously-deleted-do-not-have-access-to-the-biztalk-server-databases"></a>以前删除的 Windows 组名称不能访问到 BizTalk Server 数据库  
  
##### <a name="problem"></a>问题  
 如果在重新安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，使用以前删除的 Windows 组名，该 Windows 组将不具有对 BizTalk Server 数据库的访问权。  
  
##### <a name="cause"></a>原因  
 删除 Windows 组并具有相同名称创建一个 Windows 组生成的 Windows 组一个新安全标识符 (SID)。 但是的旧 SID 是仍缓存在 SQL Server 中，因此新的 Windows 组不能登录到 SQL Server。  
  
##### <a name="resolution"></a>解决方法  
 删除 Windows 组时，还必须删除的 Windows 组的 SQL Server 登录名。  
  
#### <a name="biztalk-administrator-cannot-start-the-biztalk-server-administration-console"></a>BizTalk 管理员不能启动 BizTalk Server 管理控制台  
  
##### <a name="problem"></a>问题  
 BizTalk 管理员 （BizTalk 管理员 Windows 组的成员） 可能不能打开 BizTalk Server 管理控制台中，如果该用户不是本地计算机上 Windows Administrators 组的成员。  
  
##### <a name="cause"></a>原因  
 如果重新安装或重新配置 BizTalk Server，则可以会出现此问题。 这是因为 SQL Server 使用缓存的安全 Id。  
  
##### <a name="resolution"></a>解决方法  
 暂时将 BizTalk 管理员添加到本地计算机上的本地 Windows 管理员组。 已成功打开后在 BizTalk Server 管理控制台，从本地计算机上的本地 Windows 管理员组中删除 BizTalk 管理员。  
  
#### <a name="cannot-start-a-host-instance-on-a-remote-computer"></a>无法在远程计算机上启动主机实例  
  
##### <a name="problem"></a>问题  
 当在远程计算机上创建 BizTalk 主机实例时，在启动 BizTalk 主机实例时，可能会看到以下错误:"由于启动失败登录失败。"  
  
##### <a name="cause"></a>原因  
 如果为运行 BizTalk 主机实例时使用的服务帐号输入了无效凭据，或者该服务帐号没有“以服务方式登录”权限，会出现此错误。  
  
##### <a name="resolution"></a>解决方法  
 启动 BizTalk 主机实例之前，为远程计算机中的服务帐户分配“以服务方式登录”权限。 这在本地计算机上自动完成，但必须在远程计算机上手动完成。  
  
#### <a name="creating-or-configuring-a-host-instance-on-an-x64-computer-with-the-32-bit-only-option-selected-fails"></a>在选择了“仅限 32 位”选项的 X64 计算机上创建或配置主机实例失败  
  
##### <a name="problem"></a>问题  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，在选择了“仅限 32 位”选项（默认选项）的 X64 计算机上创建 BizTalk 主机实例可能会失败。  
  
 在 BizTalk Server 配置管理器中在 X64 计算机上配置 BizTalk Server 运行时时，在选择了“仅限 32 位”选项的情况下创建进程内或独立的主机实例可能导致服务无法启动。  
  
##### <a name="cause"></a>原因  
 Unknown  
  
##### <a name="resolution"></a>解决方法  
 此问题是间歇性的。 尝试再次创建或配置主机，或者取消选中“仅限 32 位”选项。  
  
#### <a name="host-instance-deletion-does-not-clear-registry-information"></a>删除主机实例将不会清除注册表信息  
  
##### <a name="problem"></a>问题  
 如果你不是管理员在本地计算机上的删除进程内或独立的主机时，会出现访问被拒绝的错误消息。 您可以强制删除该主机。 但是，删除以这种方式主机不会清除所有相关的注册表信息。  
  
##### <a name="cause"></a>原因  
 删除的主机实例相关的注册表信息需要管理员权限。  
  
##### <a name="resolution"></a>解决方法  
 登录以本地管理员帐户，以便相关的注册表信息也会删除在删除主机之前。  
  
#### <a name="cannot-delete-a-messagebox-database"></a>无法删除 MessageBox 数据库  
  
##### <a name="problem"></a>问题  
 您不能删除 MessageBox 数据库。 如果删除操作失败，可能是负责以下问题之一：  
  
- 缓存刷新间隔尚未过期。  
  
- MessageBox 数据库包含未完成的实例。  
  
  删除失败时缓存刷新间隔尚未过期，如果出现以下错误消息:"由于那里无法剩余工作到 MessageBox 中的，无法删除 MessageBox。 请确保在 MessageBox 中没有其他未完成的实例，然后重试。"  
  
##### <a name="cause"></a>原因  
 缓存刷新间隔必须过期禁用 MessageBox 数据库中的发布新消息的时间和删除数据库的时间之间。 默认情况下，缓存刷新间隔为 60 秒。  
  
##### <a name="resolution"></a>解决方法  
 若要删除的 MessageBox 数据库，必须首先禁用该 MessageBox 数据库，发布新消息和缓存刷新间隔过期，然后再删除 MessageBox 数据库，然后等待。  
  
 如果 MessageBox 数据库包含不完整的服务实例，出现以下错误消息:"由于它可能仍然包含未完成的实例，无法删除 MessageBox。 确保在 MessageBox 中没有未完成的实例，然后重试"。  
  
 您可以使用 BizTalk Server 管理控制台中的“组中心”页查看 MessageBox 数据库中不完整的服务实例。 在组中心页中查看服务实例的状态的信息，请参阅[如何搜索跟踪的服务实例](../core/how-to-search-for-tracked-service-instances.md)。  
  
## <a name="see-also"></a>请参阅  
 [故障排除](../core/troubleshooting.md)
