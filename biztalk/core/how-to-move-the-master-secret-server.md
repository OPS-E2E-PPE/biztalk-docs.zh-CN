---
title: 如何移动主密钥服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], migrating
- migrating, Master Secret server
- Master Secret server, migrating
ms.assetid: 2bc5137e-f81d-486d-bb91-7c5981896f79
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b71ee8252d0a268bb3d087f53607c8a58e831c85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384479"
---
# <a name="how-to-move-the-master-secret-server"></a>如何移动主密钥服务器
本主题介绍你可以遵循主密钥移到另一台服务器和您可以按照将主密钥从一台服务器移动到 Windows Server 群集的步骤中的步骤。  
  
### <a name="to-move-the-master-secret-from-one-server-to-another-server"></a>若要将主密钥从一台服务器移动到另一台服务器  
  
1.  如果尚未安装，请在新的主密钥服务器上安装 Microsoft 企业单一登录 (SSO) 服务器。 启动从 BizTalk Server CD 上的 \Platform\SSO\setup.exe Microsoft 企业单一登录服务器安装程序。  
  
2.  如果未配置新的主密钥服务器上配置企业 SSO。 请按照下列步骤来配置企业 SSO:  
  
    1.  打开配置工具。 默认情况下，配置工具位于\<驱动器\>: \Program Files\Common Files\Enterprise Single On\Configuration.exe。  
  
    2.  单击此项可选择**企业 SSO**的左窗格中。  
  
    3.  选中复选框旁边**启用企业单一登录此计算机上**右窗格中。  
  
    4.  单击选项**加入现有 SSO 系统**。  
  
    5.  指定的现有**服务器名称**并**数据库名称**sso 数据库选项。  
  
    6.  指定的现有企业 SSO 服务帐户**企业单一登录服务器 Windows 服务**选项。  
  
        > [!NOTE]
        >  这必须是域帐户。  
  
    7.  单击选项**应用配置**然后单击**配置**中配置向导对话框中，以完成配置。  
  
    8.  单击**完成**并关闭配置工具。  
  
3.  备份现有主密钥中的步骤[如何返回主密钥](../core/how-to-back-up-the-master-secret.md)。  
  
4.  更改主密钥服务器名称以引用新的主密钥服务器在 SSO 数据库中。 例如，新的主密钥服务器的名称可能**NewMSSServer**。 若要执行此操作，请在原始主服务器上执行以下步骤：  
  
    1.  以下代码粘贴到 notepad.exe 等文本编辑器中：  
  
        ```  
        <sso>  
        <globalInfo>  
        <secretServer>NewMSSServer</secretServer>  
        </globalInfo>  
        </sso>  
        ```  
  
    2.  将文件保存为.xml 文件。 例如，将该文件作为**NewMSSServer.xml**。  
  
    3.  在命令提示符下，将更改为企业 SSO 安装文件夹。 默认情况下，安装文件夹是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
    4.  类型**ssomanage-updatedb** *XMLFile*更新数据库中的主密钥服务器名称。  
  
        > [!NOTE]
        >  替换*XMLFile*与保存的.xml 文件的名称。  
  
        > [!NOTE]
        >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
5.  重新启动新的主密钥服务器上的企业单一登录服务。  
  
6.  按照中的步骤来还原到新的主密钥服务器上备份主密钥[如何还原主密钥](../core/how-to-restore-the-master-secret.md)上新的主密钥服务器。  
  
### <a name="to-move-the-master-secret-from-one-server-to-a-windows-server-cluster"></a>若要将主密钥从一台服务器移动到 Windows Server 群集  
  
1.  安装和配置企业 SSO 服务上的 Windows Server 群集中的步骤[如何群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)。 完成的步骤中所述的步骤除了本主题中的所有**还原第二个群集节点上的主密钥**部分。 由于要将现有的主密钥服务器移动到群集未选择的选项**创建新的 SSO 系统**群集节点上配置企业 SSO 时。 在配置每个群集节点时，BizTalk Server 配置程序中设置企业 SSO 功能的以下选项：  
  
    1.  旁边的复选框**启用企业单一登录此计算机上**。  
  
    2.  单击选项**加入现有 SSO 系统**。  
  
    3.  输入现有 SSO 数据库服务器名称和数据库名称的值。  
  
    4.  指定要使用企业单一登录服务的帐户时，请输入现有 SSO 服务帐户。  
  
2.  将现有主密钥备份文件复制到文件夹每个群集节点上 \Enterprise Single Sign-on。  
  
3.  如果该 Windows Server 群集将承载一个或多个群集的 BizTalk 主机，则设置为群集主密钥服务器使用 ssomanage 命令行实用工具的所有用户的 SSO 服务器名称。 此命令应在组中每个 BizTalk Server 上运行的企业 SSO 安装文件夹。 例如，下面的命令行将设置为群集主密钥服务器的所有用户的 SSO 服务器名称：  
  
    ```  
    ssomanage -serverall SSOCLUSTER  
    ```  
  
    > [!NOTE]
    >  *SSOCLUSTER*是实际网络名称资源的占位符在包含群集主密钥服务器资源的群集组中创建这种情况下，所有 BizTalk 主机必须都创建为群集资源在同一个在群集企业 SSO 服务资源的群集组。 其中群集企业 SSO 服务的 Windows Server 群集节点上运行的非群集 BizTalk 主机实例不是受支持的配置。 这是因为当群集的企业 SSO 服务故障转移到另一个节点上的 SSO 服务的 BizTalk 主机实例的依赖性时，非群集 BizTalk 主机实例将失败。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4.  在群集管理器中，右键单击包含群集的企业 SSO 服务资源，群集组，然后单击**使联机**以启动群集组中所有资源。  
  
5.  如果该 Windows Server 群集将承载一个或多个群集 BizTalk 主机，更新可在中访问的 SSO 服务器名称**BizTalk 组属性**页以引用群集主密钥服务器。 启动**BizTalk Server 管理**，右键单击 BizTalk 组，然后选择**属性**菜单项，然后更新的条目**SSO 服务器名称**单击**确定**。  
  
    > [!NOTE]
    >  在此方案中，所有 BizTalk 主机都必须都创建为群集企业 SSO 服务资源的同一群集组中的群集资源。 其中群集企业 SSO 服务的 Windows Server 群集节点上运行的非群集 BizTalk 主机实例不是受支持的配置。 这是因为当群集的企业 SSO 服务故障转移到另一个节点上的 SSO 服务的 BizTalk 主机实例的依赖性时，非群集 BizTalk 主机实例将失败。  
  
6.  右键单击企业 SSO 服务的群集的实例，然后单击**转为脱机**，右键单击企业 SSO 服务的群集的实例，然后单击**联机**。  
  
    > [!NOTE]
    >  如果未完成此步骤中，可能会不成功尝试还原主密钥。  
  
7.  还原包含群集主密钥服务器的 Windows 群集的每个节点上的备份主密钥。 按照中的步骤[如何还原主密钥](../core/how-to-restore-the-master-secret.md)包含群集主密钥服务器在 Windows 群集的每个节点上。  
  
## <a name="see-also"></a>请参阅  
 [管理主密钥](../core/managing-the-master-secret.md)