---
title: 卸载 BizTalk Server 上的 BizTalk RosettaNet 加速器 (BTARN) |Microsoft Docs"
description: 取消部署项目，并取消配置 btarn，让其从 BizTalk Server 中删除快捷键
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: a8e26119039910f398620efe478d07eeebca6f08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299964"
---
# <a name="uninstall-the-rosettanet-accelerator"></a>卸载 RosettaNet 加速器

## <a name="before-you-begin"></a>开始之前
  
* 如果只运行**Setup.exe**，卸载过程不会删除业务活动监视 (BAM) 项目、 BizTalk 项目、 Internet 信息服务 (IIS) 虚拟目录和应用程序池。  
  
* 如果您使用了**Loopback**实用工具创建镜像协议对于单台计算机部署，然后运行该工具与 **/禁用 <** **本组织** **>** 选项在中删除合作伙伴之前**BTARN 管理控制台**。  
  
* 如果此服务器是多计算机部署的一部分，不能运行**BtarnClean**实用程序或手动取消部署 BTARN 程序集。 删除一台计算机上的项目会中断其他计算机的功能。  如果你想要从所有服务器上卸载 BTARN，然后运行**BtarnClean**实用程序。 

  
## <a name="undeploy-the-artifacts"></a>取消部署的项目  

我们建议在取消部署之前备份 BAM 项目。 

1. 取消部署已部署的所有 BAM 项目：  
  
    1.  在命令提示符处，运行以下命令：  
  
         ```cd %ProgramFiles%\\<BizTalk Server installation directory\>\Tracking```
  
    2.  在已安装跟踪 UI 命令提示符处，运行以下命令：  
  
         ```bm remove-all DefinitionFile:"%ProgramFiles%\\<installation directory\>\BAMTracking\tracking.xml"```
  
        > [!NOTE]
        >  有关 BAM 的详细信息，请参阅[管理业务活动监视](../../core/managing-bam.md) 
  
2.  备份和从 BTARN 管理控制台中删除所有协议、 合作伙伴和本组织。 请参阅有关使用信息 （在 BTARN 帮助的操作节点中） 的"管理 BTARN 配置"主题**BtarnConfig**实用工具备份协议和合作伙伴。  
  
    > [!NOTE]
    >  * 停止并取消部署 BTARN 使用创建的 BizTalk 项目[BtarnClean](btarnclean.md)实用程序。
    >  * 删除任何已部署的其他项目。 请参阅[正在取消部署 BizTalk 应用程序](../../core/undeploying-biztalk-applications.md)。
  
3.  从 BTARN 安装程序，找到 MSI\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK 文件夹。 在 SDK 文件夹中，双击**BTARNClean.exe**，然后选择**Y**若要继续，或**N**取消运行该实用程序。  
  
    > [!NOTE]
    >  如果你的服务器是多计算机部署方案的一部分，则可以跳过步骤 3。 取消部署任何共享的资源会削弱部署中的其他服务器上的功能。  
  
4.  取消部署任何自定义程序集创建和部署。  
  
5.  在命令提示符处，转到 files\microsoft BizTalk Server <your version>\Tracking。 运行下面的命令： 

    ```BM UNDEPLOY ALL <drive\>:\Program Files\\<installation directory\>\BAMTracking\tracking.xml```
  
## <a name="unconfigure-btarn"></a>取消配置 BTARN
  
1.  找到并运行以下命令，取消配置 BTARN:  
  
     ***<drive\>***  **:\Program Files\\<installation directory\>\Configuration.exe /u**  
  
2.  在控制面板中，双击**添加或删除程序**。  
  
3.  在中**当前安装的程序**列表中，单击**Microsoft BizTalk Accelerator for RosettaNet**，然后单击**更改/删除**。  
  
4.  在中**程序维护**对话框中，选择**删除**，然后单击**下一步**。  
  
5.  在中**摘要**对话框中，单击**卸载**。  
  
6.  在中**卸载已完成**对话框中，单击**完成**。  
  
    > [!NOTE]
    >  卸载过程不会删除在 BTARN 数据库 （BTARNARCHIVE、 BTARNCONFIG 和 BTARNDATA）。 您必须手动删除它们。  
  
7.  打开 SQL Server Management Studio。  
  
8.  在中**连接到服务器**对话框中，单击**Connect**。  
  
9. 展开**数据库**的左窗格中的节点。 右键单击 BTARN 数据库之一，然后单击**删除**。  
  
10. 在中**删除对象**对话框中，选择**关闭现有连接**，然后单击**确定**。  
  
