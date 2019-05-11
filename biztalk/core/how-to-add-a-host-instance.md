---
title: 将主机实例添加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98ba10a6-c5e7-4dec-98f1-4e6ba44c2851
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 072aa728eddf99c62fe83ed19e3fef82ba3f612a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387420"
---
# <a name="add-a-host-instance"></a>添加主机实例

## <a name="overview"></a>概述
可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 Windows Management Instrumentation (WMI) 来添加主机实例。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]您可以仅将主机实例添加到一台服务器一次。 有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。 有关使用 WMI 添加主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 添加主机实例映射到 BizTalk Server 的实例在给定主机的实例。 如果您有必须修复现有主机实例，可以更新主机实例属性。 必须先停止现有的主机实例，才能再次添加。 有关停止主机实例的信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。  
  
> [!NOTE]
>  如果你想要创建更多 26 主机实例，必须按照知识库文章 184802，"User32.dll 或 Kernel32.dll 无法初始化，"可在中的说明[ http://go.microsoft.com/fwlink/?LinkId=26176 ](http://go.microsoft.com/fwlink/?LinkId=26176)。 如果应用此知识库文章中的建议后，您需要其他主机实例，可以尝试减少可为每个 BTSNTSvc 服务实例的内存量。 这将提供额外的内存来创建更多实例。  
  
> [!NOTE]
>  服务帐户将自动被授予日志上作为服务安装主机实例的服务器上的权限。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 Administrators 组和 BizTalk Server Administrators 组的成员的身份登录。  
  
 此外，您还必须是 db_securityadmin SQL Server 数据库角色和以下数据库所在的服务器上的 securityadmin SQL Server 角色的成员：  
  
-   BAM 主导入 (BAMPrimaryImport)  
  
-   BizTalk 管理 (BizTalkMgmtDb)  
  
-   BizTalk MessageBox (BizTalkMsgBoxDb) （全部）  
  
-   BizTalk 跟踪 (BizTalk DTADb)  
  
-   规则引擎 (BizTalkRuleEngineDb)  
  
> [!CAUTION]
>  我们建议使用 BizTalk Server 管理控制台或 Windows Management Instrumentation (WMI) 脚本更新主机实例的帐户信息。 这可确保 BizTalk Server 可以更新 BizTalk Server 数据库中的帐户信息并保持数据库和同步的主机实例之间的安全配置。  
  
## <a name="steps"></a>步骤
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、 BizTalk 组，然后依次**平台设置**。  
  
3. 右键单击**主机实例**，单击**新建**，然后单击**主机实例**。  
  
4. 在中**主机实例属性**对话框中，执行以下操作，然后依次**确定**:  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**主机名**|显示与所选服务器关联的主机的名称。|  
   |**Server**|显示与所选主机关联的服务器。|  
   |**登录**|显示新的主机实例将运行的服务帐户的帐户名。|  
   |**配置**|单击此项可显示**登录凭据**对话框框中，您可以在其中输入帐户名称和主机实例将运行的帐户的密码。|  
   |**禁止主机实例启动**|选择此复选框可从所选主机的状态更改为已禁用已启用。 如果您不希望主机实例，若要开始，但要保留其设置，禁用主机实例非常有用。|  
  
   安装主机实例后，您必须启动它，以便它可以将消息路由到 MessageBox 数据库。 有关启动主机实例的信息，请参阅[如何启动主机实例](../core/how-to-start-a-host-instance.md)。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="a-biztalk-host-instance-is-created-with-a-status-of-uninstall-failed-if-the-designated-biztalk-server-runtime-computer-is-not-available-during-host-instance-creation"></a>如果主机实例创建期间指定的 BizTalk Server 运行时计算机不可用，创建一个 BizTalk 主机实例的状态为"卸载失败"  
  
##### <a name="problem"></a>问题  
 如果在对远程计算机上安装 BizTalk 管理控制台[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机，则可以尝试在远程数据库上创建主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机即使[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机不可用。  
  
 如果你尝试创建 BizTalk 主机的实例上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机不可用，并显示以下错误消息对话框中显示：  
  
 主机实例的安装\<*主机名*\>服务器上\<*服务器名称*\>失败。  
  
 其他信息：  
  
 RPC 服务器不可用。 (WinMgmt)  
  
 当您单击确定以关闭该对话框时，显示一个对话框，并显示以下错误消息：  
  
 清理已中止的主机安装\<*主机名*\>服务器上\<*服务器名称*\>失败。  
  
 其他信息：  
  
 故障发生时正在删除 Windows NT 服务 BTSSvc {*\<GUID\>*}。 (WinMgmt)  
  
 当您单击**确定**以关闭此对话框中，会显示在 BizTalk 管理控制台中使用的 BizTalk 主机实例**状态**的**卸载失败**.  
  
##### <a name="cause"></a>原因  
 安装主机实例之前创建的主机实例时，BizTalk 管理数据库中生成一个条目拖到指定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。 如果安装主机实例上指定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的计算机发生故障，BizTalk 管理程序将尝试卸载主机实例，但由于指定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机不可作为卸载失败嗯。  
  
##### <a name="resolution"></a>解决方法  
 如果在状态为在 BizTalk 管理控制台中创建的 BizTalk 主机实例**卸载失败**、 删除主机实例和指定的 BizTalk Server 计算机变为可用后重新创建主机实例。  
  
> [!NOTE]
>  如果 BizTalk 管理控制台中创建 BizTalk 主机实例时**状态**的**卸载失败**主机实例之后将不可功能甚至指定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机再次变为可用。  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [启动主机实例](../core/how-to-start-a-host-instance.md)   
 [停止主机实例](../core/how-to-stop-a-host-instance.md)   
 [删除主机实例](../core/how-to-delete-a-host-instance.md)   
 [修改主机实例属性](../core/how-to-modify-host-instance-properties.md)