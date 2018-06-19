---
title: 与 MSDTC 问题疑难解答 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f39cde52-da8f-4cc1-bdc5-e4b828891a79
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c244ec27cd3e584f7fb22a34effeaf0033c3e78a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280501"
---
# <a name="troubleshooting-problems-with-msdtc"></a>MSDTC 疑难解答
大多数 BizTalk Server 运行时操作都需要 Microsoft 分布式事务处理协调器 (MSDTC) 支持，以确保操作事务性一致。 如果没有 MSDTC 事务支持，则相关联的 BizTalk Server 运行时操作将无法进行。 未正确配置 MSDTC 事务支持时通常会影响的 BizTalk 组件包括（但不限于）单一登录服务、BizTalk 主机实例以及 BizTalk Server 所连接的任何 SQL Server 实例。 本部分包含的信息描述了与 MSDTC 相关的错误和步骤，遵循这些步骤可帮助你诊断并解决 MSDTC 存在的问题。  
  
## <a name="errors-that-can-occur-if-msdtc-transaction-support-is-not-configured-correctly"></a>未正确配置 MSDTC 事务支持时会出现的错误  
 如果未在 BizTalk 环境中的计算机上正确配置 MSDTC 事务支持，则 BizTalk Server 上可能出现如下错误：  
  
-   “由于 Microsoft 分布式事务处理协调器出现问题，因此无法连接到配置数据库。 该事务管理器已经禁止了它对远程/网络事务的支持"。  
  
-   “由于 Microsoft 分布式事务处理协调器出现问题，因此无法连接到配置数据库。 此事务已明地或暗地被确认或终止”。  
  
-   “错误代码：0x8004d00a，无法在指定的事务处理协调器中登记新事务”。  
  
-   “无法从配置存储中检索接收位置‘MySample ReceiveLocation’的传输类型数据。 主 SSO Server‘MyServer’发生故障。 RPC 服务器不可用”。  
  
-   “错误代码：0x8004d025,，合作伙伴事务管理器已禁用对远程/网络事务的支持”。  
  
-   “错误代码：0xc0002a24，无法导入 DTC 事务。 请检查 MSDTC 是否正确配置以用于远程操作”。  
  
-   “0x8004d01c  
  
     [0x1705] 创建内部工作项时发生失败。  
  
     确保 SQL Server 正在运行。”  
  
 要解决 MSDTC 配置错误，请遵循以下步骤。  
  
## <a name="ensure-netbios-name-resolution-between-the-biztalk-server-and-remote-servers-is-successful"></a>确保 BizTalk Server 与远程服务器之间的 NetBIOS 名称解析成功  
 要在计算机之间成功完成 MSDTC 事务，客户端计算机和服务器计算机都必须能够将对方的 NetBIOS 名称解析为正确的 IP 地址。 要检查 NetBIOS 名称解析是否在两个方向上（客户端到服务器和服务器到客户端）都工作正常，请按以下步骤进行操作：  
  
> [!NOTE]
>  NetBIOS 名称还常称为 **网络** 名称。  
  
1.  确定每台计算机的 NetBIOS 名称：  
  
    1.  右键单击“我的电脑”  以显示“系统属性”  对话框，然后单击“计算机名”  选项卡，查看分配给该计算机的“计算机全名”  。  
  
    2.  NetBIOS 名称是指定为 **完整计算机名称** 的名称的第一部分，例如，如果 **完整计算机名称** 为 myserver.company.domain.com，则计算机的 NetBIOS 名称为 **myserver**。  
  
2.  确定与每台计算机相关联的 IP 地址：  
  
    1.  在客户端计算机上启动命令提示符，键入以下命令，然后按 Enter：  
  
        ```  
        ipconfig /all  
        ```  
  
    2.  命令提示符窗口中即会列出与客户端计算机相关联的 IP 地址。  
  
    3.  在服务器计算机上启动命令提示符，键入以下命令，然后按 Enter：  
  
        ```  
        ipconfig /all  
        ```  
  
    4.  命令提示符窗口中即会列出与服务器计算机相关联的 IP 地址。  
  
