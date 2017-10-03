---
title: "如何移动主密钥服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], migrating
- migrating, Master Secret server
- Master Secret server, migrating
ms.assetid: 2bc5137e-f81d-486d-bb91-7c5981896f79
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b35fae6551a95c1c2009ac9786aa791d189f338
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-master-secret-server"></a>如何移动主密钥服务器
本主题将介绍将主密钥从一个服务器移至另一个服务器时可遵循的步骤以及将主密钥从一个服务器移至 Windows Server 群集时可遵循的步骤。  
  
### <a name="to-move-the-master-secret-from-one-server-to-another-server"></a>将主密钥从一个服务器移至另一个服务器  
  
1.  如果尚未在新的主密钥服务器上安装 Microsoft 企业单一登录 (SSO) 服务器，请安装它。 启动 Microsoft 企业单一登录服务器安装程序从 \Platform\SSO\setup.exe [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] CD。  
  
2.  如果尚未配置企业 SSO，则在新的主密钥服务器上对其进行配置。 遵循以下步骤可配置企业 SSO：  
  
    1.  打开配置工具。 默认情况下，配置工具位于\<驱动器 >: \program Files\Enterprise 单一登录 On\Configuration.exe。  
  
    2.  单击以选择**企业 SSO**的左窗格中。  
  
    3.  选中的复选框旁边**启用企业单一登录此计算机上**右窗格中。  
  
    4.  单击选项**加入现有 SSO 系统**。  
  
    5.  指定现有**服务器名称**和**数据库名称**对于的 SSO 数据库选项。  
  
    6.  指定的现有企业 SSO 服务帐户**企业单一登录服务器 Windows 服务的**选项。  
  
        > [!NOTE]
        >  此帐户必须为域帐户。  
  
    7.  单击选项**应用配置**单击**配置**中配置向导对话框中，以完成配置。  
  
    8.  单击**完成**并关闭配置工具。  
  
3.  备份现有主密钥中的步骤[如何返回向上主密钥](../core/how-to-back-up-the-master-secret.md)。  
  
4.  更改 SSO 数据库中的主密钥服务器名称以引用新的主密钥服务器。 例如，新主密钥服务器的名称可能**NewMSSServer**。 若要执行此操作，请对原始主密钥服务器执行以下步骤：  
  
    1.  将以下代码粘贴在诸如 notepad.exe 之类的文本编辑器中：  
  
        ```  
        <sso>  
        <globalInfo>  
        <secretServer>NewMSSServer</secretServer>  
        </globalInfo>  
        </sso>  
        ```  
  
    2.  将文件保存为.xml 文件。 例如，将文件另存**NewMSSServer.xml**。  
  
    3.  在命令提示符下，将目录更改为企业 SSO 安装文件夹。 默认情况下，安装文件夹是\<驱动器 >: \program Files\Enterprise 单一登录。  
  
    4.  类型**ssomanage updatedb** *XMLFile*来更新数据库中的主密钥服务器名称。  
  
        > [!NOTE]
        >  替换*XMLFile*与保存的.xml 文件的名称。  
  
        > [!NOTE]
        >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5.  在新的主密钥服务器上重新启动企业单一登录服务。  
  
6.  按照中的步骤来还原到新主密钥服务器上的备份主密钥[如何还原主密钥](../core/how-to-restore-the-master-secret.md)新主密钥服务器上。  
  
### <a name="to-move-the-master-secret-from-one-server-to-a-windows-server-cluster"></a>将主密钥从一台服务器移至 Windows Server 群集  
  
1.  安装和配置企业 SSO 服务在 Windows Server 群集上的中的步骤[如何安装群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)。 完成所有中所述的步骤除外本主题中的步骤**还原第二个群集节点上的主密钥**部分。 由于要将现有的主密钥服务器移动到群集不选择此选项**创建新的 SSO 系统**企业 SSO 配置在群集节点上时。 配置每个群集节点时，请在 BizTalk Server 配置程序中为企业 SSO 功能设置下列选项：  
  
    1.  旁边的复选框**启用企业单一登录此计算机上**。  
  
    2.  单击选项**加入现有 SSO 系统**。  
  
    3.  输入现有 SSO 数据库服务器名称和数据库名称的值。  
  
    4.  在指定用于企业单一登录服务的帐户时指定现有 SSO 服务帐户。  
  
2.  将现有主密钥备份文件复制到每个群集节点上的 \Enterprise Single Sign-On 文件夹。  
  
3.  如果该 Windows Server 群集将承载一个或多个群集 BizTalk 主机，请使用 ssomanage 命令行实用工具将所有用户的 SSO 服务器名称设置为群集主密钥服务器。 组中每个 BizTalk 服务器上，应从企业 SSO 安装文件夹运行此命令。 例如，以下命令行会将所有用户的 SSO 服务器名称设置为群集主密钥服务器：  
  
    ```  
    ssomanage -serverall SSOCLUSTER  
    ```  
  
    > [!NOTE]
    >  *SSOCLUSTER*是实际的网络的占位符名称包含群集的主密钥服务器中在群集组中创建的资源这种情况下，所有 BizTalk 主机必须都创建作为在同一个群集资源为群集的企业 SSO 服务资源的群集组。 不支持在群集企业 SSO 服务的 Windows Server 群集节点上运行非群集 BizTalk 主机实例的配置。 这是因为当群集企业 SSO 服务由于与 SSO 服务上的 BizTalk 主机实例存在依赖关系而将故障转移至另一节点时，非群集 BizTalk 主机实例将失败。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4.  在群集管理器中，右键单击包含群集的企业 SSO 服务资源的群集组，然后单击**联机**群集组中启动的所有资源。  
  
5.  如果此 Windows 服务器群集将承载一个或多个聚集 BizTalk 主机，更新 SSO 服务器名称以访问**BizTalk 组属性**页后，可以引用群集的主密钥服务器。 启动**BizTalk Server 管理**，右键单击 BizTalk 组，然后选择**属性**菜单项，然后更新的条目**SSO 服务器名称**单击**确定**。  
  
    > [!NOTE]
    >  在此情况下，所有 BizTalk 主机都必须在群集企业 SSO 服务资源所在的群集组中创建为群集资源。 不支持在群集企业 SSO 服务的 Windows Server 群集节点上运行非群集 BizTalk 主机实例的配置。 这是因为当群集企业 SSO 服务由于与 SSO 服务上的 BizTalk 主机实例存在依赖关系而将故障转移至另一节点时，非群集 BizTalk 主机实例将失败。  
  
6.  右键单击企业 SSO 服务的群集的实例，然后单击**脱机**、 右键单击企业 SSO 服务的群集的实例，然后单击**联机**。  
  
    > [!NOTE]
    >  如果未完成此步骤，则尝试还原主密钥的操作可能失败。  
  
7.  在包含群集主密钥服务器的 Windows 群集的每一个节点上恢复备份的主密钥。 按照中的步骤[如何还原主密钥](../core/how-to-restore-the-master-secret.md)保存群集主密钥服务器的 Windows 群集的每个节点上。  
  
## <a name="see-also"></a>另请参阅  
 [管理主密钥](../core/managing-the-master-secret.md)