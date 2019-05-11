---
title: 如何群集主密钥机密 Server1 |Microsoft Docs
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
ms.openlocfilehash: 88f7b25a8cf3138862e65f7c8bd96f041fc512d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386956"
---
# <a name="how-to-cluster-the-master-secret-server"></a>如何群集主密钥服务器
我们建议你遵循本部分中的说明已成功在主密钥服务器上群集企业单一登录 (SSO) 服务。  
  
 当群集主密钥服务器时，实现单一登录服务器将与主密钥服务器的主动群集实例通信。 同样，主密钥服务器的主动群集的实例与 SSO 数据库进行通信。  
  
 必须是 SSO 管理员才能执行此过程。  
  
> [!CAUTION]
>  不能在网络负载平衡 (NLB) 群集上安装主密钥服务器。  
  
### <a name="to-install-and-configure-enterprise-sso-on-the-cluster-nodes"></a>若要安装和群集节点上配置企业 SSO  
  
1. 安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]每个群集节点上。 在中**组件安装**，选择**企业单一登录管理模块**并**企业单一登录主密钥服务器**。 安装已成功完成后，请执行**不**运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。  
  
2. 创建**SSO Administrators**并**SSO Affiliate Administrators**域组。 若要创建企业 SSO 服务的群集的实例，必须为域组中创建这些组。  
  
3. 创建或指定的成员的域帐户**SSO Administrators**域组。 每个节点上的企业 SSO 服务配置为作为此域帐户登录。 此帐户必须具有**作为服务登录**直接在群集中每个节点上。  
  
4. 您用来登录到域在配置过程中的帐户添加**SSO Administrators**组。  
  
   > [!IMPORTANT]
   >  如果未完成步骤 3 和 4，企业 SSO 服务的配置将失败。  
  
5. 启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。  
  
6. 选择**自定义配置**选项并输入**数据库服务器名称**，**用户名**，以及**密码**值。 选择**配置**以继续。  
  
   > [!NOTE]
   >  因为您只是这次配置企业 SSO 服务，你可以只输入前面步骤中创建的域帐户。  
  
7. 选择**企业 SSO**选项在左窗格中，并设置以下选项为企业 SSO 功能：  
  
   1.  选择**启用企业单一登录此计算机上**复选框。  
  
   2.  选择**创建新的 SSO 系统**。  
  
   3.  输入**数据存储区**有关**服务器名称**并**数据库名称**值。  
  
   4.  验证前面创建的域帐户是与企业 SSO 服务相关联的帐户。  
  
   5.  输入先前作为与 SSO 管理员角色关联的组创建的 SSO Administrators 域组。  
  
   6.  输入先前作为与 SSO 关联管理员角色关联的组创建的 SSO Affiliate Administrators 域组。  
  
8. 选择**企业 SSO 密钥备份**选项在左窗格中，并提供用于备份企业 SSO 密钥的适当的参数。 默认情况下，企业 SSO 密钥备份到*\<驱动器\>*: Files\Enterprise Single Sign-on \Program Files\Common\\*SSOxxxx*.bak。  
  
9. 单击**应用配置**并查看摘要。  
  
10. 单击**下一步**以应用配置。  
  
11. 单击**完成**以关闭配置向导。  
  
