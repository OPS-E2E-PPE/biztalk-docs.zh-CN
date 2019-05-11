---
title: 并入新的合作伙伴接口流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, PIP schemas
- PIP schemas
- PIP schemas, deploying
- PIP schemas, downloading
- creating, PIP schemas
- PIP schemas, creating
ms.assetid: 6a5fcbcb-c6aa-40c0-bcca-dd0c391e7f42
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa2c372adb1993aacee1ba2d56d8a5dc2f8d9d0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283554"
---
# <a name="incorporating-a-new-partner-interface-process"></a>并入新的合作伙伴接口流程
您可以将合并新的 RosettaNet 合作伙伴接口流程 (PIP) 架构中 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]程序集。 为此，：  
  
- 从 RosettaNet 网站下载 PIP 架构[ http://go.microsoft.com/fwlink/?linkid=33859 ](http://go.microsoft.com/fwlink/?linkid=33859)。  
  
- 部署到的架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为的一部分[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Rnpip 程序集或作为单独的一部分[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]程序集。 有关详细信息，请参阅[使用新 PIP 扩展 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)。  
  
- 创建新的进程配置设置中[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。 有关详细信息，请参阅[如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。  
  
  下载的架构通常为.dtd 格式，但为.doc 文件的 RosettaNet 组织的伴随 PIP 规范。 扩展管道以使用新的架构的过程包括将 PIP 的.dtd 文件转换为.xsd 文件。  
  
  当你安装[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，则[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 包括若干个 XSD 架构。 您可以找到这些架构中的\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Schemas 文件夹。 BTARN 生成这些架构置入 RNPIPs.dll 文件。 如果需要更改这些架构之一，必须在同一文件夹中打开 Rnpip 项目、 更改架构在 BizTalk 编辑器中，然后重新编译和重新部署程序集。 重新部署 RNPIPs.dll 文件后，必须重新部署管道，将使用的架构。 可以使用此过程以合并新架构 BTARN 中，但更轻松地扩展管道来包含新架构。  
  
### <a name="to-obtain-the-pip-schema"></a>若要获取 PIP 架构  
  
-   在 Internet Explorer 中，转到 RosettaNet Web 站点[ http://go.microsoft.com/fwlink/?linkid=33859 ](http://go.microsoft.com/fwlink/?linkid=33859)。  
  
## <a name="see-also"></a>请参阅  
 [使用新 PIP 扩展 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)