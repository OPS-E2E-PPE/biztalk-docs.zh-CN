---
title: "合并新的合作伙伴接口进程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, PIP schemas
- PIP schemas
- PIP schemas, deploying
- PIP schemas, downloading
- creating, PIP schemas
- PIP schemas, creating
ms.assetid: 6a5fcbcb-c6aa-40c0-bcca-dd0c391e7f42
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4874c623c80a008a4f2c1aa5382c49e37616b6af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="incorporating-a-new-partner-interface-process"></a>合并新的合作伙伴接口进程
你可以在 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 程序集中并入新的 RosettaNet 合作伙伴接口流程 (PIP) 架构。 你可以通过执行以下步骤来完成此任务：  
  
-   从 RosettaNet Web 站点下载 PIP 架构[http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859)。  
  
-   将该架构作为 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] RNPIP 程序集的一部分或作为单独 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 程序集的一部分部署到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。 有关详细信息，请参阅[与新 PIP 扩展 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)。  
  
-   在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台中创建新的流程配置设置。 有关详细信息，请参阅[如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。  
  
 下载的架构文件通常为 .dtd 格式，并带有一个 .doc 文件格式的 RosettaNet 组织的伴随 PIP 规范。 扩展管道以使用新架构的流程中包含将 PIP 的 .dtd 文件转换为 .xsd 文件的步骤。  
  
 安装 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 后，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 将包含若干个 XSD 架构。 你可以找到这些架构中的\<*驱动器*>: files\microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK\Schemas 文件夹。 BTARN 将这些架构置入 RNPIPs.dll 文件中。 如果你需要更改这些架构中的一个，则必须打开同一文件夹中的 RNPIP 项目，在 BizTalk 编辑器中更改该架构，然后重新编译并重新部署该程序集。 重新部署 RNPIPs.dll 文件后，必须重新部署使用该架构的管道。 你可以使用此流程将新架构并入 BTARN 中，但通过扩展管道来包含新架构更加方便。  
  
### <a name="to-obtain-the-pip-schema"></a>获取 PIP 架构  
  
-   在 Internet Explorer 中，转到 RosettaNet Web 站点[http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859)。  
  
## <a name="see-also"></a>另请参阅  
 [扩展与新 PIP BTARN](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)