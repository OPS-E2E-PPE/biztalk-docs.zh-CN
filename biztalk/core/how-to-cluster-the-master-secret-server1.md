---
title: 如何安装群集 Master 机密 Server1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, second node
- Master Secret server, restoring
- clustering, Master Secret server
- Master Secret server, clustering
ms.assetid: ef817fa4-e43d-4e3d-8686-5bd675708001
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9740bb1c73dd5f416dda3c2f29bb15fbc7241a51
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972947"
---
# <a name="how-to-cluster-the-master-secret-server"></a>如何安装群集主密钥服务器
若要在主密钥服务器上成功地对企业单一登录 (SSO) 服务进行群集处理，建议你按照本部分中的说明进行操作。  
  
 在群集主密钥服务器时，单一登录服务器将与主密钥服务器上的主动群集实例进行通信。 同样，主密钥服务器上的主动群集实例将与 SSO 数据库进行通信。  
  
 只有 SSO 管理员才能执行此过程。  
  
> [!CAUTION]
>  不能在网络负载平衡 (NLB) 群集上安装主密钥服务器。  
  
### <a name="to-install-and-configure-enterprise-sso-on-the-cluster-nodes"></a>在群集节点上安装和配置企业 SSO  
  
1.  在每个群集节点上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在**组件安装**，选择**企业单一登录管理模块**和**企业单一登录在主密钥服务器**。 安装已成功完成后，请执行**不**运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。  
  
2.  创建**SSO Administrators**和**SSO Affiliate Administrators**域组。 若要创建企业 SSO 服务的群集实例，必须创建这些组作为域组。  
  
3.  创建或指定域帐户是成员的**SSO Administrators**域组。 每个节点上的企业 SSO 服务都将配置为使用此域帐户登录。 此帐户必须具有**作为服务登录**群集中每个节点上的权限。  
  
4.  添加的帐户，你用于登录到域在配置过程**SSO Administrators**组。  
  
    > [!IMPORTANT]
    >  如果没有完成步骤 3 和步骤 4，则配置企业 SSO 服务将失败。  
  
5.  启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置。  
  
6.  选择**自定义配置**选项并输入**数据库服务器名称**，**用户名**，和**密码**值。 选择**配置**以继续。  
  
    > [!NOTE]
    >  因为你只是在此时配置企业 SSO 服务，你可以只需输入你前面此处创建的域帐户。  
  
7.  选择**企业 SSO**选项从左窗格中，然后设置企业 SSO 功能的以下选项：  
  
    1.  选择**启用企业单一登录此计算机上**复选框。  
  
    2.  选择**创建新的 SSO 系统**。  
  
    3.  输入**数据将存储**为**服务器名称**和**数据库名称**值。  
  
    4.  验证先前创建的域帐户是与企业 SSO 服务相关联的帐户。  
  
    5.  输入先前创建的 SSO Administrators 域组作为与 SSO 管理员角色关联的组。  
  
    6.  输入先前创建的 SSO Affiliate Administrators 域组作为与 SSO 关联管理员角色关联的组。  
  
8.  选择**企业 SSO 密钥备份**选项从左窗格中并用于备份企业 SSO 密钥提供适当的参数。 默认情况下，最多支持企业 SSO 密钥*\<驱动器\>*: Files\Enterprise 单一登录的 \program\\*SSOxxxx*.bak。  
  
9. 单击**应用配置**和查看摘要。  
  
10. 单击**下一步**以应用配置。  
  
11. 单击**完成**以关闭配置向导。  
  
12. 关闭 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置。  
  
13. 登录到被动群集节点并启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置。  
  
14. 选择**自定义配置**选项并输入的相同值**数据库服务器名称**，**用户名**，和**密码**，你输入时配置的第一个群集节点。 输入这些值后，单击**配置**以继续。  
  
15. 选择**企业 SSO**选项从左窗格中，然后设置企业 SSO 功能的以下选项：  
  
    1.  选择**启用企业单一登录此计算机上**选项。  
  
    2.  选择**加入现有 SSO 系统**。  
  
    3.  输入 SSO 数据库的相同值**服务器名称**和**数据库名称**你输入时配置的第一个群集节点。  
  
    4.  为域帐户输入与配置第一个群集节点时相同的值。  
  
16. 选择**应用配置**以显示摘要。  
  
17. 选择**下一步**以应用配置。  
  
18. 选择**完成**以关闭配置向导。  
  