3.  检查每台计算机的 NetBIOS 名称是否解析为与该计算机相关联的 IP 地址之一：  
  
    1.  在客户端计算机上启动命令提示符，键入以下命令，然后按 Enter：  
  
        ```  
        ping <NetBIOS name of server computer>  
        ```  
  
         ping 命令的结果应该返回与服务器计算机相关联的 IP 地址。  
  
    2.  在服务器计算机上启动命令提示符，键入以下命令，然后按 Enter：  
  
        ```  
        ping <NetBIOS name of client computer>  
        ```  
  
         ping 命令的结果应该返回与客户端计算机相关联的 IP 地址。  
  
4.  验证每台计算机上与 NetBIOS 名称相关联的 IP 地址反向名称查找解析为正确的计算机名。  
  
    1.  在客户端计算机上启动命令提示符，键入以下命令，然后按 Enter：  
  
        ```  
        ping -a <IP Address associated with client computer NetBIOS name>  
        ```  
  
         ping 命令的结果应该返回一个 NetBIOS 名称或与步骤 3a 中使用的 NetBIOS 名称相对应的完全限定域名。 如果返回的名称不与步骤 3a 中使用的 NetBIOS 名称相匹配或对应，则 IP 地址反向查找将失败，这会导致 MSDTC 事务失败。  
  
    2.  在服务器计算机上启动命令提示符，键入以下命令，然后按 Enter：  
  
        ```  
        ping -a <IP Address associated with server computer NetBIOS name>  
        ```  
  
         ping 命令的结果应该返回一个 NetBIOS 名称或与步骤 3b 中使用的 NetBIOS 名称相对应的完全限定域名。 如果返回的名称不与步骤 3b 中使用的 NetBIOS 名称相匹配或对应，则 IP 地址反向查找将失败，这会导致 MSDTC 事务失败。  
  
 如果 NetBIOS 名称解析在任何一个方向上不成功，或者反向名称查找失败，请在 DNS 服务器、NetBIOS 名称服务器、HOSTS 文件或 LMHOSTS 文件中添加适当的条目以纠正问题。  
  
