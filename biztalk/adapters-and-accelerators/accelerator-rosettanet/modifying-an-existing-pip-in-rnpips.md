---
title: "修改现有 PIP 在 RNPIPs |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RNPIPs
- modifying, PIPs
- PIPs, modifying
- assemblies, RNPIPs
ms.assetid: f2ed25c4-1979-4691-9315-e7568e7cca8b
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aa00b1a029092247d3c4ce935edfd88f4344a95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="modifying-an-existing-pip-in-rnpips"></a>修改在 RNPIPs 现有 PIP
本主题介绍如何更改和重新部署安装的合作伙伴接口过程 (PIP) 架构之一[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]安装程序。 该架构部署为 RNPIP 程序集的组成部分。  
  
### <a name="to-modify-an-existing-pip-in-rnpips"></a>修改 RNPIP 中的现有 PIP  
  
1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  找到\<*驱动器*> files\microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK\Utilities\Schema 生成器文件夹。  
  
3.  在命令提示符处，键入**CScript InstallDTD.vbs**，然后按 ENTER。  
  
    > [!NOTE]
    >  只需执行步骤 1 和 2 一次安装之后[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]。  
  
4.  启动**Microsoft Visual Studio 2012**。  
  
5.  在**文件**菜单上，指向**打开**，然后单击**项目**。  
  
6.  在**打开项目**对话框中，移动到\<*驱动器*> files\microsoft BizTalk\<版本 > 作为 RosettaNet\SDK\Schemas，然后选择的快捷键**RNPIPs.btproj**。  
  
7.  在**视图**菜单上，单击**BizTalk 资源管理器**。 展开**程序集**，然后右键单击**Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)**。 单击**取消部署**。  
  
8.  启动**Visual Studio 2012 的命令提示符**。  
  
9. 将移动到在步骤 6，在命令提示符下，键入中输入的位置**sn-k RNPIPs.snk**，然后按**Enter**。  
  
10. 在解决方案资源管理器，右键单击**RNPIPs**，单击**属性**，单击**通用属性**，然后单击**程序集。**  
  
11. 在右窗格中，向下滚动到**强名称**中**程序集密钥文件**部分中，单击省略号按钮 （…） 按钮，转到在步骤 6，在命令提示符下，键入中输入的位置**RNPIPs.snk**，然后单击**确定**。  
  
12. 在**属性页**对话框中，单击**配置属性**，单击**部署**，单击**重新部署**，选择`True`，然后单击**确定**。  
  
13. 根据需要编辑 RNPIP 中的任何现有架构。  
  
14. 单击**文件**，然后单击**保存**。  
  
15. 右键单击项目名称，并依次**生成**。  
  
16. 右键单击项目名称，并依次**部署**。  
  
17. 单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
18. 在 BizTalk 管理控制台中，展开**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **（本地）**，然后展开**主机**。  
  
19. 在右窗格中，右键单击该主机的名称，然后单击**停止**。 服务已停止后，右键单击该主机的名称，然后单击**启动**。  
  
## <a name="see-also"></a>另请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [合并新的合作伙伴接口进程](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)