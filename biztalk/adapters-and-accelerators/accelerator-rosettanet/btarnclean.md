---
title: BtarnClean |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BtarnClean utility
- assemblies, undeploying
- BTARN, deleting artifacts
- orchestrations, unenlisting
- ports, stopping
- orchestrations, stopping
- ports, deleting
- BTARN, BtarnClean utility
ms.assetid: fbecbb88-9b18-4b4b-a286-0bfa783f2320
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa8e448d4799329a798cc7b33f222b42c4a28b4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="btarnclean"></a>BtarnClean
BtarnClean 实用程序用于清理[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]项目关闭计算机。 此过程包括以下操作：  
  
-   停止并取消所有登记[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]业务流程  
  
-   停止和删除所有关联的端口  
  
-   取消所有部署[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]。Solutions.BTARN.* 程序集  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*drive*\>\Program Files\ Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK  
  
## <a name="running-btarnclean"></a>运行 BtarnClean  
  
#### <a name="to-run-btarnclean"></a>运行 BtarnClean  
  
1.  開啟命令提示字元。  
  
2.  将移动到\<*驱动器*\>\ 程序 Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。  
  
3.  在命令提示符处，键入**BtarnClean**，然后按 ENTER。  
  
     该实用工具会提示你确认是否要继续。  
  
## <a name="remarks"></a>注释  
 如果运行 BtarnClean 实用工具的计算机上具有依赖于其他项目的 BizTalk 项目，则 BtarnClean 将指示无法删除该项目。 该实用工具会将该项目留在原处，然后继续删除其他项目。 你可以先删除依赖项目，然后再次运行该实用工具。  
  
 如果运行 BtarnClean 实用工具的计算机是多计算机部署的组成部分，则删除这些项目将影响该部署中的其余服务器。  
  
 在开发人员创建的多个流程存在的情况下运行 BtarnClean 实用工具时，该实用工具将不会删除仍在使用的流程。  
  
 如果用户的项目使用的是主接收位置，则 BtarnClean 实用工具将不会删除该接收位置。 在这种情况下，你必须删除接收端口。  
  
 如果要在运行该实用工具后取消对 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 的配置，请从 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 文件夹运行 Configuration.exe /u。  
  
## <a name="see-also"></a>另请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)