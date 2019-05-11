---
title: 修改 Rnpip 中的现有 PIP |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RNPIPs
- modifying, PIPs
- PIPs, modifying
- assemblies, RNPIPs
ms.assetid: f2ed25c4-1979-4691-9315-e7568e7cca8b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9f7b7bf3f3095e5ac1f5bc87b730935de70d63e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282914"
---
# <a name="modifying-an-existing-pip-in-rnpips"></a>修改 Rnpip 中的现有 PIP
本主题介绍如何更改和重新部署安装的 Microsoft 合作伙伴接口流程 (PIP) 架构中的一个[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]安装程序。 部署为 Rnpip 程序集的一部分的架构。  
  
### <a name="to-modify-an-existing-pip-in-rnpips"></a>修改 Rnpip 中的现有 PIP  
  
1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 找到\<*驱动器*\>\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Utilities\Schema Generator 文件夹。  
  
3. 在命令提示符处，键入**CScript InstallDTD.vbs**，然后按 ENTER。  
  
   > [!NOTE]
   >  只需执行步骤 1 和 2 一次安装 BizTalk Server 之后。  
  
4. 启动**Microsoft Visual Studio 2012**。  
  
5. 在中**文件**菜单，依次指向**打开**，然后单击**项目**。  
  
6. 在中**打开项目**对话框中，转到\<*驱动器*\>\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\架构，并选择**RNPIPs.btproj**。  
  
7. 在中**视图**菜单上，单击**BizTalk 浏览器**。 展开**程序集**，然后右键单击**microsoft.solutions.btarn.schemas.rnpips （3.3.0.0)**。 单击**取消部署**。  
  
8. 启动**Visual Studio 2012 命令提示符**。  
  
9. 转到步骤 6，在命令提示符下，键入中输入的位置**sn-k RNPIPs.snk**，然后按**Enter**。  
  
10. 在解决方案资源管理器中右键单击**Rnpip**，单击**属性**，单击**通用属性**，然后单击**程序集。**  
  
11. 在右窗格中，向下滚动到**强名称**，在**程序集密钥文件**部分中，单击省略号按钮 （...） 按钮，转到步骤 6，在命令提示符下，键入中输入的位置**RNPIPs.snk**，然后单击**确定**。  
  
12. 在中**属性页**对话框中，单击**配置属性**，单击**部署**，单击**重新部署**，选择`True`，然后依次**确定**。  
  
13. 编辑任何所需 Rnpip 中的现有架构。  
  
14. 单击**文件**，然后单击**保存**。  
  
15. 右键单击项目名称，然后依次**生成**。  
  
16. 右键单击项目名称，然后依次**部署**。  
  
17. 单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
18. 在 BizTalk 管理控制台中，展开**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**，然后展开**主机**。  
  
19. 在右窗格中，右键单击该主机的名称，然后单击**停止**。 服务停止后，右键单击主机的名称，然后单击**启动**。  
  
## <a name="see-also"></a>请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [并入新的合作伙伴接口流程](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)