19. 关闭[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。  
  
### <a name="to-update-the-master-secret-server-name-in-the-sso-database"></a>更新 SSO 数据库中的主密钥服务器名称  
  
1.  在主动群集节点上的命令提示符下键入以下命令，停止并重新启动企业 SSO 服务：  
  
    ```  
    net stop entsso  
    ```  
  
     和  
  
    ```  
    net start entsso  
    ```  
  
2.  按照以下步骤，将 SSO 数据库中的主密钥服务器名称更改为群集名称：  
  
    > [!NOTE]
    >  群集名称是为网络名称资源定义的名称，该资源是在将包含群集的企业 SSO 服务的群集组/群集服务或应用程序中已创建的资源。 例如，此名称可能是*BIZTALKCLUSTER*。  
  
    1.  将以下代码粘贴到文本编辑器中：  
  
        ```  
        <sso>  
          <globalInfo>  
            <secretServer>BIZTALKCLUSTER</secretServer>  
          </globalInfo>  
        </sso>  
        ```  
  
        > [!NOTE]
        >  *BIZTALKCLUSTER*是在群集中创建的实际网络名称资源的占位符组 / 群集服务或应用程序。  
  
    2.  将文件另存为 .xml 文件。 例如，将文件另存为 SSOCLUSTER.xml。  
  
    3.  在命令提示符下，将目录更改为企业 SSO 安装文件夹。 默认情况下，安装文件夹是*\<驱动器\>*: \program Files\Enterprise 单一登录。  
  
    4.  在命令提示符下键入以下命令，以更新数据库中的主密钥服务器名称：  
  
        ```  
        ssomanage -updatedb XMLFile  
        ```  
  
        > [!NOTE]
        >  *XMLFile*是前面保存的.xml 文件的名称的占位符。  
  
### <a name="to-create-the-clustered-enterprise-sso-resource"></a>创建群集的企业 SSO 资源  
  
1.  如果群集不使用群集的分布式事务处理协调器 (MSDTC) 资源配置然后按照在格式的"提高错误容差 BizTalk 服务器通过使用 Windows Server 群集中"白皮书中的步骤[http://go.microsoft.com/fwlink/？LinkId = 69207](http://go.microsoft.com/fwlink/?LinkId=69207)创建群集的 MSDTC 资源。  
  
2.  单击**启动**，**程序**，**管理工具**，，然后**故障转移群集管理**启动故障转移群集管理程序。  
  
3.  在左侧窗格中，右键单击**故障转移群集管理**单击**管理群集**。  
  
4.  上**选择来管理群集**对话框框中，输入群集进行管理，并且单击**确定**。  
  
5.  在左窗格中单击选择一个包含 IP 地址和网络名称资源的群集服务或应用程序。 按照中的步骤[如何创建使用磁盘、 IP 地址和名称资源的群集组](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md)如果尚不存在与一个 IP 地址和网络名称资源创建组。  
  
    > [!NOTE]
    >  群集的企业 SSO 服务没有明确要求使用同组中的群集物理磁盘资源。  
  
6.  右键单击群集的服务或应用程序，指向**将资源添加**，然后单击**通用服务**以显示**新建资源向导**对话框。  
  
    > [!IMPORTANT]
    >  在**一般服务参数**对话框中，如果不单击以选择**将网络名用作计算机名**复选框，SSO 客户端计算机将生成一个类似于以下的错误时它们尝试联系企业 SSO 服务此群集的实例：  
    >   
    >  检索主密钥失败。  
    >   
    >  请确保主密钥服务器名称正确且该服务器可用。 密钥服务器名称: ENTSSO 错误代码: 0x800706D9，终结点映射器中没有更多的终结点可用。  
  
7.  上**选择服务**页**新建资源向导**，单击以选择**企业单一登录服务**单击**下一步**。  
  
8.  上**确认**页上，单击**下一步**。  
  
9. 上**摘要**页上，单击**完成**。 企业单一登录服务的群集的实例将显示在下面**信息的其他资源**在中间窗格中**故障转移群集管理**接口。  
  
10. 右键单击企业单一登录服务的群集的实例并选择**属性**以显示**企业单一登录服务属性**对话框。  
  
11. 单击**依赖关系**选项卡上的属性对话框中，单击**插入**。  
  
12. 单击下拉框下**资源**，选择**名称：** 资源，然后单击**确定**。  
  
### <a name="to-restore-the-master-secret-on-the-second-cluster-node"></a>在第二个群集节点上恢复主密钥  
  
1.  在故障转移群集管理中，右键单击群集的服务或包含该群集的企业单一登录服务的应用程序，然后单击**让此服务或应用程序联机**启动中的所有资源群集的服务或应用程序。  
  
2.  右键单击群集的服务或应用程序，指向**将此服务或应用程序到另一个节点移动**，然后单击第二个节点。 该步骤将群集服务或包含群集企业单一登录服务的应用程序从第一个节点移动到第二个节点。  
  
3.  右键单击群集的企业单一登录服务，然后单击**将此服务或应用程序脱机**、 右键单击企业 SSO 服务的群集的实例，然后单击**将此服务或应用程序联机**。  
  
    > [!NOTE]
    >  如果不执行此步骤，则还原主密钥的操作可能失败。  
  
4.  将第一个节点上的主密钥备份文件复制到第二个节点上的 \Enterprise Single Sign-On 安装文件夹中。 默认情况下，安装文件夹是*\<驱动器\>*: \program Files\Enterprise 单一登录。  
  
5.  登录到第二个节点，在命令提示符下转入企业 SSO 安装文件夹。  
  
6.  在命令提示符下键入以下命令，在第二个节点上还原主密钥：  
  
    ```  
    ssoconfig -restoresecret RestoreFile  
    ```  
  
    > [!NOTE]
    >  替换*RestoreFile*使用的路径和包含主密钥的备份文件的名称。  
  
     主密钥存储在注册表中，位置为：  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS  
  
7.  将包含群集企业单一登录服务的群集服务或应用程序从此群集节点移动到其他群集节点，以确保故障转移功能。 然后将该群集组移回，以检查故障回复功能。  
  
## <a name="see-also"></a>另请参阅  
 [如何创建使用磁盘、 IP 地址和名称资源的群集组](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md)