12. 关闭[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。  
  
13. 登录到被动群集节点并启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。  
  
14. 选择**自定义配置**选项并输入相同的值**数据库服务器名称**，**用户名**，以及**密码**，你输入时配置的第一个群集节点。 输入这些值后，单击**配置**以继续。  
  
15. 选择**企业 SSO**选项在左窗格中，并设置以下选项为企业 SSO 功能：  
  
    1.  选择**启用企业单一登录此计算机上**选项。  
  
    2.  选择**加入现有 SSO 系统**。  
  
    3.  为 SSO 数据库中输入相同的值**服务器名称**并**数据库名称**输入时配置的第一个群集节点。  
  
    4.  配置第一个群集节点时的域帐户输入相同的值。  
  
16. 选择**应用配置**以显示摘要。  
  
17. 选择**下一步**以应用配置。  
  
18. 选择**完成**以关闭配置向导。  
  
19. 关闭[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。  
  
### <a name="to-update-the-master-secret-server-name-in-the-sso-database"></a>若要更新 SSO 数据库中的主密钥服务器名称  
  
1.  若要停止并重新启动企业 SSO 服务在活动群集节点上键入以下命令从命令提示符：  
  
    ```  
    net stop entsso  
    ```  
  
     和  
  
    ```  
    net start entsso  
    ```  
  
2.  将 SSO 数据库中的主密钥服务器名称更改为群集名称，通过执行以下步骤：  
  
    > [!NOTE]
    >  群集名称是定义已在群集中创建的网络名称资源的名称组 / 群集服务或应用程序将包含群集的企业 SSO 服务。 例如，名称可能*BIZTALKCLUSTER*。  
  
    1.  在文本编辑器中粘贴以下代码：  
  
        ```  
        <sso>  
          <globalInfo>  
            <secretServer>BIZTALKCLUSTER</secretServer>  
          </globalInfo>  
        </sso>  
        ```  
  
        > [!NOTE]
        >  *BIZTALKCLUSTER*是占位符，在群集中创建的实际网络名称资源组 / 群集服务或应用程序。  
  
    2.  将文件保存为.xml 文件。 例如，保存该文件另存为 SSOCLUSTER.xml。  
  
    3.  在命令提示符下，将更改为企业 SSO 安装文件夹。 默认情况下，安装文件夹是*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
    4.  若要更新数据库中的主密钥服务器名称的命令提示符处键入以下命令：  
  
        ```  
        ssomanage -updatedb XMLFile  
        ```  
  
        > [!NOTE]
        >  *XMLFile*是之前保存的.xml 文件的名称的占位符。  
  
### <a name="to-create-the-clustered-enterprise-sso-resource"></a>若要创建群集的企业 SSO 资源  
  
1.  如果未使用群集分布式事务处理协调器 (MSDTC) 资源配置群集然后按照"提高容错容差在 BizTalk Server 通过使用 Windows Server 群集中"白皮书，网址中的步骤[ http://go.microsoft.com/fwlink/?LinkId=69207 ](http://go.microsoft.com/fwlink/?LinkId=69207)若要创建群集的 MSDTC 资源。  
  
2.  单击**启动**，**程序**，**管理工具**，然后**故障转移群集管理**启动故障转移群集管理程序。  
  
3.  在左侧窗格中，右键单击**故障转移群集管理**然后单击**管理群集**。  
  
4.  上**选择要管理的群集**对话框框中，输入群集进行管理，然后单击**确定**。  
  
5.  在左侧窗格中，单击以选择群集的服务或应用程序中包含的 IP 地址和网络名称资源。 按照中的步骤[如何创建具有磁盘、 IP 地址和名称资源的群集组](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md)若要创建具有 IP 地址和网络名称资源的组，如果尚不存在。  
  
    > [!NOTE]
    >  群集的企业 SSO 服务不会明确要求使用同一组中的群集物理磁盘资源。  
  
6.  右键单击群集的服务或应用程序，指向**将资源添加**，然后单击**通用服务**以显示**新建资源向导**对话框。  
  
    > [!IMPORTANT]
    >  在中**一般服务参数**对话框中，如果未单击以选中**将网络名用作计算机名**复选框，SSO 客户端计算机将生成类似于以下的错误时它们尝试联系企业 SSO 服务的此群集的实例：  
    >   
    >  检索主密钥失败。  
    >   
    >  验证主密钥服务器名称正确以及可用。 密钥服务器名称：ENTSSO 错误代码：0x800706D9，提供的终结点映射程序有没有更多的终结点。  
  
7.  上**选择服务**页**新建资源向导**，单击以选择**企业单一登录服务**然后单击**下一步**。  
  
8.  上**确认**页上，单击**下一步**。  
  
9. 上**摘要**页上，单击**完成**。 企业单一登录服务的群集的实例将显示在下面**信息的其他资源**中的中心窗格**故障转移群集管理**接口。  
  
10. 右键单击企业单一登录服务的群集的实例，然后选择**属性**以显示**企业单一登录服务属性**对话框。  
  
11. 单击**依赖项**选项卡的属性对话框中，单击**插入**。  
  
12. 单击下的下拉**资源**，选择**名称：** 资源，然后单击**确定**。  
  
### <a name="to-restore-the-master-secret-on-the-second-cluster-node"></a>若要还原第二个群集节点上的主密钥  
  
1.  在故障转移群集管理中，右键单击群集的服务或包含群集的企业单一登录服务的应用程序，然后单击**使此服务或应用程序联机**以启动所有中的资源群集的服务或应用程序。  
  
2.  右键单击群集的服务或应用程序，指向**将此服务或应用程序到另一个节点移动**，然后单击第二个节点。 此步骤将群集的服务或包含群集的企业单一登录服务从第一个节点到第二个节点的应用程序。  
  
3.  右键单击群集的企业单一登录服务，然后单击**使此服务或应用程序脱机**，然后右键单击企业 SSO 服务的群集的实例，并单击**使此服务或应用程序联机**。  
  
    > [!NOTE]
    >  如果未完成此步骤可能会不成功尝试还原主密钥。  
  
4.  将第一个节点的主密钥备份文件复制到的 \Enterprise Single Sign-on 安装文件夹的第二个节点上。 默认情况下，安装文件夹是*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
5.  登录到第二个节点，并在命令提示符下，更改为企业 SSO 安装文件夹。  
  
6.  键入以下命令从命令提示符将主密钥还原到第二个节点：  
  
    ```  
    ssoconfig -restoresecret RestoreFile  
    ```  
  
    > [!NOTE]
    >  替换*RestoreFile*使用的路径和包含主密钥的备份文件的名称。  
  
     主密钥存储在注册表中的以下位置：  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS  
  
7.  移动群集的服务或包含群集的企业单一登录服务从此群集节点到其他群集节点，以确保故障转移功能的应用程序。 然后将群集组移回验证故障回复功能。  
  
## <a name="see-also"></a>请参阅  
 [如何创建具有磁盘、 IP 地址和名称资源的群集组](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md)
