---
title: "BTAD_InstallDir |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: BTAD_InstallDir [environment variable]
ms.assetid: 3120f897-5501-4e99-8552-9d97e6314cd1
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9485be1fe9fad30511438d03957c787865507399
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="btadinstalldir"></a>BTAD_InstallDir
BTAD_InstallDir 包含 BizTalk 应用程序的安装路径。 只有在操作为 Create 或 Update 且 BTAD_HostClass 是 BizTalkHostInstance 时，BTAD_InstallDir 才可用。  
  
## <a name="remarks"></a>注释  
 BTAD_InstallDir 设置为 Windows Installer 包的 TARGETDIR 属性。 默认值是通过 BizTalk %ProgramFiles%\Generated\\<*应用程序名称*>。  
  
## <a name="see-also"></a>另请参阅  
 [前期和后期处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md)   
 [环境变量如何指示部署状态](../core/how-environment-variables-indicate-deployment-state.md)   
 [如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)