> [!NOTE]
>  计算机使用的名称解析方法随计算机的 NetBIOS 节点类型不同而异。 有关 NetBIOS 节点类型的详细信息，请参阅 [NetBIOS 名称解析](http://go.microsoft.com/fwlink/?LinkId=201638)。  
  
## <a name="ensure-that-a-firewall-between-the-biztalk-server-and-remote-servers-is-not-blocking-ports-required-for-rpc-dynamic-port-allocation"></a>确保 BizTalk Server 与远程服务器之间的防火墙没有阻塞 RPC 动态端口分配所需要的端口  
 通过网络实现的 MSDTC 功能取决于通过网络实现的 RPC 功能。 通过防火墙使用 RPC 功能需要打开特定的端口，以满足 RPC 动态端口的分配要求。 如果在 BizTalk Server 与远程服务器之间有防火墙，则请按照 [如何配置与防火墙一起使用的 RPC 动态端口分配](http://go.microsoft.com/fwlink/?LinkId=66831) 中的步骤进行操作，以满足 RPC 动态端口分配的要求。  
  
## <a name="set-the-appropriate-msdtc-security-configuration-options"></a>设置相应的 MSDTC 安全配置选项  
 Windows 提供了用于管理如何通过网络访问 MSDTC 的安全增强功能。 通过修改 MSDTC 安全设置，你可以控制 MSDTC 在网络中如何与远程计算机通信。 此表列出了配置 MSDTC 安全配置时可用选项的建议值：  
  
|配置选项|默认值|推荐值|  
|--------------------------|-------------------|-----------------------|  
|网络 DTC 访问|Disabled|已启用|  
|**客户端和管理**|||  
|允许远程客户端|Disabled|Disabled|  
|允许远程管理|Disabled|禁用|  
|**事务管理器通信**|||  
|允许入站|Disabled|已启用|  
|允许出站|Disabled|已启用|  
|要求进行相互身份验证|已启用|如果所有远程计算机都运行的是 Windows Server 2003 SP1 或 Windows XP SP2 或更高版本，并且都配置有“要求相互身份验证”，则为“已启用”。|  
|要求对呼叫方进行身份验证|Disabled|如果在群集上运行 MSDTC，则为“已启用”。|  
|不要求进行身份验证|Disabled|在远程计算机为 Windows Server 2003 SP1 之前的版本或 Windows XP SP2 之前的版本时启用。|  
|启用 TIP|Disabled|如果运行 BAM 门户，则为“已启用”。|  
|启用 XA 事务|Disabled|如果与基于 XA 的事务系统进行通信（例如，使用 MQSeries 适配器与 IBM WebSphere MQ 通信），则为“已启用”。|  
  
 应用这些更改后，MSDTC 服务将重新启动。  
  
 要访问 MSDTC 安全配置选项，请按照下列步骤操作：  
  
1.  依次单击 **“开始”** 和 **“运行”**，再键入 **dcomcnfg** 以启动 **“组件服务”** 管理控制台。  
  
2.  单击以展开“组件服务”  ，然后单击以展开“计算机” 。  
  
3.  依次单击以展开“我的电脑” 、“分布式事务协调器” ，右键单击“本地 DTC” ，然后单击“属性” 。  
  
4.  单击“本地 DTC 属性”  对话框的“安全”  选项卡。  
  
> [!NOTE]
>  根据所做的更改，可能需要重新启动计算机以使更改生效。 如果在应用更改并重新启动 MSDTC 服务后仍然遇到问题，请重新启动在其中进行了更改的计算机，以确保更改生效。  
  
 如果启用了“要求相互身份验证”  或“要求对呼叫方进行验证”  配置选项，则必须为客户端计算机帐户授予“从网络访问此计算机”  用户权限。 如果没有为客户端计算机的计算机帐户授予“从网络访问此计算机”  用户权限，或者该帐户包括在“拒绝从网络访问这台计算机”  用户权限中，则该客户端与服务器计算机之间的 DTC 通信将失败。  
  
 默认设置为向 Everyone 组授予“从网络访问此计算机”  用户权限。 因此，除非修改了默认设置，否则无需更改此用户权限。 如果启用了“不要求进行验证”  配置选项，则“从网络访问此计算机”  用户权限不会应用于客户端计算机帐户。  
  
 要更改授予了“从网络访问此计算机”用户权限的用户或组，请按以下步骤进行操作：  
  
1.  依次单击 **“开始”** 和 **“运行”**，键入 **Gpedit.msc**，然后单击 **“确定”**。  
  
2.  展开“本地计算机策略”列表中的以下项：  
  
    -   计算机配置  
  
    -   Windows Settings  
  
    -   安全设置  
  
    -   本地策略  
  
3.  单击“用户权限分配” 。  
  
4.  双击“从网络访问此计算机” ，然后单击“添加用户或组” 。  
  
5.  单击“对象类型” ，选择“计算机”  并单击“确定” 。  
  
6.  在“输入对象名称来选择”区域中  添加计算机名称或组名称。  
  
7.  单击“检查名称”  以验证输入的内容。  
  
8.  单击“确定”两次  。  
  
 要更改“拒绝从网络访问这台计算机”用户权限中包括的用户或组  ，请按以下步骤进行操作：  
  
1.  展开“本地计算机策略”列表中的以下项：  
  
    -   计算机配置  
  
    -   Windows Settings  
  
    -   安全设置  
  
    -   本地策略  
  
2.  单击“用户权限分配” 。  
  
3.  双击“拒绝从网络访问这台计算机” ，然后进行单击以选择要从此用户权限中删除的计算机名称或组。  
  
4.  单击“删除”  ，然后单击“确定” 。  
  
## <a name="set-the-appropriate-values-for-the-enableauthepresolution-and-restrictremoteclients-options"></a>为 EnableAuthEpResolution 和 RestrictRemoteClients 选项设置相应的值  
 Windows 通过要求验证对 RPC 接口的调用来提高安全性。 该功能可以通过 **EnableAuthEpResolution** 和 **RestrictRemoteClients** 注册表项来配置。 若要确保远程计算机能够访问 RPC 接口，请按照下列步骤操作：  
  
> [!WARNING]
>  对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章“Microsoft Windows 注册表说明”，网址为 [Microsoft Windows 注册表说明](http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
1.  依次单击 **启动”** 和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。  
  
     导航到 **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows NT**  
  
2.  在 **RPC** 密钥下，创建具有所示值的以下 DWORD 项。 如果 **RPC** 密钥不存在，则必须予以创建。  
  
    |DWORD 项|默认值|推荐值|  
    |-----------------|-------------------|-----------------------|  
    |EnableAuthEpResolution|0（禁用）|1|  
    |RestrictRemoteClients|1（启用）|0|  
  
3.  关闭“注册表编辑器”。  
  
4.  重新启动 MSDTC 服务。  
  
> [!NOTE]
>  根据所做的更改，可能需要重新启动计算机以使更改生效。 如果在应用更改并重新启动 MSDTC 服务后仍然遇到问题，请重新启动在其中进行了更改的计算机，以确保更改生效。  
  
## <a name="if-windows-firewall-is-running-add-an-exception-for-the-msdtc-service"></a>如果 Windows 防火墙正在运行，则为 MSDTC 服务添加一个例外  
 Windows 防火墙服务可能会阻止计算机之间的 MSDTC 通信。 要确保未阻止计算机之间的 MSDTC 通信，请在 Windows 防火墙服务正在运行时，将 msdtc.exe 添加到 Windows 防火墙例外列表中。  
  
1.  依次单击 **开始”** 和 **“运行”**，键入 **firewall.cpl**，然后单击 **确定”** 以显示 **“Windows 防火墙”** 对话框。  
  
2.  单击“允许程序通过 Windows 防火墙”  以显示“Windows 防火墙设置”  对话框。  
  
3.  单击 **“Windows 防火墙设置”** 对话框的 **“例外”** 选项卡。  
  
4.  单击“添加程序”  以显示“添加程序”对话框  。  
  
5.  单击 **浏览”** 并导航到 *%system32%* \msdtc.ex。  
  
    > [!NOTE]
    >  启动命令提示符，键入 **echo %system32%** 并按 **Enter** ，以确定此计算机上的 \System32 目录的位置。  
  
6.  单击以选择 **“msdtc.exe”** ，然后单击 **“打开”**。  
  
7.  单击 **“更改作用域”** ，指定将允许其进行 MSDTC 通信的一组计算机，然后单击 **“确定”**。  
  
8.  在 **“添加程序”** 对话框中单击 **“确定”** ，并在 **“Windows 防火墙设置”** 对话框中单击 **“确定”** 。  
  
9. 关闭 **“Windows 防火墙”** 对话框。  
  
10. 停止并重新启动分布式事务处理协调器服务。  
  
    -   启动命令提示符，键入 **net stop msdtc** ，然后按 **Enter**键。  
  
    -   在分布式事务处理协调器服务停止后，键入 **net start msdtc** ，然后按 **Enter**键。  
  
## <a name="use-dtctester-or-dtcping-to-verify-msdtc-functionality-over-the-network"></a>使用 DTCTester 或 DTCPing 通过网络检查 MSDTC 功能  
 如果在两台计算机中的一台上安装了 SQL Server，则可以使用 DTCTester 实用程序检查这两台计算机之间是否支持事务处理。 DTCTester 实用程序使用 ODBC 检查 SQL Server 数据库是否支持事务处理。 有关 DTCTester 的详细信息，请参阅 [如何使用 DTCTester 工具](http://go.microsoft.com/fwlink/?LinkId=66232)。  
  
 如果两台计算机中都没有安装 SQL Server，则可以使用 DTCPing 检查这两台计算机之间是否支持事务处理。 DTCPing 是在两台计算机中都没有安装 SQL Server 的情况下替代 DTCTester 实用程序的良好工具，使用时必须既在客户端计算机上运行，也在服务器计算机上运行。 有关 DTCPing 的详细信息，请参阅[如何 MS DTC 防火墙问题进行疑难解答](http://go.microsoft.com/fwlink/?LinkId=61915)。  
  
> [!IMPORTANT]
>  如果 DCTPing 返回警告：“警告：两台测试机器的 CID 值相同”，请按照 **确保为 MSDTC 分配唯一的 CID 值** 一节中的步骤在测试机器之间调整适当的 MSDTC 功能。  
  
## <a name="ensure-that-msdtc-is-assigned-a-unique-cid-value"></a>确保为 MSDTC 分配唯一的 CID 值  
 Windows 操作系统的 MSDTC 功能要求唯一的 CID 值以确保计算机间的 MSDTC 功能正常工作。 Windows 安装的磁盘重复映像必须具有唯一的 CID 值，否则，MSDTC 功能将受到影响。 在使用虚拟硬盘将一个操作系统部署到虚拟机上时，可能会发生这种情况。  
  
 要确定运行 Windows 操作系统的计算机的 MSDTC CID 值是否唯一，请检查两台计算机上 HKEY_CLASSES_ROOT\CID 注册表项下的各条目值。 如果这些值对于每台计算机并不是唯一的，请按照 **如果其他疑难解答步骤不成功，请考虑重新安装分布式事务协调器服务** 一节中的步骤在其中一台计算机上重新安装 MSDTC，为该计算机生成唯一的 MSDTC CID 值并调整相应的 MSDTC 操作。  
  
## <a name="error-new-transaction-cannot-enlist-in-the-specified-transaction-coordinator-0x8004d00a-occurs-if-the-msdtc-connection-between-a-client-computer-and-a-server-computer-is-closed"></a>如果关闭了客户端计算机与服务器计算机之间的 MSDTC 连接，则出现错误“无法在指定事务协调器中登记新事务(0x8004d00a)”  
 在某些情况下，可能出现客户端和服务器之间的现有 MSDTC 连接关闭，并且后续尝试使用此连接将导致以下错误消息：  
无法在指定的事务处理协调器中登记新事务 (0x8004d00a)  
有关详细信息，请参阅[当你尝试在 MS DTC 中启动事务时的错误消息:"中指定的事务处理协调器无法登记新的事务"](http://support.microsoft.com/kb/922430)。  
  
## <a name="consider-reinstalling-the-distributed-transaction-coordinator-service-if-other-troubleshooting-steps-are-not-successful"></a>如果其他疑难解答步骤不成功，请考虑重新安装分布式事务协调器服务  
 如果尝试解决 MSDTC 问题的其他操作不成功，请考虑卸载并重新安装 MSDTC。 请按照下列步骤卸载并重新安装 MSDTC：  
  
1.  以管理员身份打开命令提示符。  
  
2.  在命令提示符处，键入以下内容来卸载分布式事务处理协调器服务：  
    `msdtc -uninstall`  
  
3.  在命令提示符下，键入以下内容来安装分布式事务处理协调器服务：  
    `msdtc –install`  
  
> [!IMPORTANT]
>  重新安装 MSDTC 可能会更改分布式事务处理协调器服务的默认行为。 重新安装 MSDTC 后，请按照下列步骤以确保分布式事务处理协调器服务能够正常工作：  
>   
>  -   重新安装 MSDTC 可能会将 MSDTC 安全配置选项重置回默认值。 验证重新安装 MSDTC 后 MSDTC 安全配置选项是否设置为相应的值。  
> -   重新安装 MSDTC 可能会更改分布式事务处理协调器服务的 **“启动类型”** 值。 验证重新安装 MSDTC 后分布式事务协调器服务的“启动类型”  值已设置为“自动”  。  
> -   重新安装 MSDTC 可能需要重启计算机。 若要确保分布式事务处理协调器服务工作正常，可在重新安装 MSDTC 后重启计算机。  
  
## <a name="see-also"></a>另请参阅  
 [工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Windows Server 群集进行疑难解答](../core/troubleshooting-a-windows-server-cluster.md)